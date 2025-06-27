# 🏨 Sistema de Hospedagem - Hotel Reservation System

[![.NET](https://img.shields.io/badge/.NET-6.0-purple.svg)](https://dotnet.microsoft.com/)
[![C#](https://img.shields.io/badge/C%23-239120?style=flat&logo=c-sharp&logoColor=white)](https://docs.microsoft.com/pt-br/dotnet/csharp/)
[![DIO](https://img.shields.io/badge/DIO-Trilha_.NET-ff6b35?style=flat)](https://www.dio.me)

## 📋 Sobre o Projeto

Sistema de gerenciamento de reservas hoteleiras desenvolvido em C# como parte do desafio da **Trilha .NET da DIO**. O sistema permite realizar reservas, calcular valores de diárias com desconto progressivo e validar a capacidade das suítes.

### 🎯 Funcionalidades Implementadas

- ✅ Cadastro de hóspedes com nome e sobrenome
- ✅ Gerenciamento de suítes com diferentes tipos e capacidades
- ✅ Sistema de reservas com validação de capacidade
- ✅ Cálculo automático de valores com desconto para estadias longas
- ✅ Tratamento de exceções para reservas inválidas

## 🏗️ Arquitetura do Sistema

O projeto segue uma arquitetura orientada a objetos com três classes principais que se relacionam para formar o sistema de hospedagem:

### 📊 Diagrama de Classes

![Diagrama de Classes do Sistema](diagrama_classe_hotel.png)

### 🏛️ Estrutura das Classes

#### 👤 Classe `Pessoa`
Representa um hóspede do hotel com as seguintes propriedades:
- **Nome**: Nome do hóspede
- **Sobrenome**: Sobrenome do hóspede  
- **NomeCompleto**: Propriedade computada que retorna nome + sobrenome em maiúsculas

#### 🏠 Classe `Suite`
Representa uma suíte do hotel com:
- **TipoSuite**: Tipo da suíte (Standard, Premium, Deluxe, etc.)
- **Capacidade**: Número máximo de hóspedes
- **ValorDiaria**: Valor da diária em decimal

#### 📅 Classe `Reserva`
Classe principal que gerencia as reservas, contendo:
- **Hospedes**: Lista de pessoas hospedadas
- **Suite**: Suíte reservada
- **DiasReservados**: Quantidade de dias da reserva

## 📋 Regras de Negócio Implementadas

### ✅ Validações Obrigatórias

1. **Validação de Capacidade**: Não é possível realizar reserva com mais hóspedes do que a capacidade da suíte
   - ❌ Suíte para 2 pessoas + 3 hóspedes = `ArgumentException`

2. **Cálculo de Quantidade**: O método `ObterQuantidadeHospedes()` retorna o total de hóspedes da reserva

3. **Cálculo de Valor**: O método `CalcularValorDiaria()` calcula: `Dias × Valor da Diária`

4. **Desconto Progressivo**: Reservas ≥ 10 dias recebem **10% de desconto** automaticamente

### 💰 Exemplo de Cálculo de Preços

```
Suíte Premium: R$ 30,00/dia
├── 5 dias: R$ 150,00 (sem desconto)
├── 10 dias: R$ 270,00 (com 10% desconto)
└── 15 dias: R$ 405,00 (com 10% desconto)
```

## 🚀 Como Executar

### 📋 Pré-requisitos

- [.NET 6.0 SDK](https://dotnet.microsoft.com/download/dotnet/6.0) ou superior
- IDE de sua preferência (Visual Studio, VS Code, Rider)

### 🔧 Instalação e Execução

1. **Clone o repositório**:
   ```bash
   git clone https://github.com/seu-usuario/dio-hospedagem-csharp.git
   cd dio-hospedagem-csharp
   ```

2. **Execute o projeto**:
   ```bash
   dotnet run
   ```

3. **Ou compile e execute**:
   ```bash
   dotnet build
   dotnet ./bin/Debug/net6.0/DesafioProjetoHospedagem.exe
   ```

### 🖥️ Exemplo de Saída

```
Hóspedes: 2
Valor diária: R$ 150,00
```

## 🔧 Estrutura do Projeto

```
📦 DesafioProjetoHospedagem/
├── 📁 Models/
│   ├── 📄 Pessoa.cs          # Classe que representa um hóspede
│   ├── 📄 Suite.cs           # Classe que representa uma suíte
│   └── 📄 Reserva.cs         # Classe principal de reservas
├── 📄 Program.cs             # Ponto de entrada da aplicação
├── 📄 DesafioProjetoHospedagem.csproj
└── 📄 README.md
```

## 🤝 Contribuições

Contribuições são bem-vindas! Para contribuir:

1. Faça um fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 👨‍💻 Autor

Desenvolvido como parte do desafio da **Trilha .NET** da [Digital Innovation One](https://www.dio.me).

---

⭐ **Gostou do projeto? Deixe uma estrela!** ⭐
