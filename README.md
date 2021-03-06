# CSharp > Types > Access Modifiers
@ Feb 2019

@ I searched and learned regarding Modifiers from MSDN. When I declare fields some time, I was confused which accessibility is right. 
Specially, I focus on protected internal and private protected, readonly and const.  

# All Modifiers
<image src='modifier_all.JPG' width='600px'>
 
# Accessibility Level 

<image src='image.png' width='600px'>
 

# protected internal vs. private protected 
<b> 1. protected internal </b>
 
        A protected internal member of a base class is accessible from any type within its containing assembly. 
        It is also accessible in a derived class located in another assembly only 
        if the access occurs through a variable of the derived class type
        
        public class BaseClass
        {
           protected internal int myValue = 0;
        }

        class TestAccess
        {
            void Access()
            {
                BaseClass baseObject = new BaseClass();
                baseObject.myValue = 5; 
            }
        }

        
<b> 2. private protected </b>

        The private protected keyword combination is a member access modifier. 
        A private protected member is accessible by types derived from the containing class, 
        but only within its containing assembly
        
        public class BaseClass
        {
            private protected int myValue = 0;
        }

        public class DerivedClass1 : BaseClass
        {
            void Access()
            {
                BaseClass baseObject = new BaseClass();

                // it shows differce HERE !!

                // accessed through the current derived class instance
                myValue = 5;
            }
        }
 
<image src='modifier.JPG' width='600px'>

# const vs. readonly 

     You use the const keyword to declare a constant field or a constant local. 
     Constant fields and locals aren't variables and may not be modified. 
     Constants can be numbers, Boolean values, strings, or a null reference.

    The readonly keyword differs from the const keyword. 
    A const field can only be initialized at the declaration of the field. 
    A readonly field can be initialized either at the declaration or in a constructor. 
    Therefore, readonly fields can have different values depending on the constructor used. 
    Also, although a const field is a compile-time constant, the readonly field can be used for run-time constants
