# Activity 9: Pack for the Trip — A Genetic Algorithm Challenge
## Sessions 16
## Due date (mm/dd/yyyy): 10/04/2026
## Adriana Rosales González
## Delivery Format: [] Video URL | [X] Markdown file | [] Jupyter Notebook file

---

# Activity Description
## The Story

You're heading out on a business trip with one **8 kg carry-on bag**. You have 8 items you'd
like to bring — a laptop, a client gift, a camera, and more — each with its own weight and
usefulness score, but they don't all fit. Which combination should you pack to get the **most
total usefulness** without going over the weight limit?

This is the classic **Knapsack Problem** — the same kind of decision behind choosing which
projects to fund with a limited budget, which items to stock in limited warehouse space, or
which features to build with limited developer time. Today you'll solve it the way nature
solves survival: with a **Genetic Algorithm** — evolving a population of candidate packing plans
across generations using selection, crossover, and mutation.

This activity is a single interactive app — no coding required. Everyone in the class uses the
**same fixed items and the same fixed genetic algorithm run** (the "randomness" is seeded, so it
produces identical results every time), so your results should match your classmates' exactly.


### Your Tasks


1. **Read the Packing Problem tab.** Note the 8 items, the weight limit, and the vocabulary
   table.
   <img width="625" height="293" alt="image" src="https://github.com/user-attachments/assets/4886578e-8dfb-4e2d-9b34-666fae819acb" />

- Weight limit: 8 kg
- Number of items: 8
- Vocabulary: chromosome, gene, population, fitness, generation, selection, crossover, mutation.

---
2. **Step through all 12 generations in the Run the Genetic Algorithm tab, one click at a
   time.**
   
- STEP 1
<img width="605" height="374" alt="image" src="https://github.com/user-attachments/assets/e49e9368-c636-481e-b18f-e6d4cdfedfbc" />
   
- STEP 2
<img width="628" height="359" alt="image" src="https://github.com/user-attachments/assets/67a56854-8db0-4149-b9b0-c4d44ddce267" />

- STEP 3
<img width="622" height="355" alt="image" src="https://github.com/user-attachments/assets/0c37620e-7e6f-4c22-b309-43700d93d419" />

- STEP 4
<img width="622" height="358" alt="image" src="https://github.com/user-attachments/assets/a2b0835f-c920-458d-afc2-7374c0f97c74" />

- STEP 5
<img width="626" height="358" alt="image" src="https://github.com/user-attachments/assets/6360b599-b2d1-42a0-9853-26d843e0519b" />

- STEP 6
<img width="628" height="365" alt="image" src="https://github.com/user-attachments/assets/3fc4a20c-1730-4fbd-a4b6-22e3e5bf9ab4" />

- STEP 7
<img width="620" height="353" alt="image" src="https://github.com/user-attachments/assets/40a7aadb-0406-40e5-8714-d3121236f069" />

- STEP 8
<img width="625" height="357" alt="image" src="https://github.com/user-attachments/assets/2dfdf779-11c1-40e3-b841-0547568759bf" />

- STEP 9
<img width="622" height="368" alt="image" src="https://github.com/user-attachments/assets/8facbdfe-01af-46ac-8214-990a4546b79f" />

- STEP 10
<img width="626" height="365" alt="image" src="https://github.com/user-attachments/assets/06f57204-7d28-49ec-955f-31b7f3b36186" />

- STEP 11
<img width="631" height="364" alt="image" src="https://github.com/user-attachments/assets/3be50e15-60a2-4c81-b56e-8c3759809558" />


---   
3. **Take a screenshot of the Final Result**
<img width="617" height="515" alt="image" src="https://github.com/user-attachments/assets/fdf49d9f-57b5-4749-bc20-911cd4c11b2c" />

---
# References:
- [Streamlit documentation](https://docs.streamlit.io/)
- [Markdown Guide](https://www.markdownguide.org/basic-syntax/)



---

## Activity 9 — Reflection Questions: Pack for the Trip

**1. What is the bag's weight limit, and how many total possible packing combinations exist for 8 items?**
   - The carry-on bag has a strict weight limit of 8 kg. Since there are 8 items to choose from, each item can either be included or excluded, giving us 28=256 possible packing combinations. This illustrates the combinatorial explosion of the knapsack problem: even with a small number of items, the number of possible solutions grows exponentially, making brute-force evaluation increasingly impractical in larger scenarios. 


**2. What is the **true optimal packing** (list the items) and its total value, according to the brute-force check?**
   - The brute-force check across all 256 combinations confirms that the true optimal packing is:
      - Laptop, Charger, Camera, Client Gift with a total usefulness value of 29. This represents the absolute best solution under the weight constraint, serving as the benchmark against which the genetic algorithm’s performance is measured.

**3. What is **Generation 1's** best-in-generation fitness, and which items does that packing plan contain?**
   - In Generation 1, the best solution achieved a fitness value of 24, with the items:
Laptop, Camera, Client Gift This shows that even in the initial random population, feasible and relatively strong solutions can emerge. However, it was not yet the optimal solution, highlighting the importance of iterative improvement through genetic operations.


**4. At which generation does **"Best-ever"** first reach its final value, and what is that   value?**
   - The Best-ever fitness value reached its final maximum of 29 in Generation 6. This indicates that by the sixth generation, the algorithm successfully evolved a solution that matched the true optimal packing. From that point onward, “Best-ever” preserved this result, even if later generations temporarily produced weaker solutions.

**5. Did the Genetic Algorithm find the true optimal packing? If yes, say at which generation it was first found; if no, report the exact gap between the algorithm's best-ever value and the true optimum.**
    - Yes, the genetic algorithm did find the true optimal packing.
   -  It was first discovered in Generation 6, with the items Laptop, Charger, Camera, and Client Gift. This demonstrates that the algorithm’s evolutionary process was effective in converging toward the best possible solution within a limited number of generations.


**6. Find one generation where **"Best in Generation"** is *lower* than **"Best-ever."** Name that generation, and explain in one sentence why that's possible for this particular kind of genetic algorithm (non-elitist).**

- An example occurs in Generation 9:
   - Best in Generation: 26 (Laptop, Umbrella, Camera, Client Gift)
   - Best-ever: 29 (Laptop, Charger, Camera, Client Gift) This discrepancy happens because the algorithm is non-elitist, meaning it does not guarantee that the best solution from one generation will survive into the next. As a result, weaker solutions can dominate temporarily, but “Best-ever” ensures that the highest fitness found so far is never lost.


**7. In your own words, explain what **crossover** and **mutation** each contribute to a genetic algorithm's ability to find good solutions, using this packing problem as your example.**
   - Crossover: This operation combines parts of two parent solutions to create new offspring. In the packing problem, it allows useful traits from different solutions to merge — for example, one parent with Laptop + Client Gift and another with Camera + Charger could produce a child solution containing all four items. This accelerates the search for high-value combinations.
   - Mutation: Mutation introduces random changes, such as flipping the inclusion of an item. For instance, a plan might suddenly add Snacks or remove the Umbrella. Mutation prevents the population from stagnating and helps explore new areas of the solution space, ensuring diversity and avoiding local optima.


**8. Name one **real business, IT, or design scenario** (other than packing a suitcase) where a genetic algorithm would be useful instead of just checking every possible option by brute force. Briefly explain why brute force wouldn't work well there.**

   - A practical example is feature selection in software product development. Companies often face dozens of potential features to implement, each with different costs and benefits. Brute-force evaluation of all possible feature sets would be computationally impossible due to the sheer number of combinations. A genetic algorithm, however, can evolve promising sets of features that maximize user value while respecting budget and time constraints. Just like packing the suitcase, the algorithm balances usefulness against limited resources.


   
