Coordinating energy management across multiple microgrids presents considerable challenges, especially under the uncertainties of renewable generation and demand. This paper proposes a Lean Multi-Agent Deep Q Network (L-MADQN) framework for optimal day-ahead energy scheduling in networked microgrids (NMGs) comprising electricity retailers (ERs) and microgrids (MGs). The method integrates a multi-agent Deep Q-Network (DQN) architecture with a single-level mathematical program derived from a bilevel formulation. At the upper level, ERs aim to maximize profits and available transfer capacity (ATC), while the lower level minimizes MG operating costs. To ensure technical feasibility during learning, the lower-level problem is reformulated using Karush–Kuhn–Tucker (KKT) conditions, enabling the transformation into a tractable equilibrium-constrained program. The agents learn optimal actions for uncertain parameters while satisfying power flow, ramping, and exchange constraints. The framework was validated on a modified IEEE 30-bus network. The proposed L-MADQN framework outperforms the deterministic, risk-neutral, and risk-averse optimization methods by reducing MG costs, increasing ER profits, and enhancing ATC values, all with low computational overhead.

<img width="4506" height="2181" alt="L-MADRL2-C" src="https://github.com/user-attachments/assets/2dd56039-7c94-4259-b168-cde0fdbbc47d" />


Link to full article online (for the 5 and 14 bus case): https://www.sciencedirect.com/science/article/pii/S0306261926000061?via%3Dihub


