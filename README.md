# NN Flappy Bird

NN Flappy Bird is an AI based flappy bird game where the we start game with **n** birds and when all birds died we start a **new generation** of birds who are selected from previos ones who performed most well. so that's how **_next generation will always be better then previous one_** .

## Quick Links

<details>

- [Technology Used](#technology-used)
- [Project setup](#project-setup)
- [Working](#working)
  - [Input](#input)
  - [Output](#output)
  - [Activation Function](#activation-function)
  - [Population size](#population-size)
  - [Fitness Function (Most Important Pat of NEAT algorithm)](#fitness-function-most-important-pat-of-neat-algorithm)
  - [Max Generation : 30 (in this project)](#max-generation)
- [Configuration File;](#configuration-file)
- [Images](#images)
- [Resources](#resources)

</details>

## Technology Used

Frontend: **Pygame**  
Logic : **Neat-python**  
Language : **Python**

## Project setup

1. Clone the repository

```bash
    git clone https://github.com/Suraj-1309/AI-Flappy-Bird.git
```

and change directry

```bash
cd AI-Flappy-Bird
```

2. Install required Python packages

```bash
pip install pygame neat-python
```

3. Now Setup is complete you can run the project

```bash
python .\flappy_bird.py
```

## Working:

-> **Neural Networks being Evolve using a generic algorithm**

### Input

- Bird Y (bird position on Y scale)
- Top Pipe
- Bottom Pipe

### Output

- Jump (movement of bird on Y scale)

### Activation Function

- Tan H (Hyperbolic Tengen Hunction)  
   **val > 0.5 => Jump**

![](/doc/ten.png)

### Population size

Arbitary value you can choose **Population size** as per your system can handle basiclly **_the more the Population Size the better the result will be_**.

Here I choose population size: **50**

- **Gen 1** : 50 birds
  - Test all these birds and then we gonna get the best bird.
- **Gen 2** : 50 birds
  - Little bit better than previous generation

and we keep going until we got the perfect bird.

### Fitness Function (Most Important Pat of NEAT algorithm)

- how neural network gonna grow and how birds actually will get better

takes the best bird from one population we breed them and we mutate them and we keep doing that.

now if we're actually getting the real best birds or we're scoring on some kind of matrics that dosn't make sense for the best bird then obviously we're gonna have a **trash AI**.

so we need to make sure that however we score these birds and get you know figure out which ones are better makes sense. For flappy bird, whenever bird makes it farthest in the level did the best so every kind of frame that the bird moves forward (like every X position it goes forwared) we're gonna get it another point and the birds that gt the farthest in the level gonna be a lot better than previous bird in terms of fitness because he made it further or they made it further in level.

**_Fitness Function <----- distance (how far it goes)_**

### Max Generation : 30 (in this project)

so at some point, after we ran
out of so many generations, if we still don't have an AI that works really well we're probably just gonna give up and try again because maybe we got unlucky, maybe when we did things just didn't work out in our favor.

## Configuration File;

- This is very imp. file that we need whenever we're creating a **NEAT** Project or using a **neat module**.
- This is kind of setting up all the variables and just parameters for this algorithm to run.

Genome -> Genes (connection between nodes)

## Images

![](/doc/Design.png)
![](/doc/start_game.png)
<br><br>
![](/doc/most_socre.png)

## Resources

1. This whole Project is copied from a youtuber called **_Tech With Tim_** to learn about AI with games. So whole credit goes to him.

You can check his youtube channel [here](https://youtu.be/MMxFDaIOHsE?si=6cfvygJ-kmIEAiXA)

2. The whole Projects working is depends on the Neat-Python so if you want to understand it you can read it at
   [Neat-Python Documentation](https://neat-python.readthedocs.io/en/latest/academic_research.html)
