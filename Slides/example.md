## FACYNation
* Project with the University of Sussex and the Met. Office
* Develop model to predict how climate change affects crop yields
* Shirley et al. (submitted)

Note:
​​Forecasting Agricultural Crop Yields at National scales
model climate-yield relationships 
and provide accurate real-time yield forecasts and likely climate change impacts


<!-- .slide: data-transition="slide in fade out" -->
## The model
![](Slides/assets/model_inf.png?raw=true)<!-- .element height="85%" width="85%" -->

Note: 
Takes in mean monthly temperature and total monthly precipitation, learns how they affect final yield..


<!-- .slide: data-transition="fade in slide out" -->
## The model
![](Slides/assets/model.png?raw=true)<!-- .element height="80%" width="80%" -->

Note: Lets use learnt model to predict yield from weather


### Details of model
![](Slides/assets/model_eq.png?raw=true)<!-- .element height="50%" width="50%" -->![](Slides/assets/2Dgrowthfunction.png?raw=true)<!-- .element height="40%" width="40%" -->




### Using the model to make better decisions
* A farmer living in East Sussex<!-- .element: class="fragment" -->
* They have 100 cows and 100 hectares of land<!-- .element: class="fragment" -->
* Cows need feed (hay) over winter<!-- .element: class="fragment" -->
* Can use fields to grow hay to feed the cattle<!-- .element: class="fragment" -->
* Can buy hay from a supplier<!-- .element: class="fragment" -->


### BUT...
* Buying in hay tends to be more expensive<!-- .element: class="fragment" -->
* It costs money to grow hay (less than buying)<!-- .element: class="fragment" -->
* Grow too little, farmer has to buy more hay in, loses money<!-- .element: class="fragment" -->

Note:
* Farmer does not want to grow too much. Could sell remainder but it costs more to grow then get back selling: farmer will lose money.


### What area should the farmer use to grow Hay?
A traditional approach<!-- .element: class="fragment" -->

Note:
One where use the FACYnation as a mathematical model and feed it deterministic (fixed values)


### Weather data
Met Office archival data for Eastbourne
![](Slides/assets/weather_mrk_i.png?raw=true)<!-- .element height="80%" width="80%" -->


### Use Weather to predict yield
![](Slides/assets/model.png?raw=true)<!-- .element height="80%" width="80%" -->

= Annual crop of 7.13 tonnes/ha.<!-- .element: class="fragment" -->


### Construct a loss function
Define the quantitative cost of what happens if:
 * the farmer does not grow enough hay<!-- .element: class="fragment" -->
 * the farmer grows too much<!-- .element: class="fragment" -->
 
Note: 
* GROWTH_PRICE: How much money, per hecatare, that it costs to grow hay e.g. seed cost, tractor fuel, harvesting etc
* SALES_PRICE: How much money the farmer will make for surplus hay, per tonne
* BUY_PRICE: How much it costs to buy hay 
* FEED: How much total feed is required for the herd
* MAX_FIELD_SIZE: The maximum area the farmer has for growing hay


![](Slides/assets/lossfunction.png?raw=true)<!-- .element height="77%" width="77%" -->

Farmer should use 14 ha. of land to grow hay!<!-- .element: class="fragment" -->



### What area should the farmer use to grow Hay? II
A probabilistic modelling approach

* Incorporate uncertainty on weather
* Random variables for parameters
* Probability distributions on inputs and outputs


<!-- .slide: data-transition="slide in fade out" -->
### Weather data II
![](Slides/assets/weather_mrk_i.png?raw=true)<!-- .element height="80%" width="80%" -->

Note:
The variation in temperature and precipitation has a big effect on the growth of hay and
 so we should be taking it into account in our model.
 We will therefore use the mean and standard deviation for temperature and precipitation 
for each month and model the variation with a Normal distribution.


<!-- .slide: data-transition="fade in slide out" -->
### Weather data II
![](Slides/assets/weather_mrk_ii.png?raw=true)<!-- .element height="80%" width="80%" -->


### Use Weather to predict yield II
![](Slides/assets/posterior_yield.png?raw=true)<!-- .element height="80%" width="80%" -->


### Apply Loss function to posterior 
![](Slides/assets/lossfunction_mrk_ii.png?raw=true)<!-- .element height="75%" width="75%" -->

Farmer should use 18.6 ha of land to grow hay!!<!-- .element: class="fragment" -->


### There is a difference...So what? 

Lets investigate impact of the two field size choices:
* Use monthly weather data to calculate actual yield/hectare (we assume model is correct)<!-- .element: class="fragment" -->
* Calculate total yield, given the amount of land used to grow hay<!-- .element: class="fragment" -->
* Calculate the loss for each year<!-- .element: class="fragment" -->


![](Slides/assets/distribution_of_losses.png?raw=true)<!-- .element height="80%" width="80%" -->

<span>An average difference of &#163;436 per year</span><!-- .element: class="fragment" -->


![](Slides/assets/cum_loss.png?raw=true)<!-- .element height="80%" width="80%" -->

<span>A cumulative difference of &#163; 26170</span> </span><!-- .element: class="fragment" -->

Note:
compare the cost/benefit of both decisions for each year


## Summing up
* Probabilistic modelling is a useful approach for Data Scientists to have in their toolkit<!-- .element: class="fragment" -->
* Uncertainty is information. Ignore at your peril!<!-- .element: class="fragment" -->
* Incorporating uncertainty can lead to better decisions<!-- .element: class="fragment" -->

Note:
* Not always appropriate, it can be hard. 
BUT advantages of being able to use domain expertise to work alongside data through probability distributions,
interpretable
* Known unknowns.. variablity has consequences, if we can model and use that variability we can understand and mitagate those consequences
* In the end, as data scientist, we are there to provide a service, incorporating uncertainty in our models can lead to better decisions and so provides a better service
