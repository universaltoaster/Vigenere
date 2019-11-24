
public class Vigenere
{

    // ***** Methodendefinition *****
    public static String A_Textverschluesselung(String klartext, String schluessel){
        
        String geheimtext = "";
        
        klartext = bereinigterText(klartext);
        schluessel = bereinigterText(schluessel);
        schluessel = Schluesselvermehrung(klartext,schluessel);
        schluessel = Schluesselbereinigung(schluessel);
        geheimtext = verschluesselterText(klartext,schluessel);
        
        return geheimtext;
    }
    
    public static String A_Textentschluesselung(String geheimtext, String schluessel){
        
        String klartext = "";
        
        schluessel = bereinigterText(schluessel);
        schluessel = Schluesselvermehrung(geheimtext,schluessel);
        schluessel = Schluesselbereinigung(schluessel);
        klartext = entschluesselterText(geheimtext,schluessel);
        
        return klartext;
    }
    

    public static String verschluesselterText(String klartext, String schluessel){
        String geheimtext = "";
        String ABC = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
        String abc = "abcdefghijklmnopqrstuvwxyz";

        int zahl;
        int zahl2;
        int zahl3;
        int zahl4;

        int neueZahl;
        char neuesZeichen = 'A';

        for (int i =0; i < klartext.length(); i = i+1){

            zahl = ABC.indexOf(klartext.charAt(i));
            zahl2 = abc.indexOf(klartext.charAt(i));
            zahl3 = ABC.indexOf(schluessel.charAt(i));

            if (klartext.charAt(i) >= (int) 'A' && klartext.charAt(i) <= (int) 'Z') {       //Untersucht, ob der Buchstabe ein Großbuchstabe ist.
                neueZahl = zahl + zahl3;
                if (neueZahl > 25){
                    neueZahl = neueZahl - 26;
                }
                neuesZeichen = ABC.charAt(neueZahl);
            }
            
            if (klartext.charAt(i) >= (int) 'a' && klartext.charAt(i) <= (int) 'z') {       //Untersucht, ob der Buchstabe ein Kleinbuchstabe ist.
                neueZahl = zahl2 + zahl3;
                if (neueZahl > 25){
                    neueZahl = neueZahl - 26;
                }
                neuesZeichen = abc.charAt(neueZahl);
            }
            geheimtext = geheimtext + neuesZeichen;
        }
        return geheimtext;
    }
    
    public static String entschluesselterText(String geheimtext, String schluessel){
        String klartext = "";
        String ABC = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
        String abc = "abcdefghijklmnopqrstuvwxyz";

        int zahl;
        int zahl2;
        int zahl3;

        int neueZahl;
        char neuesZeichen = 'A';

        for (int i =0; i < geheimtext.length(); i = i+1){

            zahl = ABC.indexOf(geheimtext.charAt(i));
            zahl2 = abc.indexOf(geheimtext.charAt(i));
            zahl3 = ABC.indexOf(schluessel.charAt(i));

            if (geheimtext.charAt(i) >= (int) 'A' && geheimtext.charAt(i) <= (int) 'Z') {       //Untersucht, ob der Buchstabe ein Großbuchstabe ist.
                neueZahl = zahl - zahl3;
                if (neueZahl < 0){
                    neueZahl = neueZahl + 26;
                }
                neuesZeichen = ABC.charAt(neueZahl);
            }
            
            if (geheimtext.charAt(i) >= (int) 'a' && geheimtext.charAt(i) <= (int) 'z') {       //Untersucht, ob der Buchstabe ein Kleinbuchstabe ist.
                neueZahl = zahl2 - zahl3;
                if (neueZahl < 0){
                    neueZahl = neueZahl + 26;
                }
                neuesZeichen = abc.charAt(neueZahl);
            }
            klartext = klartext + neuesZeichen;
        }
        return klartext;
    }

    public static String bereinigterText(String text){
        //Umlaute werden aus dem Text entfernt.
        String textNeu =  "";
        char zeichen;
        int neuesZeichen;
        char neuesZeichen2;
        for (int i = 0; i < text.length() ; i = i+1){
            zeichen = text.charAt(i);

            if ( zeichen == 'Ä') {
                textNeu = textNeu + "AE";
            }else
            if (  zeichen == 'ä' ){
                textNeu = textNeu + "ae";
            }else
            if (  zeichen == 'Ö' ){
                textNeu = textNeu + "OE";
            }else
            if (  zeichen == 'ö' ){
                textNeu = textNeu + "oe";
            }else
            if ( zeichen == 'Ü') {
                textNeu = textNeu + "UE";
            }else
            if (  zeichen == 'ü' ){
                textNeu = textNeu + "ue";
            }else
            if (  zeichen == 'ß' ){
                textNeu = textNeu + "ss";
            }else {
                textNeu = textNeu + zeichen;   
            }
        }
        return textNeu;
    }

    public static String Schluesselvermehrung(String text,String schluessel){
        //Der Schluessel wird an die länge des klartextes / geheimtextes angepasst.
        while (text.length() > schluessel.length()){
            schluessel = schluessel + schluessel;
        }
        return schluessel;
    }

    public static String Schluesselbereinigung(String schluessel){
        //Der Schluessel wird von Kleinbuchstaben bereinigt.
        String schluessel2 = schluessel;
        int schluessel3;
        schluessel = "";

        for (int i = 0; i < schluessel2.length() ; i = i+1){
            if (schluessel2.charAt(i) > 96 && schluessel2.charAt(i) < 123){
                schluessel3 = (int) schluessel2.charAt(i) - 32;
                schluessel = schluessel + (char) schluessel3;
            }
            else {
                schluessel = schluessel + schluessel2.charAt(i);
            }

        }
        return schluessel;
    }
    
    public static void main(String [] args){
        String klartext = "AbCÖ";
        String schluessel = "Bbb";
        String geheimtext = "";
        
        System.out.println("klartext = "+klartext);
        System.out.println("schluessel = "+schluessel);
        System.out.println("geheimtext = "+geheimtext);
        System.out.println("____________");
        klartext = bereinigterText(klartext);
        System.out.println("klartext ohne Umlaute = "+klartext);
        schluessel = bereinigterText(schluessel);
        System.out.println("schluessel ohne Umlaute = "+schluessel);
        schluessel = Schluesselvermehrung(klartext,schluessel);
        System.out.println("schluessel an länge des klartextes angepasst = "+schluessel);
        schluessel = Schluesselbereinigung(schluessel);
        System.out.println("schluessel ohne Kleinbuchstaben = "+schluessel);
        geheimtext = verschluesselterText(klartext,schluessel);
        System.out.println("geheimtext = "+geheimtext);
        System.out.println("_____________________________________________________");
        
        schluessel = "Bbb";
        System.out.println("schluessel = Bbb");
        System.out.println("geheimtext = "+geheimtext);
        System.out.println("____________");
        schluessel = bereinigterText(schluessel);
        System.out.println("schluessel ohne Umlaute = "+schluessel);
        schluessel = Schluesselvermehrung(geheimtext,schluessel);
        System.out.println("schluessel an länge des geheimtextes angepasst = "+schluessel);
        schluessel = Schluesselbereinigung(schluessel);
        System.out.println("schluessel ohne Kleinbuchstaben = "+schluessel);
        klartext = entschluesselterText(geheimtext,schluessel);
        System.out.println("klartext = "+klartext);
    }
}
