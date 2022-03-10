# Code standaarden
- Engelstalig
- Doxygen
- bestandtype: .hpp en .cpp

## Variabelen
- camelCase
- direct declareren en definieren indien mogelijk
### References en pointers
- & en * tegen het type aan
    - example:
        ```c++
            int& reference = a;
            int* pointer = b;
        ```

## Functies
- camelCase
- korte en duidelijke functienaam
- code style One True Brace Style
- example:
    ```c++
        int max, a=8, b=6;
        if(a > b){
            max = a;
        }
        else{
            max = b;
        }
    ```

- Direct doxygen voor de publieke functies met /** en **/            
    - example:
        ```c++
            /**
            * @brief brief description
            * @param var1 var description
            * @details detailed description
            * @return return details
            */
            int exampleFunction(int var1){
                return 1;
            }
        ```
- Direct korte beschrijving voor private functies gemarkeerd met /* en */ 
    - example:
        ```c++
            /* dit is een comment voor een private function */
            int exampleFunction(int var1){
                return 1;
            }
        ```

## Classes
- PascalCase
- gesorteerd op  type en dan op alfabetische volgorde
- eerst publics dan privates
    - example:
    ```c++
        class ExampleClass{
            public:
                bool booleanVar;
                int integerVar;
                int publicVar;

                bool function();
                int function(int var);
                
            private:
                int privateVar;
        }
    ```

## Commits and pull requests
- werken met feature branches
- duidelijke commit message wat er is geupdate
    - example: "Implemented communication code"
- pull requests moet door minimaal 1 persoon worden gereviewed bij merge naar dev/main branch

## Doxygen
- boven aan bestand na includes
    - example:
    	```c++
            /// @file
        ```
- begin met /**
- eindig met */
- doxygen labels met @
- example:
    ```c++
        /**
        * @brief brief description
        * @param var1 var description
        * @details detailed description
        * @return return details
        */
        int exampleFunction(int var1){
            return 1;
        }
    ```

## Files
- include_guards
    - include guard bestaat uit bestandsnaam
    - example:
        ```c++
            #ifndef FOO_BAR_BAZ_HPP
            #define FOO_BAR_BAZ_HPP
            #endif  //FOO_BAR_BAZ_HPP
        ```
    - geen pragma once
- includes
    - zelf geschreven hpp-files includes met "naam" overige met <naam>
    - eerst standaard libraries daarna zelf geschreven
    - example:
        ```c++
            #include <iostream>
            #include "eigen_bestand.hpp"
        ```
    - volgorde functies in cpp-file gelijk aan de volgorde in de hpp-file


## Overig
- Als je iets tegenkomt wat niet in dit document is gedefinieerd doe dan een @Technical Leader in de discord of neem contact op met de technical lead van jouw team
