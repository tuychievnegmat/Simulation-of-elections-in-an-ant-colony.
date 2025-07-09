# Simulation-of-elections-in-an-ant-colony.

"Ant Colonies" Simulation Overview
"Ant Colonies" is a political and economic simulation of ant societies. Ten unique factions, each with its own form of government, compete for survival and dominance on a resource-rich map.
The goal of the simulation is to observe how different political systems handle the challenges of resource management, warfare, diplomacy, and internal development. Which form of government will prove most effective: a random lottery, a rigid dictatorship, a stable monarchy, or one of the complex forms of democracy?
1. Fundamentals of Ant and Colony Life
1.1. Ants and Their Characteristics
Each ant is an autonomous unit with its own needs and tasks.
Ant's Resources:
Food and Water: Vital resources that are constantly consumed. If either drops to zero, the ant dies.
Repro (Reproductive Material), Weapon (Weaponry), and Armor: Resources that ants gather and deposit at the base. These are not consumed for personal needs.
Roles:
Worker: The primary labor force. Gathers resources.
Soldier: Fights, defends the colony, and patrols the territory. Consumes resources faster than workers.
Leader: A unique role. Determines the faction's policy. Does not participate in resource gathering.
Tasks: Each ant is assigned a task (e.g., gather_food, defend, patrol), which it performs until it receives a new assignment or an emergency arises (like needing to replenish its food supply).
1.2. Resources on the Map
Five types of resources are scattered across the map for ants to collect:
Orange - Food
Cyan - Water
Magenta - Reproductive Material (to create new ants)
Gray - Weaponry (for offense)
Blue - Armor (for defense)
1.3. Colonies (Bases)
Storage: Each colony has its own storage where ants deposit collected resources.
Reproduction: New ants are born at bases if there is enough Repro material in storage. The cost of a new ant is fixed but can be reduced by a leader's bonus.
Expansion: When a faction reaches a certain threshold of workers, it automatically founds a new colony. This increases the total resource storage capacity but also requires more ants for defense and supply. If the population declines, the faction may abandon one of its colonies.
2. Economy and Development
2.1. Faction Policy
Policy is the primary tool for managing a faction and is set by its leader. It consists of two parts:
Soldier-to-Worker Ratio: The percentage of the population that should be soldiers.
Worker Priorities: How to distribute all workers among the tasks of gathering the five different resources.
How it works: The leader (or parliament) assesses its personal (or collective) resource deficits. If a leader is low on food, it will set a policy focused on intensive food gathering. This policy is then applied to the entire faction, and ants are assigned tasks accordingly.
2.2. Research
When an ant brings more resources to a base than can fit in storage, the surplus is converted into Knowledge.
Knowledge is automatically invested in researching the resources that the faction is actively gathering (according to its current policy).
Each new research level provides a permanent bonus:
Food, Water, Repro, Weapon, Armor: Increases the storage capacity for that resource.
Repro: Also provides a damage bonus to soldiers in combat (symbolizing a "higher quality" offspring).
Weapon and Armor: Factored into combat, giving an advantage to the more technologically advanced faction.
2.3. Leader Bonuses
Upon each election, a new leader randomly generates one of five powerful bonuses for the entire faction:
Supplies: An instant deposit of the most needed resource into storage.
Gathering: Increases the gathering speed of the most needed resource.
Reproduction: Reduces the cost of creating new ants.
Attack: Increases the damage of all soldiers.
Defense: Increases the effectiveness of all soldiers' armor.
3. War and Diplomacy
Declaring War: A faction declares war if its own key resource reserves (food, water) are very low while a potential enemy's are very high. This simulates a war for resources.
Combat System: Soldiers attack enemies within their line of sight. Damage depends on base values, the leader's bonus, and the difference in research levels between the attacker's Weapon and the defender's Armor.
Ending a War:
Annihilation: One of the factions is completely destroyed.
Surrender: If a faction's leader is killed by an enemy, and the faction subsequently loses a significant portion of its population, it surrenders. The victor claims a portion of the loser's resources and population cap.
Change of Leader: If a warring faction elects a new leader, it automatically makes peace with any faction it was attacking. This simulates a shift in foreign policy.
Revolution: If a faction's food and water supplies fall to critically low levels, there is a chance of a revolution. The current government is overthrown, the leader is killed, and the faction randomly adopts a new form of government.
4. Political Systems and Leader Selection
This is the heart of the simulation. Each faction has a unique method for choosing its leader. Elections (if they exist) occur at regular intervals (ELECTION_INTERVAL).
Category 1: Autocracies
Lotocracy
Principle: Randomness.
Election: One worker is randomly selected from the entire population to become the Lotocrat.
Policy: Determined entirely by the personal needs of this randomly chosen ant.
Monarchy (Hereditary)
Principle: Continuity.
Election: Occurs only after the Monarch dies. The new Monarch is chosen from the workers based on who is most "genetically" similar (closest resource stats) to the deceased ruler.
Policy: Extremely stable, as the new leader is nearly a carbon copy of the old one.
Dictatorship
Principle: Might makes right.
Election: After the Dictator dies, the title passes to the strongest soldier (highest combined weapon and armor stats).
Policy: Extremely aggressive. Since the leader is a soldier with a perpetual resource deficit, they always set a policy of maximum resource collection.
Category 2: Majoritarian Representative Systems (elect a single President)
Representative FPTP (First-Past-The-Post)
Principle: Winner takes all.
Election: Each voter casts a single vote for one of five candidates. The candidate with the most votes wins, even if they have less than 50% support.
Policy: Determined by the winner.
Representative IRV (Instant-Runoff Voting)
Principle: Finding a consensus.
Election: Voters rank candidates in order of preference. The weakest candidate is eliminated in each round, and their votes are redistributed until one candidate secures over 50% of the vote.
Policy: Determined by the consensus-based winner.
Representative Score
Principle: The sum of preferences.
Election: Voters give a score to each candidate. The candidate with the highest total score wins.
Policy: Determined by the winner, who is often the "least disliked" candidate overall.
Category 3: Parliamentary Systems (elect a parliament and a Prime Minister)
In these systems, ants form "parties" based on their primary resource need (e.g., the "Food Party," the "Water Party"). Policy is determined not by a single leader but by the "average opinion" of the majority party or the entire parliament.
Representative PR (Proportional Representation, Closed List)
Principle: Parties matter more than individuals.
Election: Voters vote for a party. Parliament seats are distributed proportionally. The party itself decides which of its members fill the seats.
Leader: The Prime Minister is the leader of the largest party.
Representative PR Open (Proportional Representation, Open List)
Principle: Choose a party, and the best person in it.
Election: Similar to PR, but voters also cast a personal vote for a candidate within their chosen party's list. The most popular individuals within the party get the seats.
Leader: The leader of the largest party.
Representative STV (Single Transferable Vote)
Principle: Individuals matter more than parties.
Election: (Simplified) Voters rate all candidates, and the ones with the highest overall scores are elected to parliament, regardless of party.
Leader: The most popular candidate overall becomes Prime Minister.
Representative Mixed
Principle: A balance between parties and individuals.
Election: Voters have two votes: one for a party (which determines the number of seats) and a second to give personal scores to up to three candidates from any party. A party's seats are filled by its members who received the most personal votes.
Leader: The most popular member of the largest party becomes Prime Minister.


5. Allied Logistics (Economic Interaction)
Ants can now use allied bases as staging areas, but with a "tax".
What's done:
Resource Deposit: A worker can deposit resources at an ally's base. 10% of the deposit goes to the ally's storage, and 90% is "teleported" to the nearest home base.
Resupply: A worker can resupply at an ally's base. The resources are taken from the storage of his home faction, but the ally additionally receives 10% of the amount taken as a "service fee".
Where it is in the code: The Ant.depositResources() and Ant.replenish() functions have been extended to check if the base is allied (isAllyBase) and apply that logic.
6. Interface and Logs Update
To make all these complex mechanics visible, I updated the UI.
What's done:
Stats panel: Each faction block now has an Allies: ... line, which lists its allies.
Event log: When an ally joins a war, a message appears: "[Faction name] joined the war to defend its ally."
Where it is in the code:
Added a block to create allianceHTML in the render() function.
Added a logEvent() call to the declareWar() function for allies.
These changes should make the simulation much deeper, turning it from a simple "fight" into something like a geopolitical simulator with blocs, alliances, and complex economic interdependencies.
What has changed overall: from chaos to bloc politics
Previously, the world was like a "war of all against all", where each faction acted alone, guided by the immediate needs. Now the simulation has become more like geopolitics:
Unions (Alliances) have appeared: Factions with the same form of government now automatically become allies. This is the most important change. The world no longer consists of 10 individuals, but of several ideological blocs (for example, the "Monarchy" bloc, the "STV Republics" bloc, etc.).
Economic interaction: Allies can help each other. Ants can now use allied bases as "fueling stations" and resource delivery points. This makes the geographic location of allies strategically important.
Universal suffrage: Soldiers are no longer just "cannon fodder", but full-fledged citizens in democratic states. They can vote and be elected, which can lead to a more militarized policy in the republics.
Have the rules of war changed? Yes, dramatically!
The rules of war have changed in three key areas: reason, opportunity, and scale.
1. The reason for war has become more meaningful
Was: War was declared for any reason. A shortage of weapons or armor could provoke an attack on a neighbor who had a lot of them.
Now: War is declared only due to a shortage of vital resources: food, water, or a resource for reproduction (repro). Factions will no longer fight just for "hardware". They attack only when they are threatened with extinction or stagnation, and their neighbor has a surplus (>60%).
2. A condition of "military superiority" has appeared
Was: A hungry but weak faction could recklessly attack a strong, well-armed neighbor and be guaranteed to lose.
Now: Now the "hungry" will not attack the "strong" if they are not confident in their strength. To declare war, the aggressor faction must have an advantage:
Or its leader must be better armed than the defender's leader (weapons > armor).
Or it must have more soldiers.
This makes wars more calculated and less suicidal.
3. Wars have become "World" (bloc)
Was: War was strictly 1 on 1.
Now: War is now a matter for the entire alliance. If a Dictatorship attacks one STV Republic, then all other STV Republics on the map automatically enter the war on the side of their ally. Likewise, all allies of the Dictatorship (if there were any) would enter the war on its side.
This completely changes the strategy: Now you can't just attack a weak neighbor. You need to evaluate who their allies are and whether you are ready to fight their entire bloc.
Final conclusion about the changes:
If earlier the simulation was about the survival of an individual in chaos, now it has become about the confrontation of ideological blocs. The success of a faction now depends not only on its internal stability, but also on:
The number and strength of its allies.
The ability to wage war on several fronts.
The ability to choose the right moment for an attack, assessing not only the victim, but also its entire alliance.
The world has become much more structured and strategically deep.


Of course. Here is the same detailed guide, translated into English, maintaining the requested structure.

Part 1: Overview of Global Systems (The "Living World")

All factions exist within a framework of unified global rules that make the world complex and dynamic.

Advanced Economy: Factions do not just gather resources; they build production chains (Ore → Metal → Weapon/Armor). They also need to advance their science (Knowledge) to improve their technologies.

Economic Constraints: Armies and colonies (except the first one) require Gold for upkeep, and Food and Water spoil over time. This forces factions to remain economically active.

Dynamic Diplomacy: Wars and alliances are based on a fluctuating Relationship score between factions, influenced by ideology, borders, military strength, and a history of conflicts.

Part 2: Forms of Government and Election Mechanics

Here, we will examine in detail how each faction elects its leaders.

Lotocracy

Color: Red (#e53935)

Principle: Rule by chance (lottery).

Election Mechanics:

Candidates: All ants in the faction have an equal chance of becoming the leader.

Lottery: When a new leader needs to be chosen, the system selects a random ant from the entire faction population (including workers and soldiers).

Re-election: Occurs either after the current leader's death or after 2000 game ticks have passed.

Monarchy (H)

Color: Orange (#fb8c00)

Principle: Rule by "bloodline" (similarity).

Election Mechanics:

Inheritance: Upon the death of a Monarch, the system searches for an "heir."

Candidates: All workers in the faction are considered candidates.

Similarity Assessment: The system calculates the "similarity" of each candidate to the deceased monarch based on the proximity of their internal resource reserves (food, water, ore, etc.).

Selection: The worker whose resource reserves are most similar to those of the late monarch (i.e., has the smallest "distance") becomes the new Monarch.

Dictatorship

Color: Green (#43a047)

Principle: Rule by the strongest.

Election Mechanics:

Candidates: Only soldiers in the faction are eligible.

Strength Assessment: The system evaluates each soldier's strength by summing their weapon and armor stats.

Selection: The strongest soldier (with the highest combined total) becomes the Dictator.

Alternative: If there are no soldiers at the time of the "election," a random worker is appointed as Dictator.

Rep. FPTP (First-Past-The-Post Republic)

Color: Blue (#1e88e5)

Principle: Winner takes all.

Election Mechanics:

Candidates: All eligible ants.

Voting: Each voter casts a single vote for one candidate.

Preference: A voter "votes" for the candidate who is most ideologically similar to them (based on resource deficits).

Victory: The candidate who receives the most votes (a plurality, not necessarily a majority) becomes President.

Rep. IRV (Instant-Runoff Voting Republic)

Color: Pink (#f06292)

Principle: Finding a compromise majority.

Election Mechanics:

Ranking: Each voter ranks all candidates from best to worst.

First Round: Only "first-choice" votes are counted.

Elimination: If no candidate has over 50% of the vote, the candidate with the fewest votes is eliminated.

Redistribution: The votes for the eliminated candidate are transferred to those voters' next preference.

Repeat: Steps 3 and 4 are repeated until one candidate achieves an absolute majority.

Rep. Score (Score Voting Republic)

Color: Yellow (#fdd835)

Principle: The candidate with the highest average rating wins.

Election Mechanics:

Ranking: Each voter ranks all candidates.

Point Allocation: Candidates are awarded points based on their rank (e.g., 1st place gets 5 points, 2nd gets 4, etc.).

Summation: All points for each candidate are summed up.

Victory: The candidate with the highest total score wins.

Rep. PR (Proportional Representation Republic)

Color: White (#f5f5f5)

Principle: The parliament should mirror society.

Election Mechanics:

Parties: Voters are grouped into "parties" based on their most urgent need (resource deficit).

Seat Allocation: The 5 seats in parliament are distributed proportionally to the size of these parties.

Candidate Nomination: Each party nominates candidates who best represent the "average voter" of that party.

Rep. STV (Single Transferable Vote Republic)

Color: Teal (#00acc1)

Principle: Rule by the most popular individuals.

Election Mechanics: (Simplified implementation). Similar to Rep. Score, but for a parliament. The 5 candidates who achieve the highest total score from all voters' rankings become deputies.

Rep. PR Open (Open-List Proportional Representation)

Color: Gray (#9e9e9e)

Principle: Party proportionality + personal choice.

Election Mechanics: Similar to Rep. PR, seats are allocated proportionally to parties. However, the seats are filled by the most popular individuals within each party, as determined by the voters.

Rep. Mixed (Mixed-Member Proportional Republic)

Color: Mint (#26a69a)

Principle: A balance between parties and individuals.

Election Mechanics: Combines two voting methods: one for "parties" (like Rep. PR) and another for specific candidates (like Rep. STV). The final parliament is a combination of both results.

Rep. Approval (Approval Voting Republic)

Color: Purple (#8e24aa)

Principle: Choosing the most broadly acceptable candidates.

Election Mechanics:

Approval: Each voter can vote for ("approve of") multiple candidates (up to 5 of their closest ideological matches in the code).

Vote Tally: The votes for each candidate are simply summed.

Victory: The 5 candidates with the most "approvals" win seats in the parliament.

Rep. Range (Range Voting Republic)

Color: Lime (#c0ca33)

Principle: Selection based on a detailed evaluation of everyone.

Election Mechanics:

Rating: Each voter rates every candidate on a scale from 0 to 3, based on ideological similarity.

Score Summation: Each candidate's scores are summed up.

Victory: The 5 candidates with the highest total scores become deputies.

Part 3: What is "Policy" and How Does It Work?

In the simulation, "policy" is essentially a labor allocation plan. It determines what percentage of ants become soldiers versus workers, and how workers are assigned to various tasks.

Mechanics of Policy Formation

Policy is determined by the faction's "political center," which can be either a single leader or a parliament.

Determining the "Center's" Needs:

Single Leader (Lotocracy, Monarchy (H), Dictatorship, Rep. FPTP, Rep. IRV, Rep. Score): The leader's personal internal stats (food, water, ore, etc.) form the basis of the policy.

Parliament (Rep. PR, Rep. STV, Rep. PR Open, Rep. Mixed, Rep. Approval, Rep. Range): Policy is based on the "average" stats of all deputies in the parliament (specifically, the "median" deputy), ensuring a more balanced approach.

Calculating Deficits:

The system analyzes the "political center's" stats to calculate the deficit for each resource. For example, if the leader is low on food, the food deficit will be high.

Forming a Work Plan (workerDistribution):

Based on these deficits, a work plan is created for the workers.

Example: If the largest deficit is food, the highest percentage of workers will be assigned to gather_food. If there is also a shortage of ore, some workers will be assigned to gather_ore.

The system dynamically allocates 100% of worker time between gathering, production, and research, prioritizing the most acute deficits.

Policy Differences Across Systems

Lotocracy: Policy is completely chaotic. If the leader is short on food, everyone gathers food. If the next day's leader is short on metal (which is produced, not gathered), the policy becomes ineffective and illogical.

Monarchy (H): Policy is very stable and conservative. The new monarch is similar to the old one, so the faction's course changes slowly. If the dynasty is "starving," it will focus on food for generations.

Dictatorship: Policy is often militaristic. Since the leader is the strongest soldier, their personal needs are usually met. Therefore, their policy is often balanced but with a slight bias toward maintaining military strength (tasks like forge_weapon and forge_armor).

Single-Winner Republics (Rep. FPTP, Rep. IRV, Rep. Score): Policy can change drastically after each election if a candidate with completely different priorities wins. Rep. FPTP is most prone to such sharp shifts.

Parliamentary Republics (Rep. PR, Rep. STV, Rep. Approval, Rep. Range, etc.): Policy is the most balanced and moderate. Because it is determined by the average opinion of 5 deputies, the extremes of a single leader are smoothed out. This makes these factions more stable in the long run but potentially less agile during acute crises.

1. Parliamentary Lotocracy
How it's formed: Every 2000 ticks, or when the previous leader dies, a new parliament is formed. Up to 5 ants are chosen completely at random from the general population (ants that are not already politicians). The first ant selected in this random draw becomes the Prime Minister (the leader). The other selected ants become members of the parliament.
Policy: The faction's policy (resource focus, soldier ratio) is not determined by the leader alone. Instead, it's based on the median needs and stats of all parliament members. This creates a fluctuating and often unpredictable government that truly represents a random sample of the population at any given time.
2. Military Junta
How it's formed: Every 2000 ticks, an election is held to form a ruling council (the Junta). The system selects up to 5 of the most powerful soldiers, ranked by the combined strength of their weapons and armor. The single strongest soldier becomes the "Generalissimo" and acts as the faction leader. The other four form the ruling council. If there are no soldiers available, the council is formed from the strongest commoner ants instead.
Policy: Similar to the parliament, the Junta's policy is determined by the median stats of its members. Since the council consists of the military elite, their policies tend to be militaristic, focusing on the production of weapons, armor, and maintaining a high soldier count.
3. Oligarchic Monarchy
How it's formed: This faction is ruled by a council of up to 5 "Oligarch Monarchs". Unlike a traditional monarchy, each monarch has a term limit of 10,000 ticks, after which they "die of old age". When a seat on the council becomes vacant (due to death or term expiration), a successor is chosen from the populace. The new monarch is the ant whose resource stats are most similar to the average of the remaining council members. The "High Monarch" (the leader) is the one who has served on the council the longest.
Policy: This succession method creates an extremely stable and conservative government. New members are chosen to preserve the status quo, so policies change very slowly. Policy itself is determined by the median of the council's needs, leading to a highly consistent and predictable path for the faction.

Explanation of the "Negative Proportional Republic" Faction (in English)
This complex form of government is designed to elect the most acceptable and least controversial candidates. Instead of voting for who they like, voters actively cast votes against those who are too different from them.
The election proceeds in two main stages:
Stage 1: The Proportional Party Contest
Party and List Formation:
All ants are grouped into "parties" based on their primary need (food, water, etc.).
Each party creates an initial candidate list, ranking the neediest members at the top. This list is used later for tie-breaking.
Voting for Parties:
A standard proportional representation vote occurs: voters support parties, weak ones are eliminated, and their votes are transferred.
Based on the results of this round, seats in the parliament (up to 5) are allocated to the winning parties.
Stage 2: Personal Negative Voting
This is the key and unique stage that happens after the seats have been allocated.
Self-Comparison: Each voter personally evaluates every candidate within their own party. They calculate a "dissimilarity score" for each candidate by summing up the differences across all strategic resources (food, water, ore, reproduction).
Voting "AGAINST":
After determining who is least like them, the voter casts a "cross" (a negative vote) for the three candidates with the highest dissimilarity score.
In this way, voters filter out fellow party members whose life circumstances, and therefore interests, are too far removed from their own.
Final Ranking:
After all voters have cast their negative votes, the candidates on each party's list are completely re-sorted according to two rules:
Primary Rule: The candidate who received the fewest negative votes rises to the top of the list.
Tie-Breaker Rule: If candidates have an equal number of negative votes, the one who was ranked higher on the initial list (i.e., was more in need) wins the higher position.
Outcome
The parliament is formed by the candidates who lead these final, filtered lists. This system effectively weeds out "radical" candidates or those who differ too much from the average voter, promoting moderate, compromise-oriented figures who provoke the least opposition from their party's base.
