It's forbidden to access any member of a union that's isn't the current 'active' member.
There is an exception though - "if a union contains several structures that share a common initial sequence ...and if the union object currently contains one of these structures, it is permitted to inspect the common initial part of any of them anywhere that a declaration of the completed type of the union is visible".
The problem in our case is that the declaration ot the union isn't visible within function f.
