Methodologies
=============

There are various machine learning and statistical models commonly leveraged to allocate proportional credit for a sale to each touchpoint the individual experienced.  Some key challenges that need to be addressed in the methodology include how to account for potentially thousands of different touchpoints, or how to handle sequence effects, or time between touchpoints, etc.​

Markov Chains
---------------

Markov chains introduce the concept of a ‘state’, and then models the likelihood of moving from one state to another state within the state space.  The advantage of this approach is it closely aligns with the concept of customer journeys because we imagine customers progressing from state to state in their journey, where ‘state’ refers to the marketing touchpoints.  Additionally Markov Chains can account for the effect of specific sequences of touchpoints and can better scale to large number of touchpoints than Shapley value.

.. toctree::
  :maxdepth: 1

  Markov Chains/index

Shapley Values
----------------

Shapley value is a game theory based approach designed to fairly distribute gains and cost to several ‘actors’ worked together in coalition for the outcome.  When applied to attribution modeling the ‘actors’ are the marketing touchpoints that are working together to drive the outcome (sale or conversion).  Shapley value is the most commonly adopted approach to attribution, but does have downsides, mainly it doesn’t account for sequence of touchpoints and computational requirements grow exponentially with number of marketing channels/touchpoints.

.. toctree::
  :maxdepth: 1

  Shapley Values/index

Naïve Bayes
------------

Naïve Bayes is a relatively simply technique for constructing classifiers, the approach is simple to understand and can be computed very quickly.  Leveraging Naïve Bayes to assign credit to each point reduces down to calculating the likelihood of response given all possible combinations of touchpoints.  Then the credit for a particular touchpoint is the average response probability where that touch point is present minus the average probability where the touchpoint is absent.  In essence this approach is mimicking a controlled holdout test dynamic applied to historical touchpoints.  While simple to implement Naïve Bayes there are limitations to the approach, largest being assumed independence, which often require modifications to make the approach useful in practice.

Calibration to MMM
-------------------

**Place Holder**. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. At varius vel pharetra vel turpis nunc eget lorem. At urna condimentum mattis pellentesque id. Turpis egestas integer eget aliquet nibh praesent tristique magna. Sed lectus vestibulum mattis ullamcorper velit sed ullamcorper morbi. Sit amet nisl purus in mollis nunc sed id semper. Rhoncus dolor purus non enim praesent elementum facilisis. Consequat nisl vel pretium lectus quam. Ut ornare lectus sit amet est placerat in egestas erat. Amet volutpat consequat mauris nunc congue.
