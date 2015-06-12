# Token replace AJAX
--------------------

The Token replace AJAX module adds the ability to process individual tokens via
an AJAX callback. It is primarily a developer utility, built for the purpose of
offloading common functionality from other modules.



## Usage
--------

The Token replace AJAX module is essentially a very basic REST API with only one
method:



### token_replace/ajax/:token

Returns the token, replacement and any Drupal messages as a JSON object.


#### Parameters

- **:token**

    The token you wish to process in a standard token format.
 
    **Example:** [node:title]
  
  
- **entity_type** _(optional)_

    An entity type to be used for the token data.
    
    **Example:** node
    

- **entity_id** _(optional)_

    An entity id to be used for the token data.
    
    **Example:** 1



#### Example Request

```GET token_replace/ajax/[node:title]?entity_type=node&entity_id=1```

#### Example Result

```
{
  "token": "[node:title]",
  "value": "Node 1",
  "messages": {
    "data": [],
    "html": ""
  }
}
```


## Advanced usage
-----------------

You can also POST an entity form to the endpoint (excluding the entity_type and
entity_id parameters) and the module will create a dummy entity as the token
data.
