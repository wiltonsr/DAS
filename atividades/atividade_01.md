# Aula 1 - Introdução ao framework JUnit4.

### Para responder às questões abaixo, considere o framework de testes JUnit4.

### **Exercício 1: Defina os seguintes termos que são muito utilizados em testes e apresente como eles são definidos em JUnit.**

#### **Asserções**
```
Uma assertiva, segundo a definição da Oracle, é uma confirmação que permite que sejam
testadas as premissas que são utilizadas no seu programa. Por exemplo, se você escrever
um método que calcula a velocidade de uma partícula, você pode afirmar que a velocidade
calculada é menor que a velocidade da luz.

Exemplo:

@Test
public void assertThat(){
    double CalculatesSpeedOfLight(double distance, double time);
    assertThat(CalculateSpeedOfLight(100.3, .5) < 299792458.0);
}
```

#### **Teste**
```
Teste de software é a etapa de controle de qualidade, serve para assegurar que o software
está contemplando todas as funcionalidades esperadas e que estas estão funcionando corretamente.

Exemplo:

import junit.framework.TestCase;

@Test
public class TesteSoma extends TestCase{
  private int x = 4;
  private int y = 8;

  public void testSoma(){
    int z = x + y;
    assertEquals(12, z);
  }
}
```

#### **Caso de teste**
```
Um caso de teste traz a descrição do que deve ser testado, ou seja, são detalhados os valores
de entrada, restrições de execução e o resultado que se espera na saída do mesmo.

Exemplo:

Funcionalidade: Somar dois inteiros.
Etapas: Digitar dois valores inteiros.
Resultado Esperado: A soma dos dois valores inteiros.
Ambiente de Teste: Máquina de desenvolvimento.
```

#### **Suite de testes**
```
Suíte de teste é um recipiente que contém um conjunto de testes que ajuda os testadores
a executar e informar o status de execução do teste. As suítes de teste são formadas por
casos de testes específicios que podem pertencer a uma ou mais suítes. Estes testes podem
ser unitários, funcionais, de carga, estresse e etc.

Exemplo:

import org.junit.runner.RunWith;
import org.junit.runners.Suite;

@RunWith(Suite.class)
@Suite.SuiteClasses({
  TestFeatureLogin.class,
  TestFeatureLogout.class,
  TestFeatureNavigate.class,
  TestFeatureUpdate.class
})

public class FeatureTestSuite {
  // the class remains empty,
  // used only as a holder for the above annotations
}
```

### **Exercício 2: Apresente o projeto estrutural do framework.**
```
Suponhamos que tenhamos uma classe chamada 'ClassA' e desejamos testar unidades dentro
desta classe, para fazer isso, devemos criar uma classe de teste com nossos casos de teste,
vamos chamar isso 'TestClassA'. TestClassA importará as classes relevantes da biblioteca JUnit
e será compilado com a estrutura JUnit. Depois disso, usaremos o JUnit tool runner fornecido pela
estrutura para executar a classe e verificar falhas. O tool runner verificará se uma unidade falhará
ou passará no teste, então emitirá os resultados do teste mostrando como e onde (número da linha) um
teste falhou. O desenvolvedor deve então verificar a falha e mudar ClassA quando
apropriado. Depois disso, a classe de teste deve ser executada com o corretor de ferramenta novamente
para garantir que as alterações feitas tenham ativado a funcionalidade para a (s) unidade (s).
```

### **Exercício 3: O que é independência de testes e como ela é garantida pelo JUnit?**
```
Independência nos testes se dá ao nível de quem desenvolve os testes da aplicação.
Podendo ser:
- Próprio desenvolvedor;
- Outro desenvolvedor;
- Equipe de teste;
- Empresa de teste.
```

### **Exercício 4: O que é o um TestRunner do JUnit? E quais os runners existentes?**
```
Um JUnit Runner é uma classe que extende a classe Runner abstrata da JUnit. Os runners
são usados para executar as classes de teste. O Runner que deve ser usado para executar
um teste pode ser configurado usando a anotação @RunWith.
Existem alguns runners providos pelo próprio JUnit:
- Suite;
- Parameterized;
- Categories;
- Enclosed;
Além de podermos criar nossos próprios runners:
- Third party Runners
```
