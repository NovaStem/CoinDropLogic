package sample;

import javafx.event.ActionEvent;
import javafx.fxml.FXML;
import javafx.scene.Node;
import javafx.scene.control.Button;
import javafx.scene.effect.ColorAdjust;
import javafx.scene.layout.GridPane;
import javafx.scene.effect.Effect;
import javafx.scene.layout.StackPane;

import java.awt.event.MouseEvent;

public class Controller {
    // numbers represent coordinate spot on grid pane [col][row]
    @FXML
    Button b00;
    @FXML
    Button b10;
    @FXML
    Button b20;
    @FXML
    Button b30;
    @FXML
    Button b40;
    @FXML
    Button b50;
    @FXML
    Button b60;
    @FXML
    //second row
    Button b01;
    @FXML
    Button b11;
    @FXML
    Button b21;
    @FXML
    Button b31;
    @FXML
    Button b41;
    @FXML
    Button b51;
    @FXML
    Button b61;
    //third row
    @FXML
    Button b02;
    @FXML
    Button b12;
    @FXML
    Button b22;
    @FXML
    Button b32;
    @FXML
    Button b42;
    @FXML
    Button b52;
    @FXML
    Button b62;
    @FXML
    //fourth row
    Button b03;
    @FXML
    Button b13;
    @FXML
    Button b23;
    @FXML
    Button b33;
    @FXML
    Button b43;
    @FXML
    Button b53;
    @FXML
    Button b63;
    //fifth row
    @FXML
    Button b04;
    @FXML
    Button b14;
    @FXML
    Button b24;
    @FXML
    Button b34;
    @FXML
    Button b44;
    @FXML
    Button b54;
    @FXML
    Button b64;
    //sixth row
    @FXML
    Button b05;
    @FXML
    Button b15;
    @FXML
    Button b25;
    @FXML
    Button b35;
    @FXML
    Button b45;
    @FXML
    Button b55;
    @FXML
    Button b65;

    @FXML
    GridPane GameBoard;

    int [][] table = new int [7][6];



    private boolean isFirstPlayer = true;

    public void buttonClickHandler(ActionEvent evt) {


        Button clickedButton = (Button) evt.getTarget();
        String buttonColor = clickedButton.getStyle();
        String buttonLable = clickedButton.getId();



        if ("".equals(buttonColor) && isFirstPlayer) {
            clickedButton.setStyle("-fx-background-color:blue");
            String str= buttonLable;

            System.out.println(str.substring(1,2)); // gets the col
            System.out.println(str.substring(2,3)); // gets the row
            String strcol = str.substring(1,2) ;
            String strrow = str.substring(2,3) ;
            table[Integer.parseInt(strcol)][Integer.parseInt(strrow)] = 1; // first player

            isFirstPlayer = false;


        } else if ("".equals(buttonColor) && !isFirstPlayer) {
            clickedButton.setStyle("-fx-background-color: red");
            String str= buttonLable;

            System.out.println(str.substring(1,2)); // gets the col
            System.out.println(str.substring(2,3)); // gets the row
            String strcol = str.substring(1,2) ;
            String strrow = str.substring(2,3) ;
            table[Integer.parseInt(strcol)][Integer.parseInt(strrow)] = 2; // second player

            isFirstPlayer = true;
        }

        for (int row = 0; row < 6; row++) { //moves down rows
            for (int col = 0; col < 7; col++) { //moves down columns
                System.out.print(table[col][row] + " "); //prints value at coordinate
            }
            System.out.println(); //moves text to a new line


        }


        }



    }
