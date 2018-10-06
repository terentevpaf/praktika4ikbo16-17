# praktika4ikbo16-17

<pre>
import java.awt.*;
import javax.swing.*;
import java.awt.event.*;
import javax.swing.SwingConstants;

public class Main extends JFrame {

    JPanel[] pnl = new JPanel[4];
    int com1 = 0;
    int com2 = 0;
    int sum = 0;
    
    JButton ButtonLeft = new JButton("AC Milan");
    JButton ButtonRigth = new JButton("Real Madrid");
    JLabel resultLabel;
    JLabel lastScorer;
    JLabel winnerLabel;

    public Main()
    {
        super("Game");
        setLayout(new GridLayout(4,1));

        JPanel[] newGrid = new JPanel[2];
        newGrid[1] = new JPanel();
        newGrid[1].setLayout(new GridLayout(1,2));
        newGrid[1].add(ButtonLeft);
        newGrid[1].add(ButtonRigth);
        add(newGrid[1]);

        resultLabel = new JLabel("Result: 0 X 0", SwingConstants.CENTER);
        lastScorer = new JLabel("Last Scorer: N/A", SwingConstants.CENTER);
        winnerLabel = new JLabel("Winner: DRAW;", SwingConstants.CENTER);
        add(resultLabel);
        add(lastScorer);
        add(winnerLabel);

        ButtonLeft.addActionListener(new ActionListener()
        {
            public void actionPerformed(ActionEvent ae)
            {
                com1++;
                resultLabel.setText("Result: " + com1 + " X " + com2);
                lastScorer.setText("AC Milan");
                if(com1 == com2)
                {
                    winnerLabel.setText("DRAW");
                }
                else if(com1 > com2)
                {
                    winnerLabel.setText("AC Milan");
                }
                else if(com1 < com2)
                {
                    winnerLabel.setText("Real Madrid");
                }
            }
        });

        ButtonRigth.addActionListener(new ActionListener()
        {
            public void actionPerformed(ActionEvent ae)
            {
                com2++;
                resultLabel.setText("Result: " + com1 + " X " + com2);
                lastScorer.setText("Real Madrid");
                if(com1 == com2)
                {
                    winnerLabel.setText("DRAW");
                }
                else if(com1 > com2)
                {
                    winnerLabel.setText("AC Milan");
                }
                else if(com1 < com2)
                {
                    winnerLabel.setText("Real Madrid");
                }
            }
        });

        setSize(300, 300);
    }

    public static void main(String[] args)
    {
        new Main().setVisible(true);
    }
}


</pre>
