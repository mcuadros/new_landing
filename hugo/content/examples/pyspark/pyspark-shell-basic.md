---
heroTemplate: false
asideTemplate: project/aside-docs.html
---

## Basic example

In this example, the pyspark-shell is used to show a simple usage of the spark-api.

- [ref]({{< ref "pyspark-shell-classifying-languages.md" >}})

- [ref]({{< ref "pyspark-shell-classifying-languages.md" >}})
- [relref]({{< relref "pyspark-shell-classifying-languages.md" >}})
- [pyspark's shell classifying languages](pyspark-shell-classifying-languages)

First, you can see how to import the package and instantiate and object that provide all the methods to manipulate the data retrieved from repositories.

The `api` object is used to get all the repositories, get the `HEAD` references from the repositories and eventually, get all the files from these references. Then a table is showed selecting the columns `file_hash`, `path` and reference `name`.

```bash
$ pyspark --packages com.github.src-d:spark-api:master-SNAPSHOT --repositories https://jitpack.io
>>> from sourced.spark import API as SparkAPI
>>> api = SparkAPI(spark, '/path/to/siva-files')
>>> api.repositories.references.head_ref.files.select('file_hash', 'path', 'name').show()
+--------------------+--------------------+---------------+
|           file_hash|                path|           name|
+--------------------+--------------------+---------------+
|bdbf905450bc30b51...|            Rakefile|refs/heads/HEAD|
|fee334944ecfdb0a2...|model_plugins/Rak...|refs/heads/HEAD|
|e69de29bb2d1d6434...|model_plugins/acc...|refs/heads/HEAD|
|1147a1711b11a32d7...|model_plugins/acc...|refs/heads/HEAD|
|e69de29bb2d1d6434...|model_plugins/acc...|refs/heads/HEAD|
|fcb93890e049dac4a...|model_plugins/acc...|refs/heads/HEAD|
|f7157b33e0bf58f65...|model_plugins/acc...|refs/heads/HEAD|
|ec1782aa450914a33...|model_plugins/acc...|refs/heads/HEAD|
|42900ddf5dfccf25c...|model_plugins/acc...|refs/heads/HEAD|
|d452a6eb34ce195c8...|model_plugins/acc...|refs/heads/HEAD|
|e69de29bb2d1d6434...|model_plugins/aut...|refs/heads/HEAD|
|1147a1711b11a32d7...|model_plugins/aut...|refs/heads/HEAD|
|8eb073459693cba66...|model_plugins/aut...|refs/heads/HEAD|
|291e140054f63737a...|model_plugins/aut...|refs/heads/HEAD|
|db32a46ea544164a4...|model_plugins/aut...|refs/heads/HEAD|
|107f0ec8025e626d6...|model_plugins/aut...|refs/heads/HEAD|
|42900ddf5dfccf25c...|model_plugins/aut...|refs/heads/HEAD|
|2dc8d738c6ae57567...|model_plugins/aut...|refs/heads/HEAD|
|e69de29bb2d1d6434...|model_plugins/deq...|refs/heads/HEAD|
|1147a1711b11a32d7...|model_plugins/deq...|refs/heads/HEAD|
+--------------------+--------------------+---------------+
only showing top 20 rows

```
