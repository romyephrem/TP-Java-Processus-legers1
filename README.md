# TP-Java-Processus-legers1
ex1:Cpt

public class Cpt extends Thread {
      private static int _cpt =1;
      private String _name;
      public Cpt(String name) {
          _name = name; }
      public static int getValeur() {
          return _cpt; }
      public void run () {
          for(int i = 1; i <= 100000; i++ ) {
                int _c = _cpt ;
                _cpt = _c + 1 ; }
          }
     }
     public static void main (String args[]) {
          System.out.println("VALEUR " + Cpt.getValeur());
          Cpt thr1 = new Cpt("Processus1");
          Cpt thr2 = new Cpt("Processus2");
          thr1.start(); thr2.start();
          try {
              thr1.join(); thr2.join();
              }
          catch (Exception e) {
              System.out.println(e);
              }
          System.out.println("VALEUR " + Cpt.getValeur());
      }
     
                
