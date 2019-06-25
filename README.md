# C#exam
//The purpose of the C# exam was to create a console program which reads data from a .txt file, and allow the user to append data to the //file, aswell as showing the neccesary information on the console window
// PLEASE NOTE THE COMMENTS ARE IN ALL IN DANISH.

using System;

using System.Collections.Generic;

using System.Linq;

using System.Text;

using System.Threading.Tasks;

namespace ByteBusters

{

class Program

{

static void Main(string[] args)

{

int secretvalue;  //her gemmer jeg det tilfældigt generede tal manden skal gætte

Random rnd = new Random(); // her har jeg aktiveret tilfældighedsgeneratoren

int rigtige = 0; // Jeg har oprettet to tælle variabler

int antal;

int svar;

string binært; // variablen binært bruges til at gemme den binære version af tallet i secretvalue

Console.WriteLine( // Her indsætter jeg det tekst jeg gerne vil have frem i konsollen. \n indikere en ny linje i konsollen

"Christian Mørk er altid på talentjagt" +

"\nChristian Mørk ønsker dig held og lykke med spillet." +

"\nVinder du, får du en lille præmie." +

"\nDe bedste hilsener fra Christian Mørk." +

"\nOg så er vi i gang... " +

"\n");

for (antal = 1; antal < 6; antal++) // her startes mit for loop

{

secretvalue = rnd.Next(0, 129); // jeg trækker et tal ud fra tilfældighedsgeneratoren

//og gemmer det i variablen secretvalue

binært = Convert.ToString(secretvalue, 2);

Console.WriteLine(binært); // her udskriver jeg værdien gemt i binært i konsollen

svar = Convert.ToInt32(Console.ReadLine()); //her gemmer jeg tastetrykkene og convertere dem til en integer som jeg gemmer i variablen svar

if (svar == secretvalue ) // her startes mit If statement

{

rigtige++; // ++ betyder at den ligger 1 til, hver gang at svar er lig med secretvalue

Console.WriteLine("rigtigt");

if(rigtige >=3)

{

Console.WriteLine(

"Tillykke, du har vundet!" +

"\nKontakt mig på telefon 0x24688E8" +

"\n\nVenlig hilsen Christian" +

"\n\nFortsat god festival og husk nu at få din premie!"

);

}

}

else

{ // mit Else statement træder i kræft hvis mit IF statement IKKE gør

Console.WriteLine("forkert");

}

Console.WriteLine("antal {0}", antal);

}

if(antal == 6)

{

Console.WriteLine("" +

"\nDu ramte rigtigt {0} gange og mangler derfor {1} rigtige svar for at vinde" +

"\nTak fordi du spillede med. Fortsat god festival!", rigtige, 3 - rigtige);

}

Console.ReadKey();

}

}

}
