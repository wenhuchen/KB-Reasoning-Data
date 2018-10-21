# KB-Reasoning-Data

1. Underlying KB triples are stored in kb_env_rl.txt (make sure to mask out the missing relations on the fly)
2. Pre-trained Embedding for entity and relations are stored in relation2vec.bern and entity2vec.bern
3. Evaluation tasks are stored in evaluate_task.txt
4. Trainining positive and negative triples are stored in whole_train_pos_neg.txt
5. Validating and Testing triples are stored in whole_sort_test.txt and whole_sort_val.txt


# Data Format

For example in FB dataset whole_train_pos_neg.txt, we have 

```
sports@sports_team@sport#/m/03c0t9#/m/018w8:-1#/m/01gqfm:-1#/m/01lb14:-1#/m/02vx4:1#/m/02y8z:-1#/m/03_8r:-1#/m/06f41:-1#/m/06z6r:-1#/m/07bs0:-1#/m/07jbh:-1#/m/0bynt:-1
```
The first term "sports@sports_team@sport" denotes the relation of interests (@ does not act as separator here), the firts entity "/m/03c0t9" is the start entity, and the rest entities are the ranked candidates with 1 denoting connected entity, and -1 denoting disconnected entity. The MAP is calculated based on the rank of the connected candidate. For example, if /m/02vx4 ranks 3rd place, then MAP=1 / (1 + 3)=0.25. 
