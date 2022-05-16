# py-aggregate
Buffer strings, bytes, and JSON objects in Python!

```python
# create an aggregate with a max_count of 2 items and max_size of 100 bytes
agg = Aggregate(2, 10*10)

# add items to the aggregate until it is full (ok == False)
for x in ["foo","bar","baz"]:
	ok = agg.add(x)
	if not ok:
		# retrieve the items, reset the aggregate, and re-add missed item
		items = agg.items
		agg.reset()
		agg.add(x)

# retrieve any remaining items
if agg.count > 0:
	items = agg.items
```
