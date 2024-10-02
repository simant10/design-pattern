# Design Pattern
![image](https://github.com/user-attachments/assets/cb893256-665b-43a7-bb6e-a21917342fb1)

## What is creational design pattern
>creational design pattern provides a way to creating object.
>Creational pattern describe how object created at class instantiation time
![image](https://github.com/user-attachments/assets/3bac092f-ee16-401e-a135-c3f8ac57a4e1)

###  Singletone Design pattern
> In singletone design pattern a single class is responsible to create an object.
> Singletone design pattern assures us that a single object get created
#### Postmortem of singletone 
* How to create object :- we can create object using new keyword and instantiate variable using constructors.
* AS we know that in Singletone Design pattern, **we should have single object** It means we need to **restrict muliple instantiation.**
* We can restrict multiple instantiation by **making constructor private**
```javascript
    class SingleToneDemo{
        private SingleToneDemo(){

        }
    }
```
* But we should be able to create object onces.
* So we have one **static instance** of that particular class and with **one static method**, we should be allowing to create the object.

```javascript
    class SingleToneDemo{
        private static SingleToneDemo singletoneObject;
        private SingleToneDemo(){
            ..................
        }
        public static getSingletoneInstance(){
            ................
        }
    }
```
* Creation Singletone class
* Lazy instantiation 
```javascript
    class SingleToneDemo{
        private static SingleToneDemo singletoneObject=null;
        private SingleToneDemo(){
            ..................
        }
        public static getSingletoneInstance(){
            if(singletoneObject==null){
                singletoneObject = new SingleToneDemo();
            }
          return singletoneObject
        }
    }
```
* Eager instantiation
```javascript
    class SingleToneDemo{
        private static SingleToneDemo singletoneObject= new SingleToneDemo();
        private SingleToneDemo(){
            ..................
        }
        public static getSingletoneInstance(){
           return singletoneObject
        }
    }
```

