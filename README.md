# philosophers

*Oh bold thinker, step into the halls of reason where logic reigns supreme, and the age-old challenge of harmony among philosophers awaits!* 

Within this repository lies **philosophers**, an ode to the computational elegance of concurrency and synchronization. Here, you shall grapple with the conundrum of dining philosophers, a problem that has perplexed the finest minds since the 1960s, when Edsger Dijkstra first posed it to illuminate the perils of resource sharing in concurrent systems.

---

## Prelude: The Philosophers' Challenge

*In a distant era of nascent computing, where the machine's hum was the song of progress, a question arose:*

Five philosophers, seated around a circular table, pondered the mysteries of life. Between them lay five forks, and before them, steaming bowls of spaghetti. The philosophers alternated between two states: contemplating the vastness of existence and satisfying their hunger. Yet, to eat, a philosopher required two forks — the one to their left and the one to their right.

The challenge was clear: how could the philosophers dine without descending into chaos or starvation? Thus was born the **Dining Philosophers Problem**, a metaphor for resource allocation in concurrent systems. The solution demanded balance, ensuring that no philosopher starved and that no fork was forever held in greedy hands.

In this project, you, O coder, shall embody the role of the arbiter, crafting a solution that dances between deadlock and liveliness, weaving harmony among the hungry thinkers.

---

## Table of Contents

- [The Quest](#the-quest)
- [Features](#features)
- [Requirements](#requirements)
- [Getting Started](#getting-started)
- [Philosophical Mechanics](#philosophical-mechanics)
- [Testing](#testing)
- [Acknowledgments](#acknowledgments)

---

## The Quest

*Embark, O valiant coder, on a journey to bring order to the table of philosophers!*

Your mission is to simulate the Dining Philosophers Problem, adhering to these principles:
1. Each philosopher alternates between thinking and eating.
2. To eat, a philosopher must acquire both the fork to their left and the fork to their right.
3. Philosophers must dine without starving or causing a deadlock.
4. The simulation ends either when all philosophers have eaten a specified number of meals or when another defined condition is met.

This journey is a testament to your mastery over threads, mutexes, and the subtle art of synchronization.

---

## Features

*Marvel at the intricacies of philosophers:*

- **Concurrency**: Utilize threads to simulate simultaneous actions of philosophers.
- **Synchronization**: Employ mutexes to manage access to shared resources (forks).
- **Dynamic Simulation**: Configure the number of philosophers, meals, and other parameters.
- **Deadlock Prevention**: Implement strategies to avoid deadlock and ensure fairness.

---

## Requirements

*Equip yourself with these tools to navigate the labyrinth of threads and logic:*

- **Compiler**: GCC or Clang.
- **Libraries**: Standard C library and `pthread` for thread management.
- **Makefile**: Automate your build process with targets `all`, `clean`, `fclean`, and `re`.

---

## Getting Started

*Step into the halls of reason and begin thy work!*

Clone this repository and navigate to the `philosophers` directory:
```bash
git clone https://github.com/nsilva-n/42CC-3-philosophers.git
cd 42CC-3-philosophers
make
```

Run your program with:
```bash
./philosophers [number_of_philosophers] [time_to_die] [time_to_eat] [time_to_sleep] [number_of_meals]
```

Example:
```bash
./philosophers 5 800 200 200 7
```

This command simulates:
- 5 philosophers,
- who die if they don't eat within 800ms,
- taking 200ms to eat,
- 200ms to sleep,
- and finishing the simulation after each philosopher has eaten 7 meals.

---

## Philosophical Mechanics

*Understand the rules that govern the table of philosophers:*

### Parameters
1. **`number_of_philosophers`**: The number of philosophers and forks.
2. **`time_to_die`**: The maximum time (in milliseconds) a philosopher can go without eating before starving.
3. **`time_to_eat`**: The time (in milliseconds) it takes for a philosopher to eat.
4. **`time_to_sleep`**: The time (in milliseconds) a philosopher spends sleeping.
5. **`number_of_meals`** (optional): The number of times each philosopher must eat before the simulation ends.

### States
- **Thinking**: A philosopher contemplates the mysteries of existence.
- **Hungry**: A philosopher attempts to acquire two forks.
- **Eating**: A philosopher satisfies their hunger, holding two forks.
- **Sleeping**: A philosopher rests before their next contemplation.

### Rules
- A philosopher may only eat if they can acquire both forks.
- Philosophers release their forks after eating.
- The simulation ends when all philosophers have eaten the required number of meals or when a philosopher starves.

---

## Testing

*Test thy creation against the trials of concurrency and synchronization!*

### Debugging
To ensure the harmony of threads and the absence of data races, employ the following tools:
- **Valgrind's Memcheck**: For detecting memory leaks and invalid memory accesses.  
  Use the flags `--leak-check=full` and `--show-leak-kinds=all` for detailed output:
  ```bash
  valgrind --leak-check=full --show-leak-kinds=all ./philosophers 5 800 200 200
  ```
- **Valgrind's DRD**: For detecting threading errors.
  ```bash
  valgrind --tool=drd ./philosophers 5 800 200 200
  ```
- **Helgrind**: For identifying synchronization issues.
  ```bash
  valgrind --tool=helgrind ./philosophers 5 800 200 200
  ```

These tools will illuminate the shadows of concurrency, guiding you to a robust implementation.

---

### Visualization
*Witness the dance of the philosophers in real-time!*

To visualize the simulation, use the [Philosophers Visualizer](https://nafuka11.github.io/philosophers-visualizer/).  
This tool allows you to input your program's parameters and observe the philosophers' states as they transition between thinking, eating, and sleeping.

---

## Acknowledgments

*With gratitude to Edsger Dijkstra, the 42 curriculum, and the thinkers of past and present, we dedicate this work.*

May your journey through the labyrinth of `philosophers` lead you to enlightenment, where logic and harmony coexist in perfect balance.
