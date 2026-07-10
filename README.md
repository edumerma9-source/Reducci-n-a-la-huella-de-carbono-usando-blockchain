ECO-CARBON UNMSM
Blockchain Incentive Protocol for University Sustainability
Technical-Economic Report — Universidad Nacional Mayor de San Marcos
1. PROJECT NAME
Eco-Carbon UNMSM: A Blockchain Incentive Protocol for University Sustainability
The project is formally designated Eco-Carbon UNMSM. The name was chosen to explicitly convey the mechanism’s design logic: a direct, on-chain link between a pro-environmental action ("Eco") and a verifiable economic reward ("Carbon," referring to the Carbon Footprint the project seeks to mitigate). As a Web3 institutional identity, Eco-Carbon UNMSM signals to the university community, authorities, and potential partners that the project is not a simple awareness campaign, but an incentive-compatible economic mechanism, implemented as immutable software, consistent with best practices in applied mechanism design and the decentralized provision of public goods.
The project is a direct evolution of the original report "Reducing the Carbon Footprint by Promoting Sustainable Habits in the University Community," prepared by Group G5 of UNMSM, transforming a qualitative awareness proposal into a verifiable, technically rigorous economic protocol.
2. TEAM MEMBERS AND ROLES
Group — Universidad Nacional Mayor de San Marcos (UNMSM). The team divided its responsibilities according to a principle of comparative advantage, minimizing internal coordination costs and maximizing joint output — a direct application of the specialization principle from the microeconomic theory of the firm.
●  Edu Adelky Merma Uñapillco
Role: Project Lead & General Coordination
Responsibilities:
Plan and coordinate the team’s activities.
Oversee fulfillment of the project’s objectives.
Organize task distribution among team members.
Review the final report before submission.
●  Jair Antony Fredy Chipana Coarita
Role: Lead Researcher
Responsibilities:
Gather scientific and bibliographic information on the carbon footprint.
Analyze the main causes and consequences of climate change.
Select reliable sources for the report.
●  Godfrey Torres Huacho
Role: Writing & Documentation
Responsibilities:
Draft and organize the report’s content.
Review the document’s coherence, spelling, and structure.
Adapt the gathered information into academic language.
●  Tony Alexander Herrada Callirgos
Role: Design & Presentation
Responsibilities:
Design the project presentation.
Produce supporting charts, tables, and images.
Organize the visual content for the presentation.
●  Yordi Yulino Cainicela Pérez
Role: Evaluation & Improvement Proposals
Responsibilities:
Analyze strategies to reduce the carbon footprint.
Formulate sustainable recommendations and proposals.
Participate in the final review and preparation of the project presentation.
3. PROBLEM DESCRIPTION
The Challenge: The Recycling Market Failure in Peru
Peru faces a structural crisis in solid waste management. According to the Ministry of Environment (MINAM), the country generated 8,994,762.54 tonnes of municipal solid waste in 2024, of which only 249,407.25 tonnes (2.7%) were formally recovered through recycling or composting (MINAM, as cited in RCR Perú, 2026). It is important to note that this figure differs from the 63.25% of waste that MINAM itself reports as "adequately managed" — that is, disposed of in sanitary landfills or engineered cells — which shows that controlled disposal has improved, but effective recovery (actual material recycling) remains marginal (MINAM, 2025).
Waste generation, moreover, continues to trend steadily upward: between 2014 and 2023 it rose from 6.90 to 8.71 million tonnes per year, a 26.1% increase, driven by population growth, urbanization, and consumption of goods with increasingly short life cycles (CEPLAN, 2025). This inefficiency is replicated in academic settings, where solid waste management represents a critical source of Scope 3 emissions (indirect emissions from the value chain and final disposal).
From an applied economics standpoint, we find that this shortfall is not a problem of a lack of values, but a rational response to unresolved market failures.
Pigou’s Negative Externalities (1920)
Informal disposal on campus generates a negative externality in which the private cost of "throwing away trash" is nearly zero, while the social cost (pollution, health risks, and carbon footprint) is high. The Eco-Carbon protocol acts as a digital Pigouvian subsidy, assigning a positive value to recycling to balance the private cost with the optimal social benefit.
Coase’s Transaction Costs (1960)
Source segregation imposes an opportunity cost in time and effort on the student. If this transaction cost exceeds the perceived benefit, the recycling equilibrium will be zero. Our architecture reduces this friction through a simplified Web3 interface, compensating the user’s effort immediately and tangibly.
Akerlof’s Information Asymmetry (1970)
Recycling suffers from the "market for lemons" phenomenon: citizens distrust the final destination of their waste, and the university does not know the actual supply of material across its faculties. Blockchain eliminates this asymmetry by providing an immutable "proof of recycling" that links the generator with the collector without opaque intermediaries.
Table 1: Dimensions of the Market Failure
Market Dimension
Current Inefficient Status
Economic Impact
Externalities
Unregulated disposal in landfills; 1,800 informal dumpsites identified by OEFA-MINAM.
High social costs, degradation of ~146 hectares, and environmental risks.
Transaction Costs
High opportunity cost (time/effort) for citizens who sort waste.
Formal recovery rate of only 2.7% versus 8.99M tonnes generated (2024).
Information Asymmetry
Lack of clear data on material supply and the final destination of waste.
Stagnation and structural inefficiency in the circular economy.

Figure 1
Effective recovery rate of municipal solid waste in Peru (2024). Source: MINAM, cited in RCR Perú (2026).

Source: Ministry of Environment (MINAM), cited in RCR Perú (2026).
4. SOLUTION SUMMARY
Eco-Carbon UNMSM addresses the structural failure of the recycling market through an EVM-compatible Smart Contract deployed on the LNet network (formerly LACNet), which automatically mints and assigns Eco-Credits to students’ wallets once a recycling action is verified. By encoding the reward mechanism directly into transparent, immutable code, the protocol reduces the transaction and monitoring costs identified in Section 3 to nearly zero. At the same time, the auditable on-chain record of recycling activity closes the information gap between students and the university, functioning as a self-executing Pigouvian subsidy that internalizes the positive externality of recycling without requiring costly centralized administration.
Operational Flow
Source Segregation: students sort material at the source, eliminating the centralized transaction cost of mass classification.
Cryptographic Validation: the university operator (acting as an oracle) weighs the material and records the data on the LNet node, linking physical reality to the digital ledger.
On-chain Issuance (Minting): the contract automatically mints ECO tokens in the user’s wallet (MetaMask). The Eco Dashboard lets students see their direct contribution to reducing the institution’s carbon footprint.
5. TECHNOLOGIES USED
Blockchain Architecture & Smart Contract
Technology
Role in the Project
Microeconomic / Technical Justification
Solidity 0.8.20 & EVM
Smart Contract Core
Guarantees immutability and transparency, eliminating third-party auditing costs associated with compliance monitoring.
Red LNet (Testnet)
Blockchain Infrastructure
Low-cost node participation lowers entry barriers and initial fixed costs for the university.
Remix IDE
Development Environment
Minimizes R&D time by reducing deployment friction during iterative testing.
MetaMask
Decentralized Wallet
Standardizes user interaction, lowering adoption costs (entry barriers) for students.

Gas Optimization: O(1) Complexity
A critical architectural pillar is gas optimization with O(1) complexity. In a community the size of UNMSM (tens of thousands of students), using iterable arrays would cause the transaction cost to grow linearly (O(n)), eventually exceeding LNet’s per-block limits. We therefore implement a structure based strictly on mappings, ensuring that the cost of recording an action remains constant regardless of the number of users.
Figure 2
Conceptual comparison of gas cost: iterable arrays (O(n)) versus mappings (O(1)) as the user community grows.

Conceptual illustration of algorithmic complexity; not derived from actual gas measurements.
Registration and Burning Logic
The registerRecycling function acts as the value-issuance engine, while the redemption function incorporates "burning" logic, removing Eco-Credits from circulation once the benefit (discount or service) has been claimed on the EcoMarketplace.
// Recycling registration function - Eco-Carbon
function registerRecycling(
    address citizen,
    uint256 kg
) external onlyOwner {
    require(kg > 0, "Invalid input");
    uint256 pts = kg * RATE; // Conversion based on the set rate
    balances[citizen] += pts; // On-chain registration with O(1) complexity
    emit RecyclingVerified(citizen, kg, pts);
}
6. REFERENCE CASES AND INTERNATIONAL PRECEDENTS
The use of blockchain to incentivize recycling is not an isolated proposal: working international precedents exist that support the technical and social viability of the model proposed by Eco-Carbon UNMSM.
Project
Country / Region
Mechanism
RECICLOS (Ecoembes / CircularChain)
Spain (Catalonia and other regions)
Non-fungible tokens (ERC-721) issued for container deposits, redeemable for discounts and raffles; active in more than 20 municipalities.
Plastic Bank
Haiti, Philippines, Indonesia, Brazil
Blockchain rewards for collected plastic, redeemable for goods and services (healthcare, education, fuel).
Proyecto Colmena (JellyCoin)
Argentina (Campo Viera, Misiones)
Local cryptocurrency issued as an incentive for household waste recycling, currently in pilot phase.

These cases demonstrate that tokenizing environmental incentives operates effectively at municipal and community scale, validating Eco-Carbon UNMSM’s central hypothesis: that a verifiable on-chain economic mechanism can resolve the recycling market failure more effectively than traditional awareness campaigns, without directly requiring the creation of additional physical infrastructure.
7. PITCH DECK STRUCTURE
The Eco-Carbon UNMSM presentation is organized into 9 slides, following the logical sequence of the economic argument developed in this report.
Cover: Eco-Carbon UNMSM — team, tagline, and the project’s visual identity.
The Problem: the waste-recovery crisis in Peru (Pigou, 1920), with the data of 8.99 million tonnes generated and only 2.7% recovered.
Structural Frictions: why recycling doesn’t happen — transaction costs (Coase) and information asymmetry (Akerlof).
The Solution: Eco-Carbon UNMSM as an on-chain incentive protocol that mints verifiable Eco-Credits.
Technical Rigor: Solidity architecture, O(1) gas optimization, and token issuance/burning logic.
Frontend & User Experience: MetaMask authentication and the Eco Dashboard for registration and tracking.
Impact & Scalability: marginal cost trending to zero (MC → 0) and signaling theory (Spence, 1973).
Strategic Roadmap: three-phase projection following the project’s completion.
Open Source & Public Good: repository, demo video, and closing call to action.
8. GITHUB REPOSITORY LINK
Public repository, to be shared with the teaching staff / organizers: [to be completed by the team]
Repository Contents
/contracts: EcoCarbon.sol — Solidity smart contract implementing recycling registration, Eco-Credit issuance, and burning logic.
/frontend: Web3 interface for the Eco Dashboard, with MetaMask integration.
/presentation: EcoCarbon_UNMSM_Pitch_Deck.pdf — official project presentation.
README.md: Project overview and technical documentation.
LICENSE: Open-source license (MIT).
9. FUNCTIONAL VIDEO DEMO LINK
Link to the protocol’s functional demo video: [to be completed by the team]
10. IMPACT AND SCALABILITY JUSTIFICATION
Spence’s Signaling Theory (1973)
The accumulation of Eco-Credits in a public wallet functions as a credible "green signal." Unlike statements of intent, the immutable record on LNet lets students signal their pro-environmental behavior to employers (ESG) or to the university itself to access preferential benefits, solving the problem of costly signaling.
Marginal Cost Trending to Zero (MC → 0)
LNet’s distributed infrastructure means that, once the protocol is deployed, the cost of adding an additional user is virtually nil. This ensures the project can scale from a pilot faculty to the entirety of UNMSM and other regional campuses without requiring proportional increases in physical oversight infrastructure.
Positive Network Effects: the protocol’s value grows exponentially with participation. The greater the volume of on-chain data, the greater UNMSM’s capacity to monetize carbon credits and attract merchants to the ecosystem, increasing the real value of each ECO token.
11. ALIGNMENT WITH THE SUSTAINABLE DEVELOPMENT GOALS (SDGs)
The Eco-Carbon UNMSM protocol is designed to directly contribute to three Sustainable Development Goals of the United Nations 2030 Agenda (UN, 2023):
SDG 11 — Sustainable Cities and Communities: by strengthening solid waste management within the university campus through a verifiable traceability system.
SDG 12 — Responsible Consumption and Production: by economically incentivizing source segregation and the recovery of recyclable materials.
SDG 13 — Climate Action: by reducing Scope 3 emissions associated with final waste disposal and contributing to the mitigation of the institution’s carbon footprint.
12. IMPLEMENTATION ROADMAP
Figure 3
Post-development implementation timeline for the Eco-Carbon UNMSM protocol.

Phase 1: Technical Rigor and Security (Q3 2026)
Comprehensive audit of the smart contracts and penetration testing to ensure asset integrity. An additional 15% optimization in gas usage to maximize concurrency on LNet.
Phase 2: Market Validation (Q4 2026)
Pilot launch at UNMSM’s Ciudad Universitaria. Goal: 500 active users and 2 tonnes of material processed, validating the reduction in the campus’s carbon footprint.
Phase 3: Scaling and Commercial Network (Q1 2027)
Integration of APIs for redeeming tokens at local businesses and expansion of the protocol to external faculties and partner municipalities, consolidating a regional public good.


13. CONCLUSIONS
Blockchain technology resolves the information asymmetry by offering full traceability of environmental impact, turning recycling into an auditable reputation signal.
The Eco-Credits model reduces transaction costs through direct compensation for opportunity cost, encouraging compliance with the socially optimal level of recycling.
The architecture built on LNet enables scalability with marginal cost trending to zero, positioning UNMSM as a leader in applying Web3 to the circular economy.
International precedents (RECICLOS, Plastic Bank, Proyecto Colmena) validate the viability of tokenization mechanisms applied to recycling at community and institutional scale.
14. REFERENCES
Akerlof, G. A. (1970). The market for “lemons”: Quality uncertainty and the market mechanism. The Quarterly Journal of Economics, 84(3), 488–500.
Centro Nacional de Planeamiento Estratégico (CEPLAN). (2025). Incremento de los residuos sólidos. Observatorio Nacional de Prospectiva. https://observatorio.ceplan.gob.pe/ficha/ts_2_amb
Coase, R. H. (1960). The problem of social cost. Journal of Law and Economics, 3, 1–44.
IDB Lab & LACNet. (2025). LACChain and LACNet are now LNet, a global platform for trusted digital innovation.
Ministerio del Ambiente del Perú (MINAM). (2025). Municipios reportan incremento en valorización de residuos sólidos durante 2024. https://www.gob.pe/institucion/minam/noticias/1205034
Organización de las Naciones Unidas (ONU). (2023). Objetivos de Desarrollo Sostenible. https://sdgs.un.org/es/goals
Pigou, A. C. (1920). The economics of welfare. Macmillan.
RCR Perú. (2026, 16 de mayo). Día mundial del reciclaje: Perú solo recicla el 2.7% de sus residuos pese a que genera casi 9 millones de toneladas, advierte el Minam. https://www.rcrperu.com/
Red de Centros de Innovación y Desarrollo Económico (REDCIDE). (2024). tokenMYs: proyecto piloto de reciclaje con tecnología blockchain. https://www.redcide.es/
Spence, M. (1973). Job market signaling. The Quarterly Journal of Economics, 87(3), 355–374.
Universidad Católica de Chile, Ingeniería UC Educación Profesional. (2020). Tecnología blockchain para combatir el cambio climático. https://educacionprofesional.ing.uc.cl/
Alastria Blockchain Ecosystem. (2023). Tokenización — Incentivos de reciclaje: RECICLOS. https://alastria.io/tokenizacion-incentivos-reciclaje/
