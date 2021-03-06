# Document Level Models
- Prediction using Documents -> Document level LM, Document Classification
- what context to incorporate
    - Use topic modeling (mikolov and zweig)
    - Use BOW of previous sentences (wang and cho 2016)
- Self-Attention/Transformers Across sentences
    - Simply self-attend to all previous words in the document(eg: Voita et al 2018)
    - Can relatively simply use document level context
    - Computation is quadratic in sequence length (Too much)
- Transformer-XL (dai et al 2019)
    - Truncated BPTT + Transformer
    - BPTT -> Backpropogation through time
    - Attend to fixed vectors from the previous sentence
    - Like truncated backprop through time for RNNs, can use previous states but not backprop into them
- Sparse Transformers (Child et al 2019)
    - "stride", attend to every n previous states
- How to evaluate document Level Models
    - Perplexity
    - Sentence Scrambling (Barzilay and Lapata 2008)
    - Final Sentence prediction (Mostafazadeh et al 2016)
    - Final word prediction (papernot et al 2016)
# Entity Coreference
- Coreference is a structured prediction problem
    - Possible cluster structure are exponential in number
- Models are design to approximate, explore the space
- Mention Pair Models: Classify the coreference relation between every 2 mentions
    - May result in conflicts in transitivity
    - Dont not capture entity/cluster level features
- Entity mention models
    - Create an instance between a mention and a previous cluster
    - Can create cluster level features
    - Cluster level features are difficult to create
- Advantages of NNs for coreference
    - Learn the features
    - Train towards the metric
    - Clustering and Mention Detection
- Coreference Resolution w/ entity level distributed representation (Clark and manning et al 2015)
- Deep Reinforcement Learning for Mention ranking coreference models (Clark and manning et al 2016)
- End-to-end Neural Coreference (Lee et al 2017)
    - Can we represent all features with a more typical embeddings way
    - Can neural network can go back to mention detection
    - Build mention representation from the word representation
    - Coreference model is similar to mention ranking
    - MLE trained
- Co-reference aware QA models (Dhingra et al 2017)
## Discourse Parsing
- Document Problems
    - Parse a piece of text into relations between discourse units
    - Rhetorical Structure theory (Marcu 2000)
- Recursive Deep models for discourse parsing li et al 2014
- Discourse parsing with attention based hierarchical networks li et al 2016
