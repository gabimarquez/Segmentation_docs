.. role:: raw-html(raw)
   :format: html

Multi-Touch Attribution with First-Order Markov Chains
=======================================================
This is an implementation of a first-order Markov chain model in multi-touch attribution settings. The relative importance of a channel in customer journey analysis, i.e., its attribution, is measured by its contribution to converting customers. This notebook will provide (an optimized) code for evaluating channel attribution using first-order Markov chains based on a sample data set which may not represent real-world situations. The notebook below will walk through data requirements and processes, Markov chains definitions, and how to calculate transition probabilities and attributions as well as QA checks and visualizations.

Project folder: `Git repo <https://github.com/BLEND360/measurement-library/tree/master/content/Customer%20Journey%20Analytics/Methodologies/Markov%20Chains>`_
:raw-html:`<br />`
Contacts: `Peter Manders <peter.manders@Blend360.com>`_, `Amir Nasr <amir.nasrollahzadeh@blend360.com>`_, `Mo Afkhami <mo.afkhami@blend360.com>`_

.. toctree::
    :maxdepth: 5

    MTA_Markov chains_First-order

Order Estimation of Markov Chains
==================================
Although the Markovian property dictates memorylessness of transitions between different states, transition probabilities may still depend on previous steps of a Markov journey if state definitions are modified a little bit. In this setting, each state contains a history of previous steps in the chain while allowing the probabilities to still follow the Markovian rule of being independent of previous steps. How much history is stored in each state variable is a function of the order of Markov chain. While generally higher orders result in more accuracy, the exponential growth of the state space introduces the curse of dimensionality. This notebook implements a methodological approach in choosing the right order.

Project folder: `Git repo <https://github.com/BLEND360/measurement-library/tree/master/content/Customer%20Journey%20Analytics/Methodologies/Markov%20Chains>`_
:raw-html:`<br />`
Contacts: `Federico Schiaffino <Federico.Schiaffino@Blend360.com>`_, `Peter Manders <peter.manders@Blend360.com>`_, `Amir Nasr <amir.nasrollahzadeh@blend360.com>`_

.. toctree::
    :maxdepth: 5

    MTA_Markov chains_Higher-orders

Additional Insights & Analyses with Markov Chains
==================================================
Channel attribution is not the only analysis made available by Markov chain models. This notebook explores different analyses and insights about customer journeys in a multi-touch attribution settings. These analyses include **hitting times** which show the number of expected steps from each channel before conversion or loss, **absorbing probabilities** show the expected probability of being converted or lost from each channel, **most probable paths** which identify the most effective sequences of channels in customer conversions, and different **Sankey diagrams** which visualize transition probability matrix and provide insights on how traffic flows between different channels. In addition, in the **aggregating Markov states** section, an algebraic method to aggregate different Markov states into a single state is implemented. Using this method, one can reduce model's dimension for visualization or attribution purposes without retraining the Markov chain model.

Project folder: `Git repo <https://github.com/BLEND360/measurement-library/tree/master/content/Customer%20Journey%20Analytics/Methodologies/Markov%20Chains>`_
:raw-html:`<br />`
Contact: `Amir Nasr <amir.nasrollahzadeh@blend360.com>`_

.. toctree::
    :maxdepth: 5

    MTA_Markov chains_insights & analyses

Under-sampling in Training Markov Chains
==========================================
In case of tall data with unbalanced classes, e.g., a huge portion of customer journeys do not convert, the majority class can be under-sampled in order to speed up Markov chain training. This is extremely useful in cases millions of customer journeys have to be iterated over for a huge combination of possible channel transitions. An efficient method based on partitioning frequency matrices of converted vs. non-converted customers is developed in this project. The transition probability matrices of the original Markov chain is compared against the under-sampling method to show the accuracy of estimation.

Project folder: `Git repo <https://github.com/BLEND360/measurement-library/tree/master/content/Customer%20Journey%20Analytics/Methodologies/Markov%20Chains>`_
:raw-html:`<br />`
Contacts: `Serhat Kecici <serhat.kecici@blend360.com>`_, `Amir Nasr <amir.nasrollahzadeh@blend360.com>`_

.. toctree::
    :maxdepth: 5

    MTA_Markov chains_undersampling

Multi-Touch Attribution with Markov Chains Considering Number of Touches
==========================================================================
A first-order Markov chain does not consider customer's previous touches in evaluating transition probabilities from one channel to another. Therefore, customers journeys are modeled by transitions that do not depend on customer's behavior. One way to improve and relax this assumption is to augment the state space of the Markov chain with an additional variable that records each customer's number of touches as the customer moves from one channel to the next. As a result, transition probabilities for each customer will depend on where that customer is along their journey. Moreover, attributions will be evaluated for different journey lengths as attribution of channel for the first click will be different from its attribution later in the journey. To compare performance, aggregated attributions along different journey lengths are compared with first-order Markov chain attribution. The following notebook implements the augmented Markov chain model, calculates attribution, and provides additional insights possible by the additional information in each state.

Project folder: `Git repo <https://github.com/BLEND360/measurement-library/tree/master/content/Customer%20Journey%20Analytics/Methodologies/Markov%20Chains>`_
:raw-html:`<br />`
Contacts: `Amir Nasr <amir.nasrollahzadeh@blend360.com>`_

.. toctree::
    :maxdepth: 5

    MTA_Markov chains_Number of touch

Simulation of Transition Probability Matrix by Method of Perturbation
=======================================================================
Perturbing transition probabilities of a Markov chain can simulate the effects of investment on a paid channel in terms of overall conversion. Within this framework, transition probabilities of a particular channel are increased according to some scenario, the transition probability matrix is then perturbed to digest the effects, and the change in conversion is calculated. Simulating different scenarios for paid channels can estimate a channel's potential for investment as the channel which results in more conversion will have the most potential.

Project folder: `Git repo <https://github.com/BLEND360/measurement-library/tree/master/content/Customer%20Journey%20Analytics/Methodologies/Markov%20Chains>`_
:raw-html:`<br />`
Contacts: `Amir Nasr <amir.nasrollahzadeh@blend360.com>`_

.. toctree::
    :maxdepth: 5

    MTA_Markov chains_Simulation by perturbation
