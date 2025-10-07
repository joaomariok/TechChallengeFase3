# FIAP Tech Challenge - Fine-Tuning para Geração de Descrições de Produtos

## Sobre o Projeto

Este projeto faz parte do **FIAP Tech Challenge** e tem como objetivo desenvolver um modelo de inteligência artificial capaz de gerar descrições de produtos automaticamente a partir de seus títulos. Utilizamos técnicas avançadas de fine-tuning em um modelo de linguagem para criar uma solução eficiente e escalável.

## Tecnologias Utilizadas

- **Python** - Linguagem de programação principal
- **PyTorch** - Framework de deep learning
- **Unsloth** - Acelerador de fine-tuning (2x mais rápido)
- **Transformers** (Hugging Face) - Biblioteca para modelos de linguagem
- **PEFT** (Parameter-Efficient Fine-Tuning) - Para treinamento eficiente
- **LoRA** (Low-Rank Adaptation) - Técnica de fine-tuning
- **Google Colab** - Ambiente de execução

## Dataset

### Estrutura dos Dados
O dataset original continha:
- **2.2 milhões+** de produtos
- Colunas: `title` (título) e `content` (descrição)

### Processamento de Dados
1. **Limpeza**:
   - Remoção de títulos e descrições vazias
   - Eliminação de descrições duplicadas
   - Normalização de texto

2. **Pré-processamento**:
   - Formatação no padrão instruction-following
   - Criação de conjuntos de treino (150k) e teste (30k)

## Modelo

### Arquitetura
- **Modelo Base**: `Llama 3.2 3B` (3 bilhões de parâmetros)
- **Otimização**: 4-bit quantization para eficiência de memória
- **Fine-tuning**: LoRA (apenas 0.38% dos parâmetros treinados)

### Especificações Técnicas
- **Sequência máxima**: 128 tokens
- **Batch size**: 32
- **Épocas**: 1
- **Learning rate**: 3e-4
- **Dispositivo**: GPU Tesla T4 (Google Colab)

## Como Executar

### Pré-requisitos
- Google Colab (recomendado) ou ambiente Python
- GPU com pelo menos 12GB de VRAM
- Acesso ao Google Drive

### Passos para Execução

1. Abra o notebook FIAP_Tech_Challenge_Amazon_Fine_Tunning-150k-treino.ipynb
2. Execute as células sequencialmente
3. O processo é automático: limpeza, treinamento e teste

## Otimizações Implementadas

### Para Velocidade

**Unsloth**: Aceleração 2x no fine-tuning
**4-bit Quantization**: Redução de uso de memória
**LoRA**: Treinamento apenas de parâmetros específicos
**Batch Size Otimizado**: Balanceamento entre velocidade e memória

### Para Qualidade

**Limpeza Rigorosa**: Dados de alta qualidade
**Formatação Padronizada**: Estrutura instruction-following
**Regularização**: Dropout para evitar overfitting
**Early Stopping**: Prevenção de overtraining

## Resultados

### Métricas de Treinamento

**Loss Final**: ~2.28
**Tempo de Treinamento**: ~17 horas
**Parâmetros Treinados**: 12M de 3.2B (0.38%)
**Uso de Memória**: ~13GB GPU

## Equipe

- Carolina de Marco Pessoa
- Jadson Dantas de Medeiros Junior
- João Mário Künzle Ribeiro Magalhães
- Marcelo Guedes de Barros