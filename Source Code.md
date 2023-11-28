# Source Code

```
import javax.swing.*;

public class RankedMatchCalculator {

    public static void main(String[] args) {
        // Win input
        String literalWins = JOptionPane.showInputDialog("Enter the number of wins");

        while (literalWins.isBlank() || !literalWins.matches("[0-9]+")) {
            JOptionPane.showMessageDialog(null, "Please, insert a enter a non-negative number with no letters",
                    "ERROR!",
                    JOptionPane.ERROR_MESSAGE);
            literalWins = JOptionPane.showInputDialog("Enter the number of wins");
        }

        int numericWins = Integer.parseInt(literalWins);

        // Defeat input
        String literalDefeats = JOptionPane.showInputDialog("Enter the number of defeats");

        while (literalDefeats.isBlank() || !literalDefeats.matches("[0-9]+")) {
            JOptionPane.showMessageDialog(null, "Please, insert a enter a non-negative number with no letters",
                    "ERROR!",
                    JOptionPane.ERROR_MESSAGE);
            literalDefeats = JOptionPane.showInputDialog("Enter the number of wins");
        }

        int numericDefeats = Integer.parseInt(literalDefeats);

        // This is where the magic happens
        CalculateRankedMatch(numericWins, numericDefeats);
    }

    static void CalculateRankedMatch(int numWins, int numDefeats) {
        int rankingBalance = numWins - numDefeats;

        if (rankingBalance < 10) {
            JOptionPane.showMessageDialog(null, "The Hero has a Ranking Balance of " + rankingBalance +
                    " and he/she is at Iron level", "Hero Ranking", JOptionPane.PLAIN_MESSAGE);
        } else if (rankingBalance >= 11 && rankingBalance <= 20) {
            JOptionPane.showMessageDialog(null, "The Hero has a Ranking Balance of " + rankingBalance +
                    " and he/she is at Bronze level", "Hero Ranking", JOptionPane.PLAIN_MESSAGE);
        } else if (rankingBalance >= 21 && rankingBalance <= 50) {
            JOptionPane.showMessageDialog(null, "The Hero has a Ranking Balance of " + rankingBalance +
                    " and he/she is at Silver level", "Hero Ranking", JOptionPane.PLAIN_MESSAGE);
        } else if (rankingBalance >= 51 && rankingBalance <= 80) {
            JOptionPane.showMessageDialog(null, "The Hero has a Ranking Balance of " + rankingBalance +
                    " and he/she is at Gold level", "Hero Ranking", JOptionPane.PLAIN_MESSAGE);
        } else if (rankingBalance >= 81 && rankingBalance <= 90) {
            JOptionPane.showMessageDialog(null, "The Hero has a Ranking Balance of " + rankingBalance +
                    " and he/she is at Diamond level", "Hero Ranking", JOptionPane.PLAIN_MESSAGE);
        } else if (rankingBalance >= 91 && rankingBalance <= 100) {
            JOptionPane.showMessageDialog(null, "The Hero has a Ranking Balance of " + rankingBalance +
                    " and he/she is at Legendary level", "Hero Ranking", JOptionPane.PLAIN_MESSAGE);
        } else if (rankingBalance >= 101) {
            JOptionPane.showMessageDialog(null, "The Hero has a Ranking Balance of " + rankingBalance +
                    " and he/she is at Immortal level", "Hero Ranking", JOptionPane.PLAIN_MESSAGE);
        }
    }

}
```