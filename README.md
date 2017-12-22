# fuction
 //1: 第一种
 
    let arr = [1,1,2,2,3]
    
    Array.prototype.unique1= function(){
        var newArr =[];
        for(var i=0; i< this.length; i++){
            if( newArr.indexOf(this[i])  == -1 ){
                newArr.push(this[i])
            }
        }
        return newArr
    }
    console.log(arr.unique1());
    //2: 第二种
    Array.prototype.unique2 = function(){
        var newArr =[] , obj = {} ;
        for(var i=0; i< this.length; i++){
            if( !obj[this[i]] ){
                obj[this[i]] = true;
                newArr.push(this[i])
            }
        }
        return newArr;
    }
    console.log(arr.unique2())
    //3: 第三种方式
    Array.prototype.unique3 = function(){
        var newArr =[this[0]] ;
        for(var i=1; i< this.length; i++){
            if(this.indexOf(this[i]) == i ) newArr.push(this[i])
        }
        return newArr;
    }
    console.log(arr.unique3())
    //4
    Array.prototype.unique4 = function() {
        const seen = new Map()
        return this.filter((a) => !seen.has(a) && seen.set(a, 1))
    }
    console.log(arr.unique4 ())
    //5
    Array.prototype.unique5 = function () {
        return Array.from(new Set(this))
    }
    console.log(arr.unique5 ())
