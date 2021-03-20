
import java.io.*;
import java.util.*;

class goodie {
  String name;
  int price;

  public goodie(String name, int price) {
    this.name = name;
    this.price = price;
  }

  public String toString() { 
      return this.name + ": " + this.price;
  }
}

public class goodie_dilemma {
	
  public static void main(String[] args) throws Exception {
 
    FileInputStream file=new FileInputStream("C:\\Users\\aswin\\Desktop\\input.txt"); 
    Scanner sc=new Scanner(file);
    
    //Getting number of employees
    int number_of_employees = Integer.parseInt(sc.nextLine().split(": ")[1]);
    sc.nextLine(); 
    sc.nextLine(); 
    sc.nextLine();

    ArrayList<goodie> goodies = new ArrayList<goodie>();

    //Adding items and their prices to the arraylist
    while(sc.hasNextLine())  
    {
      String price[] = sc.nextLine().split(": ");
      goodies.add(new goodie(price[0], Integer.parseInt(price[1])));
    }
    sc.close();
    
    Collections.sort(goodies, new Comparator<goodie>(){
      public int compare(goodie goodie1, goodie goodie2) { 
        return goodie1.price - goodie2.price;        
      } 
    });

    int min_diff = goodies.get(goodies.size()-1).price;
    int min_index = 0;
    for(int i=0;i<goodies.size()-number_of_employees+1;i++) {
      int diff = goodies.get(number_of_employees+i-1).price-goodies.get(i).price;

      if(diff<=min_diff) {
        min_diff = diff;
        min_index = i;
      }
    }


    FileWriter writer = new FileWriter("C:\\Users\\aswin\\Desktop\\output.txt");
    writer.write("The goodies selected for distribution are:\n\n");
    for(int i=min_index;i<min_index + number_of_employees; i++) {
      writer.write(goodies.get(i).toString() + "\n");
    }

    writer.write("\nAnd the difference between the chosen goodie with highest price and the lowest price is " + min_diff);
	  writer.close();
  }
}
