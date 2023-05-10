
# DEVELOPER TOOLS

There are three ways to open the Chrome Developer Tools menu:

- From the Chrome Menu > More Tools > Developer Tools
- Right-click anywhere on a webpage and select Inspect
- Use the keyboard shortcut F12 or CTRL + Shift + C (option + command + C on Mac)


# DEVICE MODE

- Device Mode is a feature in Chrome DevTools that allows developers to simulate different devices and screen sizes to test their web applications.
- The mobile emulation feature within Device Mode can simulate a variety of mobile devices and network conditions to give developers an accurate representation of how their app will behave on different mobile devices.
- Device Mode also allows developers to view their web application in a variety of resolutions, orientations, and pixel ratios.
- Developers can use the Network Throttling feature in Device Mode to simulate various network conditions, such as 3G or 4G connections, to test their app's performance under different network speeds.
- Device Mode also provides a number of useful tools to help developers test and debug their applications, such as the Element Inspector, Console, and Timeline.
- To review these, visit: https://developer.chrome.com/docs/devtools/device-mode/

When debugging, the workflow only applies a fix to the code that is running in your browser. It won't fix the code for all users that visit your page. To do that, you need to fix the code that's on your servers. You can, however, edit files in DevTools and save them to your sources with Workspaces.


# BREAKPOINTS

- JavaScript breakpoints are a debugging feature in Chrome DevTools that allow developers to pause the execution of their JavaScript code at specific lines or statements to inspect the program state and debug issues.


# debugger KEYWORD

- Developers can set breakpoints in their JavaScript code by clicking on the line number in the Sources panel or using the `debugger` keyword in their code.

To use the debugger keyword in the Chrome DevTools Console:

1. Open the Chrome DevTools Console by pressing Ctrl+Shift+J (Windows/Linux) or Cmd+Option+J (Mac).
2. Navigate to the JavaScript file that you want to debug using the "Sources" tab.
3. Locate the line of code where you want to pause execution and insert the debugger statement at that point. For example:

```
function myFunction() {
  var x = 5;
  debugger;
  return x * 2;
}
```
4. Run the JavaScript code. When the code reaches the debugger statement, execution will pause and the debugger will launch.
5. Use the debugger tools to inspect the program state and debug any issues. You can use the "Call Stack" and "Scope" panels to see where you are in the program and what variables are in scope.
6. You can also use the "Sources" panel to step through the code line by line and view the values of variables at each step.

Please note : The debugger keyword doesn't actually highlight the last returned expression value, but it does pause the execution of the JavaScript code at the line where the debugger statement is placed, allowing you to inspect the program state and debug any issues.


# Types of breakpoints

- Line-of-code breakpoints allow developers to pause the execution of their code at a specific line number.
- Conditional breakpoints allow developers to pause the execution of their code when a specific condition is met.
- DOM change breakpoints allow developers to pause the execution of their code when a specified DOM element is modified.
- XHR/fetch breakpoints allow developers to pause the execution of their code when a specified AJAX request is made.

# Setting and managing breakpoints

- Developers can set and manage breakpoints in the Sources panel of Chrome DevTools.
- To set a breakpoint, click on the line number where you want to pause execution.
- To remove a breakpoint, click on the red circle that appears on the line number where the breakpoint is set.
- Developers can manage their breakpoints in the Breakpoints tab of the Sources panel.

# Advanced breakpoint features

- The "Ignore Caught Exceptions" option allows developers to ignore caught exceptions when debugging their code.
- The "Log Message" option allows developers to log a message to the console when a breakpoint is hit.
- The "Conditional" option allows developers to specify a condition that must be true for the breakpoint to be hit.

# Debugging techniques

- Using the `console.log()` function to log variables and other data to the console for debugging.
- Using the `debugger` keyword in your JavaScript code to pause execution at a specific line or statement.
- Using the "Call Stack" and "Scope" panels in the Sources panel to inspect the current state of the program.

# Breakpoint types and when to use them


- Line-of-code breakpoints: When you want to pause execution at a specific line of code to inspect the program state.
- Conditional breakpoints: When you want to pause execution only when a certain condition is met.
- DOM change breakpoints: When you want to pause execution when a specified DOM element is modified.
- XHR/fetch breakpoints: When you want to pause execution when a specified AJAX request is made.