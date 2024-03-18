# FineTuning_LLAMA2
FineTuning LLAMA2 for medical datasets

<br> I use [this medical dataset](https://huggingface.co/datasets/gamino/wiki_medical_terms/viewer/default/train?p=68) to fine-tune the model.
<br> However, we cannot use this raw dataset directly for training. Hence, we use [this formatted dataset](https://huggingface.co/datasets/aboonaji/wiki_medical_terms_llam2_format) that we can directly use to fine-tune a Llama2 model.
<br> I am using AutoModelForCausalLM from the transformers library to train a causal LM for text generation. 
<br> To reduce the compute and memory usage, we use the 4 bit version of the model. We also turn off cache memory and deactivate accurate computation on the linear layers.
<br> I use AutoTokenizer to tokenize the input text.
<br> I then use the SFTTrainer to fine-tune the pretrained Llama2 model. 
<br> training_loss=1.6542158508300782
<br> I end by asking the fine-tuned model about a disease.
<br>---------------SAMPLE OUTPUT-----------------------------------
<br> <s>[INST] Please tell me about Ascariasis [/INST]  Ascariasis is a parasitic infection caused by the Ascaris lumbricoides roundworm. Unterscheidung between Ascaris suum and Ascaris lumbricoides is difficult, and the two species are often considered to be the same. The infection is caused by the ingestion of infective larvae, which then migrate through the body and can cause a range of symptoms, including:

1. Abdominal pain
2. Diarrhea
3. Vomiting
4. Weight loss
5. Fatigue
6. Anemia
7. Malnutrition

Ascariasis is a common infection worldwide, particularly in areas with poor sanitation and hygiene. The infection is most commonly found in tropical and subtropical regions, where the parasite is more likely to be present in contaminated soil, water, or food.

The diagnosis of Ascariasis is typically made through a combination of physical examination, medical history, and laboratory tests. Laboratory tests may include:

1. Stool examination: A stool sample can be examined for the presence of Ascaris eggs or larvae.
2. Blood tests: Blood tests can be used to measure the levels of anemia or
