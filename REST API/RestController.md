### 概要
* Spring 4+で、REST APIに対応するannotation-> @RestController
 class levelに付けるannotation

* class levelでRequestMappingでaccess API指定。

* method levelでRequestMappingか（text-based return value)
 GetMapping(value="", produces="")でreturn valueのtypeまで指定可能。
 
### 例1 ("value" - API // "produces" - return type)
 
```kotlin
@GetMapping(value="/sendVO", produces = ["application/json"])
fun sendVO():RestfulSampleVO{
    val vo = RestfulSampleVO()
    vo.name = "John Doe"
    vo.address = "12345 21st Avenue, Pasadena, CA"
    return vo
}
```

### 例1: 結果
```json
{"name":"John Doe","address":"12345 21st Avenue, Pasadena, CA"}
```
