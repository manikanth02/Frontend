for reference
[Refrence](https://medium.com/@ayusharma.in/objects-writable-configurable-enumerable-365cdff6a408#id_token=eyJhbGciOiJSUzI1NiIsImtpZCI6ImQ3YjkzOTc3MWE3ODAwYzQxM2Y5MDA1MTAxMmQ5NzU5ODE5MTZkNzEiLCJ0eXAiOiJKV1QifQ.eyJpc3MiOiJodHRwczovL2FjY291bnRzLmdvb2dsZS5jb20iLCJhenAiOiIyMTYyOTYwMzU4MzQtazFrNnFlMDYwczJ0cDJhMmphbTRsamRjbXMwMHN0dGcuYXBwcy5nb29nbGV1c2VyY29udGVudC5jb20iLCJhdWQiOiIyMTYyOTYwMzU4MzQtazFrNnFlMDYwczJ0cDJhMmphbTRsamRjbXMwMHN0dGcuYXBwcy5nb29nbGV1c2VyY29udGVudC5jb20iLCJzdWIiOiIxMTQ5NTE2NDY2MTE1ODI0NjY0MjIiLCJlbWFpbCI6Im1hbmk4NGFzaWFAZ21haWwuY29tIiwiZW1haWxfdmVyaWZpZWQiOnRydWUsIm5iZiI6MTcyNTk2MDk0OSwibmFtZSI6Ik1hbmlrYW50aCBQcmFzYWQiLCJwaWN0dXJlIjoiaHR0cHM6Ly9saDMuZ29vZ2xldXNlcmNvbnRlbnQuY29tL2EvQUNnOG9jSklVcFg3TXExaVNxdHAtWDdFbDU1Nnh0TlpPcTN1SFRaVVR3V1lxTjJtQ25fLWRvTEI9czk2LWMiLCJnaXZlbl9uYW1lIjoiTWFuaWthbnRoIiwiZmFtaWx5X25hbWUiOiJQcmFzYWQiLCJpYXQiOjE3MjU5NjEyNDksImV4cCI6MTcyNTk2NDg0OSwianRpIjoiZGZmZmM4NmMwMmU4OWM4M2VmNTRkNGQ0NTAzM2NhOTUyMmU5OGEwNiJ9.o-iXhlu_2MNrVQfn6nyzd9JNVT7wb5xQeu7Eduv0002CkWN5qWpcs_gym4nCLEgovqDjtUHAQ0UEdv52M2KMR7SIyK9noaIdwRMrKuBoJcd07wvPn_a8_iNDy2Inv63VGm3yEZ788lvyxd0v52KL-3C9Oefd6qyQuitmf2U7aIeiuBK9hgKQH82r91uGhzeN6EjE5nal3jI0DP9NxAV2-f6VzQafvgB1_0wT0Pg4bOToWybMiiiks7QPTSN3PJMRgp0nRMODw1bBnSbZHvLVQ03EBSTROScfrnnm9AfvPjDy_HDqjtNQu_3G7rf5KuwqXpjSLoVAfeExHUYWVMcuog) 


```

class Bird {
    #breed;
    constructor(breed, name) {
        this.#breed = breed;
        this.name = name;
        this.fly = function () {
            console.log('It can fly');
        }
    }

    getDescription() {
        console.log(`${this.name} is a bird of breed ${this.#breed}`)
    }
}

const Pengiun = new Bird('X', 'Pengiun');
console.log(Pengiun.name);
console.log(Pengiun.#breed);

```

fly is created inside functions while getDescription is cretae on prototype.


```
function Bird() {
    this.breed = breed;
    this.name = name;
    this.fly = function () {
        console.log('It can fly');
    }
}

Bird.prototype.getDescription = function() {
    console.log(`${this.name} is a bird of breed ${this.breed}`)
}

```

In constructor function we create function at prototype by using key prototype



There are two ways to create Objects .


1.
```
const Bird = {
    breed: 'X',
    name: 'Pengiun',
    fly: function() {},
    getDescription: function() {
        console.log(`${this.name} is a bird of breed ${this.breed}`)
    }
};


```

2.In this method all values are define insise prototype and empty object is initialized

```
let Bird = Object.create({
    breed: 'X',
    color: 'white',
    fly: function() {},
    getDescription: function() {
        console.log(`${this.name} is a bird of breed ${this.breed}`)
    }
});


```



Some of the ways to configuer the object property

```
Object.defineProperty(Bird, 'name', {
    value: 'Pengiun',
    configurable: true, // we can either delete the property
    enumerable: true, // we can travrese the object by using loop
    writable: true // we can edit the value
});


```
