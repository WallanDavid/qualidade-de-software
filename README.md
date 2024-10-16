Questão 1
Quantos casos de teste são necessários para cobrir todas as condições (verdadeiras e falsas)?

Código:

plaintext
Copiar código
READ A
READ B
READ C
IF C > A THEN
    IF C > B THEN
        PRINT “C deve ser menor que pelo menos um número”
    ELSE
        PRINT “Vá para o próximo passo”
    ENDIF
ELSE
    PRINT “B pode ser menor do que C”
END IF
Resposta: Para cobrir todas as condições do código, precisamos pensar nas possíveis combinações de valores para C, A e B:

C > A (verdadeiro) e C > B (verdadeiro) → "C deve ser menor que pelo menos um número".
C > A (verdadeiro) e C > B (falso) → "Vá para o próximo passo".
C > A (falso) → "B pode ser menor do que C".
Então, precisamos de 3 casos de teste.

Questão 2
Quais os testes que você pensou?

Teste 1: C = 5, A = 3, B = 4 → C é maior que A e B (saída: "C deve ser menor que pelo menos um número").
Teste 2: C = 5, A = 3, B = 6 → C é maior que A, mas não é maior que B (saída: "Vá para o próximo passo").
Teste 3: C = 2, A = 3, B = 4 → C não é maior que A (saída: "B pode ser menor do que C").
Questão 3
Você vê algum problema no código?

Sim, o código funciona, mas a mensagem "B pode ser menor do que C" no bloco ELSE pode ser enganosa. Esse bloco é executado sempre que C não é maior que A, e não necessariamente significa que B é menor que C.

Questão 4
Como faço para obter o nome de todas as pessoas nascidas a partir de 1980 da coleção abaixo? (escreva o código C#)

Coleção:

csharp
Copiar código
class Pessoa {
    public string Nome { get; set; }
    public DateTime DataNascimento { get; set; }
}

List<Pessoa> pessoas = new List<Pessoa> {
    new Pessoa { Nome = "João", DataNascimento = new DateTime(1975, 5, 23) },
    new Pessoa { Nome = "Maria", DataNascimento = new DateTime(1985, 11, 12) },
    new Pessoa { Nome = "Pedro", DataNascimento = new DateTime(1990, 3, 9) },
    new Pessoa { Nome = "Ana", DataNascimento = new DateTime(1979, 8, 14) }
};
Código C#:

csharp
Copiar código
var nascidosApos1980 = pessoas
    .Where(p => p.DataNascimento.Year >= 1980)
    .Select(p => p.Nome)
    .ToList();

foreach (var nome in nascidosApos1980)
{
    Console.WriteLine(nome);
}
