HELLO, THIS IS CS50 😄..

my name is Kholoud and im from Egypt

# MY PROJECT NAME IS : DAILYWATHER

#### Description: a daily weather website that gives you the weather about a specific city with the date and time.





## my project name and what it talks about:
 name: dailyweather
 a simple weather website that gives you the forecast of
 your city as soon as you search about it which is :
  - the daily temperature
  - the wind status
  - the humidity
  - visibility
  - air pressure
  - the condition
  - the time and date of the day
  - and finally the name of the city apparently

## features that i added:
 - dark & light theme button using the help of  TailwindCSS library :
 ```jsx
 /** @type {import('tailwindcss').Config} */
export default {
  content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"],
  theme: {
    extend: {},
  },
  plugins: [],
  //added this dependency darkMode feature to help me activate the dark className
  darkMode: "class",
};
//then i added a classname dark in every component that i wanted to chaneg colors in 
//a sample of what i added 
//App.jsx
    <div className="bg-slate-800 h-screen flex justify-center  items-start dark:bg-blue-200">
    </div>
    <h1 className="text-slate-200 text-2xl col-span-2 dark:text-black">
          Today's Forecast
    </h1>
   <button onClick={toggleLightMode} className="absolute w-8 h-8 top-16 left-72 bg-blue-600 rounded-3xl text-black font-semibold dark:bg-blue-500 dark:text-white">
   </button>
//temperature.jsx
   <div className="flex justify-center items-center text-slate-200 mt-8 dark:text-slate-900">
        <p className="font-semibold text-[55px] ">
          {stats.temp}
          <span className="text-[33px]">°C</span>
        </p>
      </div>

      <div className="flex justify-center text-slate-300 mt-8 text-[25px] dark:text-slate-700">
        {stats.condition}
      </div>

      <div className="flex justify-center text-slate-400 mt-5 text-[15px] dark:text-slate-700">
        Today &#183; {stats.time} | {stats.location}
      </div>

  //and also with the Higlights.jsx
  <div className="text-slate-200 ms-2 dark:text-slate-700">{stats.direction}</div>
 <div className="w-full mt-4 bg-gray-200 rounded-full h-1.5 mb-4 dark:bg-gray-700">
<div
   className="bg-blue-600 h-1.5 rounded-full dark:bg-blue-300"
   style={{ width: `${stats.value}%` }}
   ></div>
</div>
 ```


 - local storage so that when you click refres the color theme you like stays as it is 
 ```jsx
 //first of all i installed the library : npm i use-local-storage
 //then i imported it 
 import useLocalStorage from "use-local-storage"
//then made a const declaring the lightmode and its set 
  const [lightMode,setLightMode] = useLocalStorage("lightMode",preference);
  const toggleLightMode = () => {
    setLightMode(!lightMode);
  }
  // then i added the condition of the lightmode and dark them class in the container className.
      <div className={`${lightMode && "dark"}`}></div>
   //i added a button to activate the dark and light theme as sooon as you click on it with a sun icon for the light mode and a moon for the dark mode
   <button onClick={toggleLightMode} className="absolute w-8 h-8 top-16 left-72 bg-blue-600 rounded-3xl text-black font-semibold dark:bg-blue-500 dark:text-white">
        {lightMode? <div><svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-white ml-1">
        <path stroke-linecap="round" stroke-linejoin="round" d="M12 3v2.25m6.364.386-1.591 1.591M21 12h-2.25m-.386 6.364-1.591-1.591M12 18.75V21m-4.773-4.227-1.591 1.591M5.25 12H3m4.227-4.773L5.636 5.636M15.75 12a3.75 3.75 0 1 1-7.5 0 3.75 3.75 0 0 1 7.5 0Z" />
         </svg></div>:<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24  24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 ml-1 ">
       <path stroke-linecap="round" stroke-linejoin="round" d="M21.752 15.002A9.72 9.72 0 0 1 18 15.75c-5.385 0-9.75-4.365-9.75-9.75 0-1.33.266-2.597.748-3.752A9.753 9.753 0 0 0 3 11.25C3 16.635 7.365 21 12.75 21a9.753 9.753 0 0 0 9.002-5.998Z" />
      </svg>}
      </button>
      //using hero icons website for theicons  as we will say later..

 ```


 - also added preference system : it simply changes the theme as your device's theme color by default..

 ```jsx
 // as i wanted to go a little further by making the the dark or light theme as the user prefernce i used the following code
 const preference = window.matchMedia("(prefers-color-scheme:light)").matches;
  const [lightMode,setLightMode] = useLocalStorage("lightMode",preference);
  //you can simply chnage the prefernce theme by right clicking and choose inspect
  //then on the application side type ctrl+p show rendiring and chnage the emulation color then refresh the website 
 ```



## what i used to create this website:
 1. **React library** : i created this website using React librry . you can check about react on the official website
    * [React](https://react.dev/)

 2. *vite* : it is a good frontend tool that handles the slowness that we face when we start the react library 
    * [Vite](https://vitejs.dev/)

 3. *Weather api* : used an open weather api in my project 
    * [Weather api](https://www.weatherapi.com/)  
    note:i made the default city "Ismailia" respectfully as it is the city i live in right now

 4. *Tailwind CSS*  : A utility-first CSS framework packed   with classes that can be composed to build any design, directly in your markup 
     * [Tailwind css](https://tailwindcss.com/)
 
 5. *Hero coins* : added some icons by this open icons source
      * [Heroicons](https://heroicons.com/)

 6. *use-local-storage* in react : handeled the refresh theme by installing and using this library
  -- "npm install use-local-storage" and then import it in your project   


## How I created (divided) my project:
 1. first, i created a folder 
 2. second, installed vite and activated react.js on it 
 3. then installed the node_modules of the react 
    by running on the terminal "npm i"
 4. i deleted everything that i wouldn't be in need off 
    like the react icons and the testing file
 5. devided the project into two components : 
    one for the first column of the project and
    another for the second one 
 6. imported those components in **App.jsx** 
 7. the first component "Temperature.jsx" was about 
    the search bar , the location icon , 
    the degree of the temprerature ,the condition of 
    the dayweather it is sunny clear or cold etc 
    letting the weather api to decide ,and
    finally thr time and date of the city that we searched for 
 8. the second component which i named it "Highlight.jsx" 
    about just a simple div saying: Forecast.
    and 4 divs giving us the wind speed ,
    humidity,visibility and the air pressure
 9. then finally i connected all the information i needed 
 from the weather api and passed it to 
 those 2 components as proops from the App.jsx components which is the main page

      

THIS WAS CS50 .💚

#   d a i l y w e a t h e r  
 