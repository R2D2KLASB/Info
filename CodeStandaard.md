# Codestandaard
- Programmeren in het Engels
- Alle extern beschikbare code wordt voorzien van Doxygen documentatie
- Gebruikte bestandtypen zijn .hpp en .cpp

## Variabelen
- camelCase
- Direct declareren en definieren indien mogelijk
### References en pointers
- & en * tegen het type aan \
  *voorbeeld:*
    ```c++
    int& reference = a;
    int* pointer = b;
    ```

## Functies
- camelCase
- Gebruik korte en duidelijke functienamen
- Gebruik de One True Brace Style \
  *voorbeeld:*
    ```c++
    int max, a=8, b=6;
    if(a > b){
        max = a;
    }
    else{
        max = b;
    }
    ```

- Gebruik voor het toevoegen van Doxygen tekst aan public functies /** en */ \
  *voorbeeld:*
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
- Gebruik voor het toevoegen van informatie aan private functies /* en */ \
  *voorbeeld:*
    ```c++
    /* dit is een comment voor een private function */
    int exampleFunction(int var1){
        return 1;
    }
    ```

## Classes
- PascalCase
- Public variabelen en functies komen bovenaan
- Variabelen komen boven functies
- Zowel variabelen als functies worden eerst op (return) type gesorteerd, en daarna op alfabetische volgorde \
  *voorbeeld:*
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
- Werk met feature branches
- Zet in de commit message duidelijk neer wat er geüpdatet is \
  *voorbeeld:* `Implemented communication code`
- Een pull request naar de dev of main branch moet altijd door minimaal één iemand gereviewd worden

## Doxygen
- Komt altijd bovenaan header files, na de includes \
  *voorbeeld:*
    ```c++
    #include <iostream>

    /// @file
    ```
- Begin altijd met /** en eindig met */
- Begin Doxygen labels met een @ \
  *voorbeeld:*
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
### Include guards
- Een include guard moet overeen komen met de bestandsnaam \
  *voorbeeld:*
    ```c++
    #ifndef SAMPLE_HEADER_HPP
    #define SAMPLE_HEADER_HPP

    ...
        
    #endif  //SAMPLE_HEADER_HPP
    ```
    `#pragma once` is dus niet toegestaan
### Includes
- Bij het includen van zelfgeschreven header files gebruik je aanhalingstekens en alle andere met punthaken
- Standard libraries include je eerst, daarna de zelfgeschreven libraries \
  *voorbeeld:*
    ```c++
    #include <iostream>
    #include "eigen_bestand.hpp"
    ```
- De volgorde van functies in source files moet overeen komen met die in de header files


## Overig
- Als je in een situatie komt waarin je niet zeker bent hoe iets neergezet moet worden en het staat niet in dit document, doe dan @Technical Leader in de [Discord server](https://discord.gg/JZc7WXrrU3) of neem contact op met de Technical Lead van jouw team
