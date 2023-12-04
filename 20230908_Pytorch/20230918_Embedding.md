### pytorch의 Embedding
- 임베딩 층(embedding layer)을 만들어 훈련 데이터로부터 처음부터 임베딩 벡터를 학습하는 방법
- 미리 사전에 훈련된 임베딩 벡터(pre-trained word embedding)들을 가져와 사용하는 방법
- `nn.Embedding()`를 사용하여 구현

### 사전 훈련된 워드 임베딩
- 해당 문제에 특화된 것은 아니지만 보다 일반적이고 보다 많은 훈련 데이터로 이미 `Word2Vec`이나 `GloVe` 등으로 학습되어져 있는 임베딩 벡터들을 사용하는 것이 성능의 개선을 가져올 수 있습니다.
- 토치텍스트는 영어 단어들의 사전 훈련된 임베딩 제공
- 사전 훈련된 워드 임베딩
```
fasttext.en.300d
fasttext.simple.300d
glove.42B.300d
glove.840B.300d
glove.twitter.27B.25d
glove.twitter.27B.50d
glove.twitter.27B.100d
glove.twitter.27B.200d
glove.6B.50d
glove.6B.100d
glove.6B.200d
glove.6B.300d
```