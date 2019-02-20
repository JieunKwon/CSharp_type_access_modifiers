# CSharp > Types > Access Modifiers

# Accessibility Level 

<image src='image.png' width='500px'>
 
** confused two types **  
<b> 1. protected internal </ b>
 
        A protected internal member of a base class is accessible from any type within its containing assembly. 
        It is also accessible in a derived class located in another assembly only 
        if the access occurs through a variable of the derived class type
        
<b> 2. private protected </ b>

        The private protected keyword combination is a member access modifier. 
        A private protected member is accessible by types derived from the containing class, 
        but only within its containing assembly
 
<image src='modifier.JPG' width='500px'>
