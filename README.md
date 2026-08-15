# str
that lybreary can use str mthod on c
# why i created it
because using char* , const char* is hard on C base and C important for
(Compiler,interpeter,os....) //opkll
#include <stdbool.h>
#include <stdlib.h>
#include <stddef.h>
#include <stdio.h>
#include <string.h>
//
///@brief that return str class
struct str{char* c_str;};
/// @brief that return number of character str
/// @param self that str
size_t length(str self){return strlen(self.c_str);}
/// @brief that function like constractor str
/// @param _l that str what is
/// @return str
str newstr(const char* _l)
{
    //set returning var
    str returning;
    //set memorey str
    returning.c_str =(char*)malloc(99*sizeof(char));
    //set c_str elements  _l
    strcpy(returning.c_str,_l);
    //return
    return returning;
}
/// @brief that function  add str to _add
/// @param _self that str will add to it
/// @param __add that character add it
/// @return str
str add(str _self,char __add)
{
    //set returning var
    str returning =  _self;
    //add character to len
    returning.c_str[strlen(_self.c_str)] =__add;
    //return
    return returning;

}
/// @brief that function return add string with auther
/// @param _self that str base
/// @param __add that str who add it
/// @return str
str add(str _self,const char* __add)
{
    str returning = _self;
    strcmp(returning.c_str,__add);
    return returning;
}

 /// @brief  that function transform str to  lines array                   
/// @param code that str what code it
str* superate(str code,char superateline)
{
    //set returning
    str* returning = (str*)malloc(999*sizeof(str));
    //set command var
    str  command=newstr("");
    size_t lenCommand = 0;
    //
    size_t numOfCharcterCommand=0;
    //for loop
    for (size_t i = 0; i <=strlen(code.c_str); i++)
    {
        //set add
        if(code.c_str[i]==superateline) {returning[lenCommand++]=command ;command=newstr("");continue;}
        //add characterl
        command=add(command,code.c_str[i]);
    }
    //fix final command
    returning[lenCommand]=command;
    //return  
    return returning;
}
//to Lines '\n'
auto toLines =[](str code){return superate(code,'\n');};
//to void ' '
auto superateVoid= [](str code){return superate(code,' ');};
