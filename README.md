# fluorinefx
fluorinefx with .Net Core 3.1/.Net 5 support.

### Original repo message
Source code belongs to http://www.fluorinefx.com/

This FluorineFx github project is branched from revision #209 located at http://code.google.com/p/fluorinefx/

What I changed to the source code:
- fixed a bug that occasionated by a race condition in FluorineFx/Messaging/Endpoints/Filter/ProcessFilter.cs. The FactoryInstance class is shared between 
threads and often get overriden by another thread (http://code.google.com/p/fluorinefx/issues/detail?id=11). A lock was added in order to prevent concurrent access.
- more detailled error messages were added in order to always log the name of the class and the method (in particular: __Res.Invocation_NoSuitableMethod).
- the name of the class/method were added to the exception message that is sent back to flash/flex (ExceptionASO.cs) when something goes wrong.
- documented a bit more some methods/classes.