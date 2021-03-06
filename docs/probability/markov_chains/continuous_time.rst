Continuous-Time
===============
A continuous-time Markov chain :math:`(X_t)_{t \geq 0}` is defined by a finite or countable state space :math:`S`.

**Transition rate matrix** :math:`Q` with dimensions equal to that of the state space and initial probability distribution defined on the state space

**Rate of the process transitions** from state :math:`i` to :math:`j` is described by the elements of matrix :math:`Q`

.. math::

   Q(i, j) > 0, \quad i \neq j

The elements are chosen such that each row of the transition rate matrix sums to zero.

.. math::

   \sum_{j \in S} Q(i, j) = 0


Definitions
-----------

Jump Chain / Holding Time
^^^^^^^^^^^^^^^^^^^^^^^^^
Define a discrete-time Markov chain :math:`Y_n` to describe the :math:`n` th jump of the process and variables

.. math::

   S_1, S_2, S_3, \ldots

to describe holding times in each of the states where :math:`S_i` follows the exponential distribution with rate parameter :math:`\lambda = -Q(Y_i, Y_j)`

.. math::

   S_i \sim \operatorname{Exp}(\lambda).


Transition Probability
^^^^^^^^^^^^^^^^^^^^^^
For any value :math:`n = 0, 1, 2, \ldots` and times indexed up to this value of :math:`t_0, t_1, t_2, \ldots` and all states recorded at these times :math:`i_0, i_1, i_2, \ldots` it holds that

.. math::

   \Pr(X_{t_{n+1}} = i_{n+1} | X_{t_0} = i_0 , X_{t_1} = i_1 , \ldots, X_{t_n} = i_n ) = p_{i_n i_{n+1}}( t_{n+1} - t_n)

where :math:`p_{ij}` is the solution of the forward equation (a first-order differential equation)

.. math::

   \begin{cases}
   P'(t) = P(t) Q \\
   P(0) = \mathbf{I}
   \end{cases}


Stationary Distribution
-----------------------
In vector form

.. math::
   \boldsymbol{\pi} = \boldsymbol{\pi} P

and

.. math::
   \sum_{i \in S} \boldsymbol{\pi}(i) = 1 \\
   \boldsymbol{\pi} Q = 0

Expected Number of Visits
-------------------------

.. math::

   M_t(i, j) = \int_{0}^{t}P_s(i, j)d\,ds


Expected Number of Hits
-----------------------

.. math::
   g_n(i) = \sum_{j \in S} M_{n} (i, j) c(j)

In vector form

.. math::
   g_{n} = M_{n} c

where :math:`c(i)` is the cost of hitting node :math:`i`

