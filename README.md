# Cobis-Convience-Store

package com.company;
import java.util.ArrayList;
import java.util.Scanner;
public class Main {


    public static void main(String[] args) {
        //add starters variable
        ArrayList<String> storeproduct = new ArrayList<String>();
        ArrayList<Integer> productarchive = new ArrayList<Integer>();
        ArrayList<String> archive = new ArrayList<String>();
        ArrayList<Double> rate = new ArrayList<Double>();

        storeproduct.add("Red-Hot Spicy Doritos");
        rate.add(2.99);
        //
        storeproduct.add("Cool Ranch Doritos");
        rate.add(2.99);
        //
        storeproduct.add("Coke");
        rate.add(0.99);
        //
        storeproduct.add("Diet Coke");
        rate.add(0.99);
        //
        storeproduct.add("Pepsi");
        rate.add(0.99);
        //
        storeproduct.add("Five Hour Energy");
        rate.add(3.99);
        //
        storeproduct.add("Sunflower Seeds");
        rate.add(0.99);
        //
        storeproduct.add("Peanuts");
        rate.add(0.99);
        //
        storeproduct.add("Mac Book Chargers");
        rate.add(120.00);
        //
        storeproduct.add("Dell Chargers");
        rate.add(50.00);



        System.out.println("Hello, Welcome to Cobis Convenience Store!\n");
        System.out.println("The items we offer are presented below: ");
        System.out.println("0 :  Red-Hot Spicy Doritos" +
                "\n1 :  Cool ranch Doritos" +
                "\n2 :  Coke" +
                "\n3 :  Diet Coke" +
                "\n4 :  Pepsi" +
                "\n5 :  Five Hour Energy" +
                "\n6 :  Sunflower seeds" +
                "\n7 :  Peanuts" +
                "\n8 :  Mac Book Chargers" +
                "\n9 : Dell Chargers");

        Scanner scanner = new Scanner(System.in);
        String putin;
        StringBuilder output = new StringBuilder();
        double endTotal;
        double grandTotal = 0;


        System.out.println("insert your name for us or type 'end session'");
        while(!(putin = scanner.nextLine()).equalsIgnoreCase("end session")) {
            output.append(putin);
            endTotal = 0;
            do {
                System.out.println("each item has a identification, what is it? /enter 010 when to finalize purchases ");
                putin = scanner.nextLine();
                for(String prod :storeproduct) {
                    if(Integer.parseInt(putin)==(storeproduct.indexOf(prod) )) {
                        storeproduct.get(storeproduct.indexOf(prod));
                        endTotal += rate.get(storeproduct.indexOf(prod));
                        String itemname = storeproduct.get(Integer.parseInt(putin));
                        output.append("\n").append(itemname);
                        if(!archive.contains(putin)) {
                            archive.add(putin);
                            productarchive.add(1);
                        }
                        else {
                            int indexnum = archive.indexOf(putin);
                            productarchive.set(indexnum, productarchive.get(indexnum) + 1);
                        }
                        break;
                    }
                }
            }while ((!putin.equalsIgnoreCase("010")));
            output.append(" \n \t\t\t").append(endTotal).append("\n");
            grandTotal += endTotal;

            System.out.println("Enter the name of the next customer if store hours are between 10am - 10pm.(Type end session if store is closed): ");
        }
        System.out.println( "The Cobis Convenience Store is now Closed ");

        System.out.println("\n" + "Receipts per Customer Today:  \n  "  + output);

        System.out.println("Total Inventory Sold Today: ");
        System.out.println(" ");

        for(String invquantity :archive) {

            System.out.println(  "Item Number " + invquantity + ":" + " [" + productarchive.get(archive.indexOf(invquantity))+"]");
        }





        System.out.println(" ");

        System.out.println("Grand Total: $"  + grandTotal);

    }
}
