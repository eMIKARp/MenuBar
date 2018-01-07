# MenuBar
a piece o code that creates a simple menu bar

    package paskimenu;

       import javax.swing.*;
       import java.awt.*;
       import java.awt.event.*;

    public class Main extends JFrame 
    {

    private JMenuBar pasekMenu = new JMenuBar();
    private JCheckBoxMenuItem tylkoDoOdczytu= new JCheckBoxMenuItem("Tylko do odczytu");
    
    public Main()
    {
        initComponets();
    }
    
    public void initComponets()
    {
        this.setTitle("Okno Główne");
        this.setBounds(300,300,700,200);
        
        this.setJMenuBar(pasekMenu);
        JMenu menuFile = pasekMenu.add(new JMenu("File"));
            menuFile.add("New project...").addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                System.out.println("Został utowrzony nowy projekt");
            }
        });
            menuFile.add("New file...").addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                System.out.println("Został utworzony nowy plik");
            }
        });
            menuFile.addSeparator();
            menuFile.add("Open project...");
            menuFile.add("Open recent project...");
            menuFile.add("Close project...");
            menuFile.add("Close other projects...");
            menuFile.add("Close all projects...");
            menuFile.addSeparator();
            menuFile.add("Open file...");
            menuFile.add("Open recent file...");
            menuFile.addSeparator();
            JMenu iMenu = new JMenu("Import project");
            menuFile.add(iMenu);
            iMenu.add("Eclipse project");
            iMenu.add("Resynchronize eclipse project");
            iMenu.add("From ZIP");
            JMenu eMenu = new JMenu("Export project");
            menuFile.add(eMenu);
            eMenu.add("To ZIP File");
            menuFile.addSeparator();
            JMenuItem podMenuZapis = menuFile.add(new JMenuItem("Zapisz"));
            menuFile.add("Zapisz jako...");            
            menuFile.addSeparator();
            menuFile.add(tylkoDoOdczytu).addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
            if (tylkoDoOdczytu.isSelected())
                podMenuZapis.setEnabled(false);
            else
                podMenuZapis.setEnabled(true);
            }
        });
            menuFile.add("Exit");
        JMenu menuEdit = pasekMenu.add(new JMenu("Edit"));
            menuEdit.add("FAQ");
            
        pasekMenu.add(new JMenu("View"));
        pasekMenu.add(new JMenu("Navigate"));
        pasekMenu.add(new JMenu("Source"));
        pasekMenu.add(new JMenu("Refractor"));
        pasekMenu.add(new JMenu("Run"));
        pasekMenu.add(new JMenu("Debug"));
        pasekMenu.add(new JMenu("Team"));
        pasekMenu.add(new JMenu("Tools"));
        pasekMenu.add(new JMenu("Window"));
        pasekMenu.add(new JMenu("Help"));
        
        
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    }
    
    public static void main(String[] args) {
       new Main().setVisible(true);
    }
    
    }
