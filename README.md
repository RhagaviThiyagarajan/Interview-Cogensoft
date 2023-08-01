1)Curry function sum(1)(2)(3)()
//- &gt; should return 6

answers-function App(num) {
  let sum = num;

  function AddNext(nextNum) {
    if (typeof nextNum !== "number") {
      return sum;
    }

    sum += nextNum;
    return AddNext;
  }


  return AddNext;
}
console.log(App(1)(2)(3));
export default App;




2)Promise.all polyfill

if(!Promise.all)
{
  Promise.all=function(promises)
  {
    return new Promise(function(resolve,reject)
    {
      if(!Array.isArray(promises))
      {
        return reject(new TypeError('Promises must be resolved'))
      }



      let resolvedCount=0;
      const results=new Array(promises.length);



      promises.forEach((promise,index)={
Promise.resolve((promise)).then((result)=>{
  results[index]=result;
  resolvedCount++;


  if(resolvedCount===promises.length)
  {
    resolve(results);
  }
}).catch(reject);
      });
    });
  };
}


const promise1 = Promise.resolve(1);
const promise2 = new Promise((resolve) => setTimeout(() => resolve(2), 1000));



Promise.all([promise1,promise2])
.then((results)=>{
  console.log(results);
}).catch((error)=>{
  console.log(error);
});





3. Try writing the code without using async and await
 async function main() {
  
    try {
 const name = await getName();
 console.log(`Hello ${name}!`);
 const age = await getAge(name);
 const drink = age &lt; 10 ? &quot;milk&quot; : &quot;coke&quot;;
 console.log(`Have a ${drink}.`);
 const child = age &lt; 10;
 return child;
 } catch (e) {
 console.log(&#39;Error&#39;)
 }
 return null;
 }
 Rewrite above function without using async await



  answers-
  function main()
  {

    return getName().then(function(name)
    {
      console.log(`hello ${name}`);
      return getAge(name);
    })
.then(function(age)
{
  const drink=age<10 ? 'milk':'coke';
  console.log(`have a ${drink}`);
  const child=age<10;
  return child;
}).catch(function(e)
{
  console.log('error');
  return null;
});
  }




  4)  Question-
  //Flatten following array without using array.flat
// [1,2,[3,4], [5, [6, 7,[8,[9]]]]] into -&gt; [1,2,3,4,5,6,7,8,9]

answer-function flattenedArray(values)
{


  var flattenArray=[];
  values.forEach((element)=>
  {
    flattenArray.push(...flattenedArray(element))
  } else {
    flattenArray.push(element);
  })

  const nestedArray= [1,2,[3,4], [5, [6, 7,[8,[9]]]]] ;
  const flattenedNewArray=flattenedArray(values);
  console.log(flattenedNewArray);



  5)Question-


  const subscriptions={};
  function subscribe(event,callback)

{
  if(!subscription[event])
  {
    subscription[event]=[];
  }
  subscription[event].push(callback);
}







  subscribe('event1',function(value)
  {
    console.log('subscriber1:',value);
  })



