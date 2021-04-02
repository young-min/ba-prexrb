# ba-prexrb
Posterior samples from Bayesian Inference on 6 LMXB sources for the estimation of Masses and Radii of Neutron Stars.

* source type: Photosphere Radius Expansion (PRE) X-ray Bursters (XRBs)
* basic algorithm for MCMC: Metropolis-Hastings algorithm
* 6 LMXB
  * 4U 1820-30
  * SAX J1748.9-2021
  * EXO 1745-248
  * KS 1731-260
  * 4U 1724-207
  * 4U 1608-52

* Priors
  * Radius, R_NS [km] : Uniform(2.0, 20.0)
  * Mass, M [Msun] : Uniform(0.6, 3.5)
  * Hydrogen Mass Fraction, x : Uniform(0.0, 0.7)
  * Color-correction factor, fc : Uniform(1.35, 1.45)
  * Spin Frequency, fns [Hz]
    * Uniform(250, 650) : 4U 1820-30, EXO 1745-248, 4U 1724-207
    * fixed fns at measured values.
      * SAX J1748.9-2021 : 410 Hz
      * KS 1731-260 : 524 Hz
      * 4U 1608-52 : 620 Hz
  * h (= 2 R_NS/r_ph) : Uniform(0.0, 2.0)
    * R_NS : a radius of a neutron star
    * r_ph : a photosphere radius 
  * Distance, D : Gaussian distribution based on indepedent observations
    * for EXO 1745-248, KS 1731-260, the distance prior is flat due to the observation uncertainties.

* Posterior samples
  * Among 2*10^6 MCMC samples, 19800 independent samples for each source are collected to avoid the correlation between neighbor samples during MCMC steps.
  * column names
    * radius [km] , mass [Msun], x (hydrogen mass fraction) [non-dim.], fc (color-correction factor) [non-dim.], fns (NS spin frequency) [Hz], h (= 2 R_NS/r_ph) [non-dim.], distance [kpc]
    * The spin frequencies (fns) of 3 sources (SAX J1748.9-2021, KS 1731-260, 4U 1608-52) were measured by independent observations. In those cases, "fns" was fixed, and "fns" was not included in posterior samples. See the above priors.


* See, https://arxiv.org/abs/2104.00263 for details.
* Please acknolowedge our publication (https://arxiv.org/abs/2104.00263) or specify it in the reference list of your publications if you use the posteiror samples in this repository.
