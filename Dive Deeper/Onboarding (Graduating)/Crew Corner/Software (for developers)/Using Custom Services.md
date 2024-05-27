In [[Make]] you can make a custom app. What this means is Make wraps an API endpoint for you with further functionality such as modules. Some parts of the app are common to all modules. Make calls this the Base. Within Base, you specify the base URL. 

*Edit: As it turns out, this is likely not needed, as it's more straightforward to use Make's custom HTTP module.* 
# Astral (Micro-) Services
At Astralship, we're building a suite of microservices to integrate the physical environment with digital collective intelligence tooling. We have deployed [[FaaSD]] microservices, hosted on [[Digital Ocean]] that make available different functions with a given API endpoint: 
![[Pasted image 20231218151547.png]]
We can then send parameters to this url, for example, as part of the [[Voice-to-Wiki Pipeline]], an audio file containing a voice note from Telegram. 
![[Pasted image 20231218170857.png]]

