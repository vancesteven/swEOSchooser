# swEOSchooser
Matlab tool for modular equation of state approach for planetary ocean simulations.

Input:
string_EOS: 'mgso4', 'gsw302', 'gsw305'

Output:
struct_swEOS: contains handles to functions useful for modeling planetary oceans based on oceanographic conventions, but using units often convenient for planetary modeling (concentration in g/kgH2O, pressure in MPa, T in K)


For example:
case('mgso4')
        swEOS.adtg=@mgso4_adtg; % (S,T,P) [K/bar] 
        swEOS.alpha=@mgso4_alpha; % (S,T,P) [1/K] 
        swEOS.beta=@mgso4_beta; % (S,T,P) [1/mol]
        swEOS.C=@Larionovp01molalMgSO4; % (T,P) [S/m]
        swEOS.cp=@mgso4_cp; % (S,T,P) [J/kg-K]
        swEOS.dens=@mgso4_dens; % (S,T,P) [kg/m^3]
        swEOS.tfreezing=@mgso4_t_freezing; % (S,P) [K]
        swEOS.latent_heat_melting=@mgso4_latent_heat_melting; % L = mgso4_latent_heat_melting(S,P)
        swEOS.pden=@mgso4_pden; % (S,T,P,PR) [kg/m^3] 
        swEOS.ptmp=@mgso4_ptmp; % (S,T,P,PR) [K}
        swEOS.vel=@mgso4_vel; % (S,T,P) [km/s] 

Equations of state are loaded from associated git repositories.
