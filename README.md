#Solar Car

#aux kit
***One of , if not the first open source solar car auxiliary framework

After my first experience participating in the national solar car challenge in Texas, I gained some new insight about our auxiliary system. Namely it was unreliable, wires were often hard to find and would unknowingly rip out of connections. Any task that involved adding in new components like turn signal flashers or connecting bus bars would usually be a task so unnecessarily complicated, days would sometimes be lost.

With the pain points in mind I decided to just create an all in one solution that would allow further iteration to be made much quicker in a smaller, more reliable package. This would give us more control over our car if we wanted to add in new features or improve old ones. Additionally I wanted the completed system to work standalone and be able to drop into another car if we decided to race for another division. 

Aux-kit wasn't ever essential to the cars functionality but it was an exercise in improving areas of friction myself and others working with the electrical system had. I wanted to make the system open source so other teams could also adopt the system and add more features. Because the solar car isn't necessarily a competition but instead a challenge I was interested in seeing how much we could pack into a PiHAT. 

The first version had many issues and was designed as a Pi HAT stackup where the bottom board was power management so the system could run off of a smaller 12v battery. The top was the controller which connected to other expansion boards for turn signal control and brake pedal detection. 

![1000005474](https://github.com/user-attachments/assets/4137936c-6702-4bb2-91b8-517de88e96bf)

I had endless issues with monitoring everything on the car and because of this the software was inefficient. I realized that I needed to redesign my board logic, offloading software components into hardware ones to make the system more efficient. Because of this I redesigned the battery monitor, brake detection, and turn signal flasher.

![PXL_20240612_231920880](https://github.com/user-attachments/assets/bf8bae29-f479-4160-9b8c-491e7096c862)

The current version is building off the working principles of the second version and the experience I gained using Kicad to make the board more user friendly. I added jumpers to switch any part of the board from built-in analog control to customizable digital control that a team could configure for their car in their way. I also eliminated the power management board and integrated everything into 1 main board by cutting down on unnecessary features that weren't yet requested by any users. Finally I made sure the dimensions and on device specs of the PiHAT were compliant with the Pi foundations HAT requirements and made the board double side with common off the shelf components so it’s even easier for a team to create. 

![Screenshot 2024-12-14 190422](https://github.com/user-attachments/assets/74220aa1-d73b-4a5f-b92a-4fd972da86ba)

#CAD Developments 
***Improving first year designs


A recurring issue we would have as a team was that wheel adapters would shift, preventing the wheels from making a smooth circular rotation. Also motor mounts and mounting tabs would be out of alignment with the tabs also breaking off after certain use. The first year I had designed a motor mount for an ME1305, however the mount was way too heavy and wasn't perfectly inline with the driven gear. This alignment issue caused the chain to work its way off of the drive gear or just cause excessive chain wear. To make another improvement on the things I had designed from the first year, I created a completely new motor mount from the ground up with input from one of the main metal workers on our team. 

![PXL_20240513_153738418](https://github.com/user-attachments/assets/32ac9458-eb37-4908-8ee9-f1f4219c0748)
![PXL_20230625_150715272](https://github.com/user-attachments/assets/3f7fefa1-f179-4cf6-a2c9-149eceacddd0)

first version and prototype of the motor mount

The final design had 2 main parts allowing the motor to be moved in the x and y direction to find the best alignment with the driven gear. This solution was ideal since it allowed us to just reset the mount positioning if any changes were made to the part of the car it was fixed to or the axle that the driven gear was attached to. I then sent these files to be water-jet out of metal for free. Because the only available material was ¼” steel I made the motor mount as lightweight as possible by removing as much metal as possible while keeping the mount strong. This is why the final design looks like a skeleton.  

![Screenshot 2024-12-12 225820](https://github.com/user-attachments/assets/774faba3-69ba-49a7-bf85-dbeb4c99a1af)

To create wheel adapters I designed every component to be as lightweight as possible which also meant designing them with the least amount of parts. Another criteria was making the adapters easily accessible since many of the older adapters had placed the mating bolt pattern in a way where certain bolts would be directly behind wheel spokes making them incredibly annoying to adjust or remove. 

![Screenshot 2024-06-03 112336](https://github.com/user-attachments/assets/e7c9185e-d876-4ee9-999d-00f2a1bec23d)


Lastly for the mounting tabs, I had written a simple OpenSCAD script to create parametric mounting tabs as we needed them. Before this we would hand make them out of flat bar which could take an unnecessarily long amount of time for tabs that weren't consistent enough for aligned bolt holes. While the OpenSCAD script worked, I had also created a Fusion file which is what we ended up waterjetting. 

![Screenshot 2024-11-25 172606](https://github.com/user-attachments/assets/7359dee2-41c8-4ce8-9504-b2ece805f5f9)
