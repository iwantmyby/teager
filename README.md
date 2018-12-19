The teager-py package is a clean Python solution to performing a Teager operation.

<b>To install this package on your computer, run the command:</b><br> 
<pre>
     pip install teager-py
</pre>

<b>Dependencies: </b><br>
<pre>
     (Linux/macOS)
     sudo apt install python3-pip
     sudo apt install python3-numpy
     
     or 
     
     (Windows)
     pip install "numpy‑1.14.2+mkl‑cp36‑cp36m‑win32.whl"
     
</pre>
  
 <b> How to use within your Python CLI: </b>
    
    // You must have numpy dependency installed and imported
    
    $ import numpy as numpy
    
    // Your input array (e.g. test_array) can be in the form of a list or numpy.ndarray
    // However, the output of the Teager operation will always be a numpy array
    
    $ test_array = numpy.array([[1, 1, 1], [1, 1, 1], [1, 1, 1]])
    $ test_array = [[1,1,1], [1,1,1], [1,1,1]]
    
    $ from teager import Teager
    
    // There are two ways of running the Teager operation
    
    $ new_array = Teager(test_array, 'horizontal', 1)
    $ new_array = teager.Teager(test_array, 'horizontal', 1)
    
    // Display the output. It will be a numpy.ndarray with dtype = 'int'
    
    $ print(new_array)
    $ [[0], 
       [0], 
       [0]]
       
<b>Teager Parameters</b>
<pre>
     def Teager(
     teager_array, 
     teager_angle_one: str, 
     teager_one_spread: int, 
     teager_angle_two: str = None, 
     teager_two_spread: int = None, 
     *positional_parameters, 
     **keyword_parameters)
     
<b>teager_array:</b> (list or numpy.ndarray()) - the input array of which will be manipulated by 
the Teager operation within the program

<b>teager_angle_one:</b> (str) - can any of the following options within the list:

     <b> ['horizontal', 'vertical', 'diagonal-right', 'diagonal-left'] </b>
     
     <b> horizontal </b> - the teager operation is looping through a row of the array, 
      whether it is 1-dimensional or 2-dimensional (matrix).
      
     <b> vertical </b> - the teager operation is looping through the columns of the array,
      meaning the array is 2-dimensional (matrix).
      
     <b> diagonal-right </b> - the teager operation is looping through both the columns and rows of 
      the array at an angle of 45 degrees (x<sub>t+1</sub>) and 225 degrees (x<sub>t-1</sub>) 
      about the current value in a loop.
     
     <b> diagonal-left </b> - the teager operation is looping through both the columns and rows of
      the array at an angle of 135 degrees (x<sub>t+1</sub>) and 315 degrees (x<sub>t-1</sub>) 
      about the current value in a loop.
     
<b>teager_one_spread:</b> (int) - the radius from the current number in a loop. 
The teager spread can be either 1 or 2. 

     The teager operation: 
          <b>Teager(x<sub>t</sub>) = x<sub>t</sub><sup>2</sup> + x<sub>t-1</sub> * x<sub>t+1</sub></b>
     
     The 1 within the t - 1 and t + 1 is the radius such that <em>(with r being the radius)</em>:
          <b>Teager(x<sub>t</sub>) = x<sub>t</sub><sup>2</sup> + x<sub>t-r</sub> * x<sub>t+r</sub></b>

<b>teager_angle_two: (optional)</b> (str) - can be any of the following options within the list:

     <b> [None, 'horizontal', 'vertical', 'diagonal-right', 'diagonal-left'] </b>
     
     This field can be left blank as seen within the 'How to use within your Python CLI' section.
     
<b>teager_two_spread:</b> (int) - the radius from the current number in a loop. 
The teager spread can be either 1 or 2. 

     This is the same as teager_one_spread, but instead of changing the radius of teager_angle_one, it determines the radius      of teager_angle_two.

</pre>

    
