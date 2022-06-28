# YAML
-------------------------------
***Concept***
> - YAML is a data serialization language [ *Process of converting data to a format that could be easily stored/ recovered/ sent over network, eg- use python to serialize data and sent over network to JS program which deserialize it and use* ] like JSON / XML
> - Mainly used for configuration files
> - Supports several data strcutures like array, set, dictionary, list etc.
> - File extension of .yaml or .yml
> - yaml content is oragnised in key-value pair ***`<key>:<value>`***
> 
>   ![image](https://user-images.githubusercontent.com/103237142/176063242-a466072e-4139-4b74-90cd-65b7b78adb6b.png)
> - Datatype for key is always string whereas datatype for value can be anything
> - yaml doesnot support `TAB` identation, we have to use `Spaces`, it can be one or more but it should be uniform throught the document
> - yaml file starts with three dashes `(---)` and ends with three dashes (---), we can have multiple files in the same 
> - Comments in yaml document is mentioned with #, it can be inline or separate line


***Datatype***
> - Boolean: Trur / true / On / Yes , False / false / Off , No
> - Number: Supports Integer, Float and Exponential
>   * Support NaN and Infinity
> - String: With or Without quotes
>   * Escape sequence is evaluated with double quotes
> - Multiline string: Using `fold ( > )` or `block ( | )`
>   * fold(>): Prints in a single line
>   * block(|): Prints in multiple lines similar to input
>   + Using strip operator (-) along with multipline operators, whitespaces can be removed ( >- ) or ( |- )
> - Dictionary: can be represented inline or multiline in key-value pair
> - Null: Null value represented as `tilde (~)` or `null`
> - List: Any datatype enclosed in square brackets [.......] or with -
> - Set: Any datatype preceded by ? and set is declared as !!setName
>   * consists of only unique values

![image](https://user-images.githubusercontent.com/103237142/176082816-ef47f515-d470-4340-b982-3461d9d47fbd.png)

![image](https://user-images.githubusercontent.com/103237142/176082888-2f0a9c61-cc6e-457d-a6d3-892ca43f5a10.png)

![image](https://user-images.githubusercontent.com/103237142/176082952-a7530f86-57ef-45c0-aa64-e5016ee97fdd.png)

![image](https://user-images.githubusercontent.com/103237142/176082980-0ccb3c48-a17f-45c5-b73f-58b369346248.png)

![image](https://user-images.githubusercontent.com/103237142/176083021-e9b348d7-a6d6-44f6-8de7-57059da9dd11.png)


## Anchors and Extensions
> - Feature to identify an item and then reference it elsewhere in file
> - Anchors are created using the & sign followed alias name
> - Use this alias name along with * sign to reference the value
> - Extensions extends the anchor values to add additional values

## Placeholders
> - YAML placeholders are used to reference variables inside the YAML files



