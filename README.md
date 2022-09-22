# Astronomy_projects

A compilation of all my small projects in Astronomy.

## 1. Colours in Astronomy

> Vega is estimated to have surface temperatures of around 9,500C (17,000F), which is almost as twice as hot as the sun

*Ever wondered how we estimate the temperatures of stars? You might guess - wavelengths of the light emitted by those stars, or in other words, **color**.*

*Now how do we tell which star is bluer or redder than another? We can't exactly look at the stars. Do we need to measure the wavelength of the light from each and every star? Or is it sufficient to measure it for one star? (Hint: Yes)*

What this project explores:

- what is the meaning of colour in the astronomical sense and how do we simultaneously estimate the colors of thousands of stars in the night sky
- how we can translate this color into the steller temperatures

## 2. Galaxy Eccentricity Estimation
### Using 2D Fourier Transform

> Galaxies are classified into three main categories- Elliptical, Spiral and Irregular

*Unfortunately, the way to tell which of these three categories a galaxy falls into is msotly told by looking at it. Thats why the SDSS (Sloan Digital Sky Survey) started its [galaxy zoo project](https://www.zooniverse.org/projects/zookeeper/galaxy-zoo/) which is a crowdsourced project for classifying galaxies.*

*Can we use ML to guess the type of galaxy? Yes! But again due to the sheer number of galaxies performing ML on the huge number of pixels in each image takes a lot of power. Thus we can use other factors:*

1. **Colour indices** are the same types of colors we explored in the previous project. Studies of galaxy evolution tell us that spiral galaxies have younger star populations and therefore are 'bluer' (brighter at lower wavelengths). Elliptical galaxies have an older star population and are brighter at higher wavelengths ('redder').

2. **Eccentricity** approximates the shape of the galaxy by fitting an ellipse to its profile. Eccentricity is the ratio of the two axis (semi-major and semi-minor). 

3. **Adaptive moments** are a measured quantity to describe the shape of a galaxy. They are used in image analysis to detect similar objects at different sizes and orientations.

4. **Concentration** is similar to the luminosity profile of the galaxy, which measures what proportion of a galaxy's total light is emitted within what radius[^1] .

Out of these 4, I try to estimate the second parameter- the eccentricity.

How?
- Fit ellipse to images of galaxies by performing edge estimation using 2D Fourier Transform
- Then estimated eccentricity of galaxies by simply fitting an ellipse

## 3. Sunspot Data Forecast

> Elon Musk's SpaceX says a geomagnetic storm wiped out 40 of the 49 Starlink satellites it launched into orbit last week[^2]

We don't launch satellites when there is a stormy weather. Similarly we need to check the condition of space weather before launching said satellite.

What is space weather? Simply the effect of the activity of the sun on earth. Magnetic storms which can disrupt the magnetic field of earth and generate ionic particles which cause auroras and also mess up satellite launches.

Similar to how earth weather is predicted, can we predict space weather? Yes. How? The Sun is typically very active when sunspot counts are high. Sunspots are indicators of disturbances in the Sun's magnetic field, which can generate energetic solar events like solar flares and coronal mass ejections. Since reasonably reliable records of sunspot counts extend back to the early 1700s, long before other measures of solar activity could be observed, sunspot counts serve as a valuable, relatively long-term indicator of solar activity[^3].

- Thus in this project we use ARIMA or **A**uto**r**egressive **I**ntegrated **M**oving **A**verage to try and predict the next solar cycle.

[^1]: Features important for classification of galaxies: https://www.coursera.org/learn/data-driven-astronomy
[^2]: ttps://www.businessinsider.com/spacex-lost-starlink-satellites-orbit-geomagnetic-solar-storm-space-launch-2022-2?r=US&IR=T
[^3]: https://scied.ucar.edu/learning-zone/sun-space-weather/sunspot-cycle
