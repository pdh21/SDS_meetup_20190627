### Using the model to make better decisions
* A farmer living in East Sussex<!-- .element: class="fragment" -->
* They have 100 cows and 100 hectares of land<!-- .element: class="fragment" -->
* Cows need feed (hay) over winter<!-- .element: class="fragment" -->
* Can use fields to grow hay to feed the cattle<!-- .element: class="fragment" -->
* Can buy hay from a supplier<!-- .element: class="fragment" -->

Note:
Show how model could be used in agritech sector
* an example problem
* show the affect of taking into account uncertainty in weather


### BUT...
* Buying in hay is expensive<!-- .element: class="fragment" -->
* Grow too little, farmer has to buy more hay in, loses money<!-- .element: class="fragment" -->
* It costs money to grow hay<!-- .element: class="fragment" -->
* Costs more to grow then get back selling<!-- .element: class="fragment" -->

Note:
* want to avoid buying in hay
* need to decide how much to grow, but weather affects growth and so is variable
* farmer grow lots to cover poor yield. BUT costs money. sell remainder
 but it often costs more to grow then get back selling unless growing at massive scale 


### What area should the farmer use to grow Hay?
A traditional approach<!-- .element: class="fragment" -->

Note:
* farmer has to make a balanced decision
* use the FACYnation as a mathematical model and ignore uncertainty in weather
* use the FACYNation as a probabilistic model take into account uncertainty


### Weather data
Met Office archival data for Eastbourne
![](Slides/assets/weather_mrk_i.png?raw=true)<!-- .element height="80%" width="80%" -->

Note:
* use mean value for each month


### Use Weather to predict yield
![](Slides/assets/model.png?raw=true)<!-- .element height="80%" width="80%" -->

= Annual crop of 7.13 tonnes/ha.<!-- .element: class="fragment" -->

Note:
* Feed in mean values to model.
* Know yield per area, need to know what area


### Construct a loss function
Define the quantitative cost of what happens if:
 * the farmer does not grow enough hay<!-- .element: class="fragment" -->
 * the farmer grows too much<!-- .element: class="fragment" -->


* *GROWTH_PRICE*: How much money, per ha. that it costs to grow hay
* *SALES_PRICE*: How much money the farmer will make for surplus hay
* *BUY_PRICE*: How much it costs to buy hay 
* *FEED*: How much total feed is required for the herd

Note:
need to include what will impact the cost
* e.g. seed cost, tractor fuel, harvesting etc


![](Slides/assets/lossfunction.png?raw=true)<!-- .element height="77%" width="77%" -->

Farmer should use 14 ha. of land to grow hay!<!-- .element: class="fragment" -->

Note:
Function of field size
Loss function shows we get penalised more for not growing enough, than if we were to grow too much.
Buy price.. margin:growth price - sales price
Minimise loss. look for minima:



### What area should the farmer use to grow Hay? II
A probabilistic modelling approach

* Incorporate uncertainty on weather
* Random variables for parameters
* Probability distributions on inputs and outputs

Note:
Now lets re approach this problem using a probabilistic approach.
Doing this to incorporate uncertainty on weather
turn into probabilistic model by:


<!-- .slide: data-transition="slide in fade out" -->
### Weather data II
![](Slides/assets/weather_mrk_i.png?raw=true)<!-- .element height="80%" width="80%" -->

Note:
Know variation in temperature and precipitation has big effect on growth of hay.
We should be taking it into account in our model.


<!-- .slide: data-transition="fade in slide out" -->
### Weather data II
![](Slides/assets/weather_mrk_ii.png?raw=true)<!-- .element height="80%" width="80%" -->

Note:
We will therefore use the mean and standard deviation for temperature and precipitation 
for each month and model the variation with a Normal distribution.


### Use Weather to predict yield II
![](Slides/assets/posterior_yield.png?raw=true)<!-- .element height="80%" width="80%" -->

Note:
Because using probabilistic model, output is now a probability distribution.
Shows uncertainty of getting a particular yield. Coming from variability in weather
Compare to value from before


### Apply Loss function to posterior 
![](Slides/assets/lossfunction_mrk_ii.png?raw=true)<!-- .element height="75%" width="75%" -->

Farmer should use 18.6 ha of land to grow hay!!<!-- .element: class="fragment" -->

Note:
Get a probability of loss for given field area, take average value..
By using the full probability distribution for yield, it has taken into account how likely the different yields are and the cost implications
before taking decision.
Broadening of mean loss comes from taking into account probability


### There is a difference...So what? 

Lets investigate impact of the two field size choices:
* Use monthly weather data to calculate actual yield/hectare (we assume model is correct)<!-- .element: class="fragment" -->
* Calculate total yield, given the amount of land used to grow hay<!-- .element: class="fragment" -->
* Calculate the loss for each year<!-- .element: class="fragment" -->

Note:
* Assume model is accurate in calculating yield, and use historic weather to calculate yield we would have actually got. If a real problem, we could
use actual yield
* we have losses from 1958 up to 2018


![](Slides/assets/distribution_of_losses.png?raw=true)<!-- .element height="80%" width="80%" -->

<span>An average difference of &#163;436 per year</span><!-- .element: class="fragment" -->

Note:
* average loss per year is less
* Also, range of losses is less. Easier for farmer to plan financially


![](Slides/assets/cum_loss.png?raw=true)<!-- .element height="80%" width="80%" -->

<span>A cumulative difference of &#163;26170</span> </span><!-- .element: class="fragment" -->

Note:
Add up the cost for each year, farmer ends up loosing a lot more money


## Summing up
* Probabilistic modelling is a useful approach for Data Scientists to have in their toolkit<!-- .element: class="fragment" -->
* Uncertainty is information. Ignore at your peril!<!-- .element: class="fragment" -->
* Incorporating uncertainty can lead to better decisions for clients<!-- .element: class="fragment" -->

Talk and blog post available at<!-- .element: class="fragment" -->
http://pdh21.github.io<!-- .element: class="fragment" -->

Note:
* Not always appropriate, it can be hard. 
BUT advantages of being able to use domain expertise to work alongside data through probability distributions,
interpretable e.g. probability on how much hay could rot
* Known unknowns.. variability has consequences, if we can model and use that variability we can understand and mitagate those consequences
* there to provide a service, incorporating uncertainty in our models can lead to better decisions and so provides a better service
