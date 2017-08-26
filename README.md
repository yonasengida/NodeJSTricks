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

