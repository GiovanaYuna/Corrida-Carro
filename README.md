# Corrida-Carro
using System;
using System.Collections.Generic;

// Classe base
abstract class Veiculo
{
    public string Nome { get; set; }
    public int VelocidadeMaxima { get; set; }

    public Veiculo(string nome, int velocidadeMaxima)
    {
        Nome = nome;
        VelocidadeMaxima = velocidadeMaxima;
    }

    // Método polimórfico
    public abstract void Correr();
}

// Subclasse Carro
class Carro : Veiculo
{
    public Carro(string nome, int velocidadeMaxima) : base(nome, velocidadeMaxima) { }

    public override void Correr()
    {
        Console.WriteLine($"{Nome} (Carro) está correndo a {VelocidadeMaxima} km/h!");
    }
}

// Subclasse Moto
class Moto : Veiculo
{
    public Moto(string nome, int velocidadeMaxima) : base(nome, velocidadeMaxima) { }

    public override void Correr()
    {
        Console.WriteLine($"{Nome} (Moto) está acelerando a {VelocidadeMaxima} km/h!");
    }
}

// Subclasse Bicicleta
class Bicicleta : Veiculo
{
    public Bicicleta(string nome, int velocidadeMaxima) : base(nome, velocidadeMaxima) { }

    public override void Correr()
    {
        Console.WriteLine($"{Nome} (Bicicleta) está pedalando a {VelocidadeMaxima} km/h!");
    }
}

// Programa principal
class Program
{
    static void Main()
    {
        List<Veiculo> corrida = new List<Veiculo>()
        {
            new Carro("Ferrari", 300),
            new Moto("Yamaha", 180),
            new Bicicleta("Caloi", 40)
        };

        Console.WriteLine("🏁 Início da corrida!\n");
        foreach (var veiculo in corrida)
        {
            veiculo.Correr(); // Polimorfismo em ação
        }
    }
}
