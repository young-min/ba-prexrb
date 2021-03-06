# Measuring Masses and Radii of Neutron Stars in Low-Mass X-ray Binaries: Effects of Atmospheric Composition and Touchdown Radius
Posterior samples from Bayesian Inference on 6 LMXB sources for the estimation of Masses and Radii of Neutron Stars.

(Not released yet. The public release of the posterior samples will be conducted soon.)

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
    * For EXO 1745-248, KS 1731-260, the distance prior is flat due to the observation uncertainties.
    * For 4U 1820-30, there are 2 independent observations for luminosity distance. In current study, 8.4+/-0.6 kpc (higher value) was used for simplicity without considering double Gaussian distribution. The result with double Gaussian distribution for the luminosity distance will be updated later.

* Posterior samples
  * Among 2*10^6 MCMC samples, 19800 independent samples for each source are collected to avoid the correlation between neighbor samples during MCMC steps.
  * column names
    * radius [km] , mass [Msun], x (hydrogen mass fraction) [non-dim.], fc (color-correction factor) [non-dim.], fns (NS spin frequency) [Hz], h (= 2 R_NS/r_ph) [non-dim.], distance [kpc]
    * For SAX J1748.9-2021, KS 1731-260, 4U 1608-52, "fns" was not included in posterior samples becase the "fns" of 3 sources were measured by independent observations and it was fixed in our estimation. See the above priors.


* See, https://arxiv.org/abs/2104.00263 for details.
* If you use the posterior samples in this repository, Please add our publication (https://arxiv.org/abs/2104.00263) into the reference list in your publications.
