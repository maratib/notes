# Vue3 Typescript notes


## reactive 
```javascript
//name: Infer type 
// (Typescript will auto detect it as string and if later we pass number into it will show error)
//age: union type string or number
setup() {
const state = reactive({
    name: 'Musa' 
    age: 25 as string | number 

    name = 25 //will not work as the type is string only
    age = '25' // will work as type is a union means string or number
    return {
        //toRefs() will keep the state reactive even if it is being 
        //spread. see bellow
        ...toRefs(state)
    }

})
}
```
## ref 
```javascript
//name: Infer type 
// (Typescript will auto detect it as string and if later we pass number into it will show error)
setup() {
const state = reactive({
    name: ref('Musa'); 
    //age: ref(25) as string | number //will not work hence we will change it to generic type
    age: ref<string | nummber> ref(25);
    return {
        name, age
    }

})
}
```

