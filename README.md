using System;
using System.Drawing;
using System.Windows.Forms;

class CircularCursorMovement : Form
{
    Timer timer = new Timer();
    double angle = 0;
    double centerX, centerY;
    double radius = 100;

    public CircularCursorMovement()
    {
        centerX = Screen.PrimaryScreen.Bounds.Width / 2; // Center X of screen
        centerY = Screen.PrimaryScreen.Bounds.Height / 2; // Center Y of screen

        timer.Interval = 10; // Interval in milliseconds
        timer.Tick += Timer_Tick;
        timer.Start();
    }

    private void Timer_Tick(object sender, EventArgs e)
    {
        angle += 0.05; // Adjust speed of rotation here
        double newX = centerX + radius * Math.Cos(angle);
        double newY = centerY + radius * Math.Sin(angle);

        Cursor.Position = new Point((int)newX, (int)newY);
    }

    static void Main()
    {
        Application.Run(new CircularCursorMovement());
    }
}
