# Ex.No:3(C) ABSTRACTION

## QUESTION:
Description:
Create abstract class GameScore with method finalScore().
Subclasses:

ArcadeGame: score = baseScore + (level × 100)

PuzzleGame: score = (attempts ≤ 3) ? 1000 - (attempts × 100) : 500

Input Format:

First line: 1 or 2
Second line: base, level (or attempts)

Output Format:

Final score (int)

For example:

<img width="433" height="168" alt="image" src="https://github.com/user-attachments/assets/7e044b2e-268e-493e-84b6-5cbdb407b4f1" />


## AIM:
To create an abstract class GameScore and calculate final scores for different types of games using subclasses.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'.
3.	Create an abstract class GameScore with an abstract method finalScore().
4.	Create subclass ArcadeGame that calculates score as baseScore + (level × 100).
5.	Create subclass PuzzleGame that calculates score as 1000 - (attempts × 100) if attempts ≤ 3, else 500.
6.	In the main method, read game type and relevant input values.
7.	Create the appropriate game object and call finalScore().
8.	Display the final score.
9.	Stop the program.




## PROGRAM:
 ```
/*
Program to implement a Abstraction using Java
Developed by: Sabitha P
RegisterNumber:  212222040137
*/
```

## SOURCE CODE:


```
import java.util.*;

abstract class GameScore {
    abstract int finalScore();
}

class ArcadeGame extends GameScore {
    private int baseScore;
    private int level;

    public ArcadeGame(int baseScore, int level) {
        this.baseScore = baseScore;
        this.level = level;
    }

    @Override
    int finalScore() {
        return baseScore + (level * 100);
    }
}
class PuzzleGame extends GameScore {
    private int attempts;

    public PuzzleGame(int attempts) {
        this.attempts = attempts;
    }

    @Override
    int finalScore() {
        return (attempts <= 3) ? 1000 - (attempts * 100) : 500;
    }
}

public class GameScoreCalculator {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int type = sc.nextInt();

        GameScore game;
        if (type == 1) {
            int base = sc.nextInt();
            int level = sc.nextInt();
            game = new ArcadeGame(base, level);
        } else if (type == 2) {
            int attempts = sc.nextInt();
            game = new PuzzleGame(attempts);
        } else {
            System.out.println("Invalid game type.");
            sc.close();
            return;
        }

        System.out.println(game.finalScore());
        sc.close();
    }
}

```

## OUTPUT:

<img width="603" height="245" alt="image" src="https://github.com/user-attachments/assets/49113b00-48bd-4399-b561-4a41cf15b493" />


## RESULT:
The program successfully calculates and displays the final score for Arcade and Puzzle games based on user input.
