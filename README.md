# NodeJSTricks
nodejs Async.each Nested loop Confusion
async.each(ListA, function(itemA,callback){
    //process itemA
    async.each(itemA.Children/*this should be an array*/, function(itemAChild/*element of the array*/,callback1){
          //process itemAChild
          callback1();
     },function(err){
         console.log("InnerLoopFinished");
         callback();
      }) ;

} ,function(err){
  console.log("OuterLoopFinished");
  console.log('Process Finished');
});



var a = [{x:1,y:2}, {x:3,y:4}, {x:5,y:6}, {x:1,y:2}];

var b = _.uniq(a, function(v) { 
    return v.x && v.y;
})

console.log(b);  // [ { x: 1, y: 2 }, { x: 3, y: 4 }, { x: 5, y: 6 } ]

