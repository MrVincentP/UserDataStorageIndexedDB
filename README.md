# UserDataStorageIndexedDB
a web component for storage user data by IndexedDB

### About IndexedDB JS Component
In 2020, I worked as a front-end leader in a company, but in fact, I didn't care about these titles or similar things. At that time, I had multiple systems. Simply put, there were a series of management systems on the PC that corresponded to different businesses. I didn't have time to organize these systems uniformly, nor did I have time to unify them into a larger SaaS system (regarding the packaging of SaaS systems according to different business requirements, I will continue to post the code below, please continue to follow, thank you). Data exchange can only be done through localStorage.

Simply put, it is to log in to a BMS system, read the permissions of several subsystems that the user has, and then display these authorized subsystems. Users can click on the corresponding subsystem to enter and use the subsystem's login to receive their tokens. On the surface, it should be correct, but it is not. LocalStorage can only solve the login problem of users and cannot solve the storage problem of some user information. Once the user's information storage capacity increases, localStorage will discard the previous data and only save the most recent data, which is one of them. Secondly, at that time, based on the Vue2 version of Vuex, user information was saved, and once the application was refreshed, all data would be reinitialized, which could not achieve true computation and persistence.

At that time, I was thinking that there should be a better way to solve this problem, so I thought of IndexedDB, but I didn't have time to spare any time to do this.

The turning point came in 2021. In March, I was laid off. Yes, because of the COVID-19 epidemic. In April 2021, I joined a big data financial systems company that specializes in B2B SaaS systems. The front-end development languages for the systems are AngularJs 1.6 and Angular9+. Then in May 2021, I was sent to a large bank to implement a system project. The front-end language of the bank system was Vue2, and the company also provided me with two helpers. So, I had time to implement the storage idea of IndexedDB and apply it to the bank system, solving some problems that I had never encountered before.

Then, after June 2022, I started working on the gameFi project and upgraded to another version.

The Js component of this IndexedDB can be deeply bound to routing and is applicable to all front-end frameworks currently on the market.

# Principle

Please read the official documentation

# Example
The Main File is '$idb.js', I have explained everything ;
 
The Controller File is '$indexedDB.js', I have explained everything;

import '$indexedDB' from '$indexedDB';

    if you want store / update a json file to you indexedDB:
    $indexedDB.set('constantApp', 'json.key', 'json.name', json.data, (cb)=>{
       // constantApp is table name
       // json.key is a route name,
       // json.name is a route key,
       // json.data is ths json file's data
       // cb is an Optional 
    });

    if you want get a json file to you indexedDB:
    $indexedDB.get('constantApp', 'json.key', 'json.name', (cb)=>{
        // constantApp is table name
        // json.key is a route name,
        // json.name is a route key,
        // json.data is ths json file's data
        // cb is an Optional
    });

    if you want delete a json file to you indexedDB:
    $indexedDB.delete('constantApp', 'json.key', 'json.name', (cb)=>{
       // constantApp is table name
       // json.key is a route name,
       // json.name is a route key,
       // cb is an Optional 
    });

    if you want delete a route to you indexedDB:
    $indexedDB.delete('constantApp', 'json.key', (cb)=>{
        // constantApp is table name
        // json.key is a route name,
        // cb is an Optional
    });

    if you want delete a table to you indexedDB:
    $indexedDB.delete('constantApp', (cb)=>{
    // constantApp is table name
    // cb is an Optional
    });


These examples basically cover all business requirements. For specific operation documents, please refer to the internal instructions of JS.

It should be noted that since it is implemented based on a promise, it is also possible to package an additional layer of Promise outside. If using promise. all, please note that promise. all can only be used once and cannot be included in promise.all. It is recommended to use a for loop instead.

Because it is a promise implementation, the issue of synchronization was not considered, and only asynchronous and synchronous methods were considered. A slight modification is needed.




