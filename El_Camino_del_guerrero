using System;

class Guerrero
{
    static int fuerza = 10;
    static int resistencia = 10;
    static int energia = 100;
    static int experiencia = 0;
    static int nivel = 1;
    static Random random = new Random();

    static void Main()
    {
        int opcion;
        do
        {
            MostrarMenu();
            opcion = Convert.ToInt32(Console.ReadLine());

            switch (opcion)
            {
                case 1:
                    Entrenar("fuerza");
                    break;
                case 2:
                    Entrenar("resistencia");
                    break;
                case 3:
                    Descansar();
                    break;
                case 4:
                    Pelear();
                    break;
                case 5:
                    VerEstado();
                    break;
                case 6:
                    Console.WriteLine("¡Saliendo del simulador de entrenamiento!");
                    break;
                default:
                    Console.WriteLine("Opción no válida.");
                    break;
            }

            RevisarNivel();

        } while (opcion != 6);
    }

    static void MostrarMenu()
    {
        Console.WriteLine("\n=== MENÚ PRINCIPAL ===");
        Console.WriteLine("1. Entrenar Fuerza");
        Console.WriteLine("2. Entrenar Resistencia");
        Console.WriteLine("3. Descansar");
        Console.WriteLine("4. Pelear");
        Console.WriteLine("5. Ver Estado");
        Console.WriteLine("6. Salir");
        Console.Write("Elige una opción: ");
    }

    static void VerEstado()
    {
        Console.WriteLine($"\n--- Estado del Guerrero ---");
        Console.WriteLine($"Nivel: {nivel}");
        Console.WriteLine($"Fuerza: {fuerza}");
        Console.WriteLine($"Resistencia: {resistencia}");
        Console.WriteLine($"Energía: {energia}");
        Console.WriteLine($"Experiencia: {experiencia}");
    }

    static void Entrenar(string stat)
    {
        Console.Write("¿Cuántas horas quieres entrenar? (1-6): ");
        int horas = Convert.ToInt32(Console.ReadLine());

        if (horas < 1 || horas > 6)
        {
            Console.WriteLine("Horas inválidas. Elige entre 1 y 6.");
            return;
        }

        int energiaNecesaria = horas * 10;

        if (energia < energiaNecesaria)
        {
            Console.WriteLine("No tienes suficiente energía para entrenar.");
            return;
        }

        energia -= energiaNecesaria;

        if (stat == "fuerza")
        {
            fuerza += horas * 2;
            experiencia += horas * 5;
            Console.WriteLine($"Has entrenado fuerza por {horas} horas. +{horas * 2} fuerza, +{horas * 5} XP.");
        }
        else if (stat == "resistencia")
        {
            resistencia += horas * 2;
            experiencia += horas * 5;
            Console.WriteLine($"Has entrenado resistencia por {horas} horas. +{horas * 2} resistencia, +{horas * 5} XP.");
        }
    }

    static void Descansar()
    {
        Console.Write("¿Cuántas horas quieres descansar? (1-6): ");
        int horas = Convert.ToInt32(Console.ReadLine());

        if (horas < 1 || horas > 6)
        {
            Console.WriteLine("Horas inválidas. Elige entre 1 y 6.");
            return;
        }

        int energiaRecuperada = horas * 15;
        energia += energiaRecuperada;

        if (energia > 100) energia = 100;

        Console.WriteLine($"Has descansado por {horas} horas. +{energiaRecuperada} energía.");
    }

    static void Pelear()
    {
        if (energia < 30)
        {
            Console.WriteLine("Estás demasiado cansado para pelear. Necesitas al menos 30 de energía.");
            return;
        }

        energia -= 30;

        int enemigoNivel = random.Next(nivel, nivel + 3);
        int poderJugador = fuerza + resistencia + random.Next(1, 11);
        int poderEnemigo = enemigoNivel * 15 + random.Next(1, 21);

        Console.WriteLine($"\nTe enfrentas a un enemigo de nivel {enemigoNivel}...");

        Console.WriteLine($"Tu poder total: {poderJugador}");
        Console.WriteLine($"Poder del enemigo: {poderEnemigo}");

        if (poderJugador >= poderEnemigo)
        {
            int xpGanada = enemigoNivel * 10;
            experiencia += xpGanada;
            Console.WriteLine("¡Ganaste la pelea! Ganas " + xpGanada + " XP.");
        }
        else
        {
            Console.WriteLine("Perdiste la pelea... No ganaste experiencia.");
            energia -= 10;
            if (energia < 0) energia = 0;
        }
    }

    static void RevisarNivel()
    {
        int umbralSubida = nivel * 100;
        if (experiencia >= umbralSubida)
        {
            nivel++;
            experiencia = experiencia - umbralSubida;
            fuerza += 5;
            resistencia += 5;
            Console.WriteLine($"\n*** ¡Subiste a nivel {nivel}! ***");
            Console.WriteLine("+5 fuerza, +5 resistencia.");
        }
    }
}
