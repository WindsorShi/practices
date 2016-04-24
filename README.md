# practices
####这是三个小练习（真的很小，所以就把js文件放到HTML文件里了）
#####1、将0~100分学员以10分为界，分为十段，然后计算出该生为数字几等生（range.html）  
#####这里注意几个点：  
     （1）onclick="range(document.getElementById('num').value)"num一定要用单引号，括号里的括号里的内容用单引号  
     （2）switch的最后一定要有default：  
          default: alert("errorinput");     
    （3）result.innerHTML=1+"等生";这里用了innerHTML，表示将result的HTML表现写成1+"等生"显示出来  
==================================
#####2、开发简易计算器，输入 x 、y 以及操作符可以计算出数值，如函数计算器输入 4，5，* 可以返回20，输入3 ，8，+可以等于11.
#####这里的注意点：
    （1）在除法情况需要防止分母为0，所以加入这个步骤，且要返回false，跳出这个为/的case   
     else if (o == '/') {
            if (b==0) {
                alert('wronginput');
                return false;
            }
            alert(a / b);
        }  
      （2）这里把a,b的值调出之后必须用parseInt或者parseFloat把原先默认的字符串格式转换成整型或浮点型才能进行计算
        var a = document.getElementById('num1').value;
        var b = document.getElementById('num2').value;
        a = parseFloat(a);
        b = parseFloat(b);
==================================
#####3、找到数组[“a“，”x“，”b“，”d“，”m“，”a“，”k，“m”，“p”，“j”，“a”]出现最多的字母并给出个数和每一个所在的顺序。  
#####详细的代码里面有显示，这里主要是几个用到的函数：    
     （1）indexOf（）：显示元素在数组中第一次出现的位置  
     letter.indexOf(arr[i]) == -1) 如果arr那个数组中的i位置上的字母没有出现在letter那个数组中，  
             那么在letter中该字母的index就会是-1
     （2）push(): 将括号内元素push到数组的最后一位的位置上  
     letter.push(arr[i]); 
     （3）Math.max.apply(Math, num)
       Math.max能找出给出元素中的最大值，但不能用于数组；  
       .apply(XX, num)调用apply的第二个参数必须为数组，在这里就是把num转换成前面Math.max需要的格式对数组num进行操作  
       第一个参数就是：你想让max这个方法里面的this指向的那个人或东西  
       在这里将XX改成任意值都能正常执行，是因为max方法里面的this不影响返回值。  
    （4）arr.splice(i, 1, "");
      在有三个参数的情况下，splice后第一个参数表示要被换掉的元素的位置，第二个元素表示替换掉的个数，第三个元素表示替换元素
     （5）alert这类不识别br
     document.write能识别它
