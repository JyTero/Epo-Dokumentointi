<h3>Epo Dokumentoinitehtävä -palautus</h3>
<p>Tehtävänannossa käsketään tekemään yhtenäinen palautus, jossa koko tiimi kommentoi samaa samalla tavalla ja palauttaa saman palautuksen. Ymmärsin, että palautuksen pitää olla yhdessä luodusta desgn pattern -esimerkistä, tiimini tapauksessa adapterista. Kommentoin koodin, koodi alla, ja pistin tiimille jakoon. En tosin muistanut manita mistään tästä muulle tiimille, joka sitemin rupesin työstämään tehtävää. En ollut nähnyt aiheesta käytyä keskustelua, enkä siksi mitenkään osallistunut muun tiimin palautukseen.</p>
<p>Irtopisteiden toivossa palautan tämä vaikka se onkin erivä muusta ryhmästä. Yrittänyttä ei laiteta jne.</p>

```markdown
using System;

namespace ConsoleApp2
{
    /// <summary>
    /// A program for figuring out, how much sugar, yeast and water you need. Input in metric, output in American units.
    /// </summary>
    class Program
    {
        public static float Sugar;
        public static float Yeast;
        public static float Water;

        public static void Main()
        {
            Console.WriteLine("How much sugar u need in kilos");
            string input = Console.ReadLine();
            Sugar = ParseInputs(input);

            Console.WriteLine("How much Yeast u need in grams");
            input = Console.ReadLine();
            Yeast = ParseInputs(input);

            Console.WriteLine("How much Water u need in Liters");
            input = Console.ReadLine();
            Water = ParseInputs(input);

            ConvertToUSA();

            Console.WriteLine("For strong homemade brew you need " + Round(Sugar) + " pound of Sugar and " + Round(Yeast) + " ounces of yeast and mix with " + Round(Water) + " pounds of waterfl");
        }
        /// <summary>
        /// Input will changed from string to float for later conversion
        /// </summary>
        /// <param name="input">String as user typed it </param>
        /// <returns>Returns input as a float</returns>
        public static float ParseInputs(string input)
        {
            float inputFloat;
            float.TryParse(input, out inputFloat);
            return inputFloat;
        }

        /// <summary>
        /// Converts units from metric to imperial
        /// </summary>
        public static void ConvertToUSA()
        {
            Sugar = Sugar * 2.205f; //pound
            Yeast = Yeast / 28.35f; //ounces
            Water = Water * 4.227f;//cup
        }

        /// <summary>
        /// rounds the number for more pleasant output
        /// </summary>
        /// <param name="input">Float of ammount if ingridient</param>
        /// <returns>Returns neater looking version of the number</returns>
        public static float Round(float input)
        {
            float fc = (float)Math.Round(input * 100f) / 100f;
            return fc;
        }

    }
}

```
