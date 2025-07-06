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
