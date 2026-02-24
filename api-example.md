# Cognee REST API

1. Get all datasets
2. If no dataset available, create one.
3. Add data to the dataset
4. Build knowledge graph
5. Search

> [!NOTE]
> Replace localhost with 107.98.150.183

## Datasets

### Get All datasets

```sh
curl http://localhost:8000/api/v1/datasets
```

### Create Dataset

```sh
curl -X POST http://localhost:8000/api/v1/datasets -H "Content-Type: application/json" -d '{"name": "newjeans"}'
```

### Get dataset data

```sh
curl http://localhost:8000/api/v1/datasets/0444ad07-0744-52f2-a609-d888e246386e/data
```

## Add

```sh
curl -X POST http://localhost:8000/api/v1/add -F 'data=@newjeans/newjeans.txt' -F 'datasetName=newjeans'
curl -X POST http://localhost:8000/api/v1/add -F 'data=@newjeans/minji.txt' -F 'datasetName=newjeans'
curl -X POST http://localhost:8000/api/v1/add -F 'data=@newjeans/hanni.txt' -F 'datasetName=newjeans'
curl -X POST http://localhost:8000/api/v1/add -F 'data=@newjeans/danni.txt' -F 'datasetName=newjeans'
curl -X POST http://localhost:8000/api/v1/add -F 'data=@newjeans/haerin.txt' -F 'datasetName=newjeans'
curl -X POST http://localhost:8000/api/v1/add -F 'data=@newjeans/hyein.txt' -F 'datasetName=newjeans'
curl -X POST http://localhost:8000/api/v1/add -F 'data=@newjeans/bunnies.txt' -F 'datasetName=newjeans'
```

## Cognify

```sh
curl -X POST http://localhost:8000/api/v1/cognify -H "Content-Type: application/json" -d '{"datasets": ["newjeans"]}'
```

## Search

```sh
curl -X POST http://localhost:8000/api/v1/search -H "Content-Type: application/json" -d '{"query": "What are the main topics?", "datasets": ["newjeans"], "top_k": 5}'
```
