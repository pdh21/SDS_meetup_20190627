### Data Science:
* *Extracting information from Data*<!-- .element: class="fragment" -->
* *Using information to make predictions, decisions etc*<!-- .element: class="fragment" -->

Note:
* Breaking down data science into basic principle, it is about...
* Depending on project, we use that information for different things, e.g. in a recommendation engine, we predict what a customer might like to buy, decide what stocks to buy based on predicted performance


![](Slides/assets/uncertainty_example.png?raw=true)<!-- .element height="55%" width="55%" --><!-- .element: class="fragment" -->
* You don't want to just know prediction<!-- .element: class="fragment" -->
* You want to know how certain you are about that prediction<!-- .element: class="fragment" -->
* Uncertainty is information<!-- .element: class="fragment" -->

Note:
* what information is in the data.. and how are we using it?
* Two stocks, and their predicted price in a years time. Who would go for orange stock, who would go for blue?
* Most of you choose blue. Why? Because according to the distribution, there is a chance the stock price could be quite high.
* You have used the shape of the distribution to make that decision. If you were to use the most likely value, the two are the same
* Using point statistics such as the maximum likelihood are often used to give prediction


### Probabilistic modelling
* Models that incorporate random variables and probability distributions<!-- .element: class="fragment" -->
* Random variables represent the potential outcomes of an uncertain event<!-- .element: class="fragment" -->
* Probability distributions assign probabilities to the potential outcomes<!-- .element: class="fragment" -->

Note:
A natural way to make the most use of and take into account uncertainty, is to use probabilistic modelling
* parameters in a model become random variables
* probability distributions can also be used as inputs
* probabilistic modelling and Bayesian probability talked about together as a natural match
* We often use Bayesian methods to infer parameters and make predictions from our probabilistic models 


* Realistic decision making necessitates recognising uncertainty<!-- .element: class="fragment" -->
* By incorporating uncertainty, we can measure the uncertainty associated with outputs<!-- .element: class="fragment" -->
* Incorporating uncertainty leads to better decisions<!-- .element: class="fragment" -->

Note:
* both in the inputs and outputs, just as quantifying the risk in a business process
* incorporating uncertainty in models, measure uncertainty in outputs such as predictions
* shown with example in stocks
