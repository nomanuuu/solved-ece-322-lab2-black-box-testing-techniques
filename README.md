Download Link: https://assignmentchef.com/product/solved-ece-322-lab2-black-box-testing-techniques
<br>
The objective of this laboratory experiment is to become familiar with several black-box testing techniques, specifically the Extreme Point Combination (EPC), and weak n x 1 testing strategies.

The following sections will serve as an introduction to the testing techniques used in this lab. Please be aware that only those testing techniques required for the assignment need to be used for each task.

Extreme point combination (EPC)

<ul>

 <li>For a given subdomain, complete a single domain analysis in order to identify the domain limits for each dimension (variable).</li>

 <li>Choose test cases for x​i max, min, slightly under min, slightly over max.<sub>​ </sub></li>

 <li>Produce all possible combinations of inputs with each of its variables taking on one of the four values shown above in the n-dimensional space. This should result in <strong>4</strong>​ <strong><sup>n</sup></strong>​<strong> +</strong>​<strong> 1</strong> test cases (one test is added somewhere within the valid subdomain).</li>

</ul>

<h2>Weak n x 1 strategy</h2>

<ul>

 <li><em>Linear boundaries</em>​ of the problem must be identified through domain analysis</li>

 <li>Select <em>n</em>​ ​ points located on the boundary, ​<em>n</em>​ is the dimensionality of the problem</li>

 <li>Plus one point located off the boundary</li>

 <li>Boundaries are linear, hence <em>n</em>​ ​ independent points fully specify each boundary</li>

 <li>If the boundary is ​<strong>open </strong>then​ all points on the boundary recieve exterior processing, choose the additional point within the boundary.</li>

 <li>Else if the boundary is ​<strong>closed </strong>​the all points on the boundary recieve interior processing, choose the additional point outside the boundary.</li>

 <li>This strategy produces ​<strong><em>b(n+1)</em></strong> test cases where ​<em>b</em> is the number of linear boundaries, and ​<em>n</em>​ is the dimensionality.</li>

</ul>

<h2>Test case automation</h2>

<ul>

 <li>In many forms of testing the number of required test cases can become very large very quickly as the system complexity increases.</li>

 <li>Performing large numbers of manual test cases is time consuming and tiresome, something to be avoided.</li>

 <li>Many types of testing can be automated to speed up testing and reduce the effort required by the tester when simple input/output tests are required.</li>

</ul>

<strong><u>Preparation:</u></strong>

Prepare a set of test cases for both tasks you will be completing during the lab session. Follow formatting for test cases similar to the formatting used in lab 1. (ID, description / input values, expected result, actual result). Remember when reporting your test results to ​<strong>highlight</strong> failed test cases.

<h1>Lab Experiment</h1>

For all experiments in this lab, you should only include test cases specific to the testing methods focused on in this assignment. You​<strong> do not</strong>​ ​need to include any error guessing etc test cases for this report.

Task 1 <sub>          </sub>

A new GPS-enabled automated pilot system is being tested for an unmanned reconnaissance aircraft. The benefit of such a system would allow the government to perform peaceful reconnaissance missions without the risk of sending a highly trained pilot and using very expensive aircraft. The system controls the unmanned aircraft from takeoff to landing. The unmanned aircraft has enough fuel to reach a maximum range of some distance <strong><em>k</em></strong>​ before needing to turn back to home base, i.e. <strong><em>k</em></strong>​ is the maximum distance the unmanned aircraft can fly before exceeding the “point of no return.” A maximum of 3 waypoints can be specified in the autopilot system before the unmanned aircraft starts its trek to home base.

The system is simplified by assuming that the unmanned aircraft follows the same path back to its destination. The distances to each waypoint are given by x​1, x<sub>​ </sub>​2<sub>​</sub>, and x​3.<sub>​</sub>

<em>Figure shows  three legs of combined distance less than k. </em>

The application provided for this task takes three inputs: The value of k is hardcoded to 100 for simplicity, and three values for the lengths of each leg of the trip are entered on one line separated by spaces:

<em>drone&gt; x1 x2 x3</em>

The application will output success, failure, or give an explanatory error message. Each value should be specified as an ​<strong>integer </strong>​value.

The application satisfies the following system of inequalities:

x​1 + x<sub>​ </sub>​2 + x<sub>​ </sub>​3 &lt;= k<sub>​                    </sub>

x<sub>1</sub>​ <sub>​</sub> &gt;=0 x​2 &gt;=0<sub>​  </sub> x​3 &gt;=0<sub>​                        </sub>

The application for this task is available on the class website along with running instructions.

<strong>Your task</strong>​ for this portion of the lab is to:

<ul>

 <li>Draw the subdomain for this problem. ​<em>Include this drawing in your report. </em></li>

 <li>Apply the EPC strategy and develop a set of test cases</li>

 <li>Apply the weak nx1 strategy and develop a set of test cases</li>

 <li>Execute your test cases for both types of testing and record your results</li>

</ul>

For ​<strong>your report</strong>​ include:

<ul>

 <li>Your observations and completed test cases, failed test cases should be highlighted, test cases must be presented in a test case table.</li>

 <li>A comparison of the two testing strategies in terms of effectiveness and efficiency (# test cases, discovery of errors, effort)</li>

 <li>Describe any errors you may have found in the application</li>

 <li>A discussion of the root causes of these errors, from what you can tell as a black box tester</li>

 <li>Your subdomain diagram, with labeled axes, must be readable.</li>

 <li>Task 2</li>

</ul>

You are testing a software program that allows you to pilot a remote controlled car. The program accepts Cartesian inputs in the form of (x, y) that specify where the car should move. Your computer radio signal originates at the origin (0,0). Unfortunately, if the car exceeds a maximum distance of ​<strong><em>r</em></strong> from the origin, the signal strength is too weak to be recognized and the instructions fail. This results in a circular domain of radius ​<strong><em>r</em></strong> centered at the origin where the car can be successfully controlled.

Circular boundaries are too complex to test using the linear methods we have learned so far. Hence, we need to approximate the circular subdomain with ​<em>m</em> linear segments. For this lab task we will use a simple case of ​<em>m </em>​= 4, with the new subdomain defined as the square formed within the circular boundary. For simplicity, the radius is hard coded to ​<strong><em>r</em></strong>​ = 1 for this lab experiment.

<em>Approximate subdomain shown in red, center is at the origin. </em>

<em>During test case generation, you should use expected values under the assumption that the domain approximation used is the real domain. </em>

<strong>Your task</strong>​ for this task is to:

<ul>

 <li>Formulate the equations of the approximated linear boundaries</li>

 <li>Apply both the EPC and weak nx1 strategy to this problem</li>

 <li>Develop test cases for each strategy</li>

 <li>Execute your test cases and record the results</li>

 <li>Comment on the use of domain approximation, is it effective? Would a different configuration be better? How would the complexity of the problem be affected?</li>

 <li>Provide a discussion on the effectiveness of your test cases, and how meaningful your tests are considering the approximation, are these strategies efficient?</li>

 <li>Did you identify any errors in the application? Are they approximation errors or real errors?</li>

</ul>

For ​<strong>your report</strong>​ include:

<ul>

 <li>Completed observations and completed test cases</li>

 <li>A comparison of the two strategies for this task</li>

 <li>The equations for the linear segments used to define the problems subdomain</li>

 <li>Your comments on domain approximation

  <ul>

   <li>Would using more linear segments improve the approximation?</li>

   <li>How many test cases would be required for EPC and weak nx1 if we instead used 8 linear segments? Or more?</li>

  </ul></li>

</ul>