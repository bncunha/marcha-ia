# 🧠 Identificação de Desvios de Marcha com Inteligência Artificial

Este repositório contém o código desenvolvido para o Trabalho de Conclusão de Curso (TCC) de **Bruno da Silva Cunha**, intitulado  
**“Aplicação de Modelos de Aprendizado de Máquina na Identificação de Desvios de Marcha Humana”**, apresentado ao curso de Ciência da Computação da Universidade Federal do Espírito Santo (UFES).

O objetivo do projeto é **avaliar a aplicabilidade de técnicas de inteligência artificial na identificação de desvios de marcha humana** a partir de vídeos, utilizando visão computacional e aprendizado de máquina.

---

## 🎯 Objetivo

A pesquisa busca verificar se **modelos de aprendizado de máquina** são capazes de **classificar padrões de marcha** como **normais ou anormais**, a partir de vídeos públicos disponíveis no dataset **Gait Abnormality in Video Dataset (GAVD)**.  
A análise combina técnicas de **extração de poses corporais com YOLOv11n-Pose** e **classificação supervisionada** com diferentes algoritmos.

---

## ⚙️ Metodologia

O pipeline do projeto é dividido em três etapas principais:

1. **Obtenção e preparação dos dados**
   - Download e filtragem dos vídeos do dataset GAVD.
   - Seleção de vídeos com visão lateral.
   - Balanceamento entre as classes “normal” e “anormal”.
   - Geração de metadados em CSV.

2. **Extração de poses corporais**
   - Utilização do modelo **YOLOv11n-Pose** para identificar e extrair pontos-chave (keypoints) do corpo em cada frame.
   - Espelhamento de vídeos para uniformizar a direção da marcha.
   - Descarte de vídeos com múltiplas pessoas no frame.
   - Geração de arquivos `.npy` contendo os keypoints de cada vídeo.

3. **Treinamento e análise dos modelos**
   - Geração de *features* estatísticas a partir dos keypoints.
   - Treinamento dos modelos **Logistic Regression**, **LinearSVC**, **Random Forest** e **Gradient Boosting**.
   - Ajuste de hiperparâmetros via **GridSearchCV**.
   - Avaliação com **validação cruzada (StratifiedKFold)** e métricas **F1-Score** e **matriz de confusão**.

---

## 🧩 Principais Tecnologias

- **Python 3.12**
- **YOLOv11n-Pose (Ultralytics)**
- **OpenCV**
- **NumPy / Pandas**
- **Scikit-learn**
- **yt_dlp** (para download automatizado dos vídeos)
- **Google Colab** (ambiente de experimentação)
  
---

## 🔗 Dataset e Código

- Dataset público: [Gait Abnormality in Video Dataset (GAVD)](https://ieeexplore.ieee.org/document/10545787)  
- Modelo de pose: [YOLOv11n-Pose – Ultralytics](https://github.com/ultralytics/ultralytics)  
- Repositório oficial deste projeto: [github.com/bncunha/marcha-ia](https://github.com/bncunha/marcha-ia)
