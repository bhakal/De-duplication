# De-duplication
Approach to solve de-duplication problem

Our aim is to train a model that helps us to identify the unique patients in a given dataset.
We have given four features, namely “fn”, “dob”, “gn”, “ln” which denotes the “First-name”, “Date-of-Birth”, “Gender”, “Last-name” respectively.

We will see that if any of the feature like “dob”, or “gn” is different then the patient corresponding to that feature is considered to be unique. Because Date-of-birth and Gender information provided in the dataset are assumed to be true.
Next we will compare each record with the other records of same “dob” as well as “gn”.And we will assign binary digits to First-name.

After giving binary values to first name we will remove all values that have 0 value in first-name and will work with records that have 1 in the first name.
Now we have to compare all the records that have dob, gn, fn same with varying last-name.
Here we will compare each record with others and will assign the weight against each pair by using the method called “jarowinkler”.

Now we will cluster the records based on the value of weight. If weight is =1 that means, all records with weight 1 are totally similar and can be considered as unique overall.
Rest weight falling in particular cluster are considered to be unique overall.
We will repeat the same thing for First-name value=0.
In this way all the unique values are identified.
