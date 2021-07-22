
## Intro
A repository of sanskrit sandhi rules (as standardized by the pANini-patanjali-kAtyAyana tradition), for shared use in sandhi-engines implemented in various programming languages. Various sandhi engines may read these toml files and construct _regular expression substitution rules_.

We anticipate that similar repositories may be constructed for sandhi rules of other languages, and other sanskrit grammatical traditions.

## Rule format
- General terms are defined in [/terms.toml](terms.toml) . These terms are used to more concisely specify regular expression matching and substitution rules. These terms will need to be substituted with their values specified in /terms.toml to arrive at valid regular expressions.
- Each input pattern gets one rule file.
- We prefer simpler regular expressions. So, rather than use markups like <yaN_accent>, we use specially defined characters like ʸ. Generally such special code-symbols are chosen from [non-sanskrit superscripts and subscripts](https://en.wikipedia.org/wiki/Unicode_subscripts_and_superscripts). 
- See [vowel/i__ach.toml](vowel/i__ach.toml) for an exmaple of the format.

## Assumptions
- We assume a particular but clear devanAgarI representation in defining our rules. 
  - Given ब्रह्म॑ + अस्ति in the external representation, we get: ब्र्अ꣡ह्म्अ꣢ + अस्त्इ for the purpose of internal processing. So, we have a simple and uniform way of representing any vowel with its duration/mAtrA and accent.
  - Once the processing is done, we get ब्र्अ꣡ह्म्आ꣢स्त्इ. The result would then be converted to the desired output for humans to see: ब्रह्मा॑स्ति or ब्र꣡ह्मा꣢स्ति  or bráhmāsti.
- Use unicode sAmaveda superscript 1 to represent udAtta, 2 to represent general svarita, atharvavedic mark र्यं᳡ to represent jAtya svarita, sAmaveda superscript 3 to represent sannatara, something else (or nothing) for ekashruti.

## Appendix
### Devanagari for internal use: justification.
- In this day and age, programming languages can quite easily deal with devanAgarI concisely and directly despite the clumsy unicode "a" mark absence . 
- It works well with accent notation (given the wide variety of accent marking supported for that script).
- The script is the most popular one for sanskrit.
