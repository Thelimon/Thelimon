```ts
import { Component, OnInit } from '@angular/core';

 @Component({
  selector: 'app-me',
   template: `
      <h1 class="name"> {{ aboutMe.Juan David }} </h1>
        <div class="codding">     
        
          <p class="code"> 
            {{ aboutMe.HTML }} - {{ aboutMe.CSS }} - {{ aboutMe.SCSS }} -  {{ aboutMe.Javascript}} 
            - {{ aboutMe.Typescript}} - {{ aboutMe.Java}}
          </p>
    
          <p class="tools"> 
            {{ aboutMe.Tailwind }} - {{ aboutMe.Bootstrap }} - {{ aboutMe.styledComponents }} 
            - {{ abooutMe.React }} - {{ abooutMe.Redux }} - {{ abooutMe.Angular }} - {{ abooutMe.Rxjs }}
          </p>
         
        </div>
        
        <div class="workplace"> 
          <p class="company"> {{ aboutMe.PappCorn }}  </p>
          <p class="position"> {{aboutMe.webDeveloper }} </p>
        </div>
    `
  })
  
  export class HomeComponent Implements OnInit {
  
        public aboutMe: aboutMeI[] = [];    
        
        constructor(private: aboutMeSvc: AboutMeService){}
        
        ngOnInit(): void { this.getMe(); }
        
        private getMe(): void {
          this.aboutMeSvc
          .getMe()
          .subscribe((content: aboutMeI[]) => {
            this.aboutMe = content;
          }
        );
      }
  }   
```
