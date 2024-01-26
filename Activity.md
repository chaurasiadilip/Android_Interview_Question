What happens to an Activity when the Home button is pressed?
Answer: When the Home button is pressed, the current Activity is moved to the background, and the onPause() method is called, followed by onStop(). The Activity is not destroyed, but it can be killed by the system when memory is needed elsewhere.

2. What happens to an Activity when the Back button is pressed?

Answer: When the Back button is pressed, the current Activity is destroyed, and the previous Activity in the back stack is resumed. The onPause(), onStop(), and onDestroy() lifecycle methods are called in sequence.

3. How can you intercept the Back button press in an Activity?

Answer: You can intercept the Back button press by overriding the onBackPressed() method in your Activity. This allows you to perform specific actions before the Activity is finished.

4. What is the purpose of the onUserLeaveHint() method?

Answer: The onUserLeaveHint() method is called when the user has clicked the Home button or has selected another app through the Recent Apps list. It allows you to detect that the user is leaving your app.

5. How can you launch an Activity when the user presses the Home button?

Answer: Launching an Activity when the Home button is pressed is generally discouraged because it disrupts the standard navigation flow. However, it can be done by creating a launcher Activity that is started when the HOME intent is fired.

6. How can you prevent the Back button from destroying your Activity? Answer: You can prevent the Back button from destroying your Activity by overriding the onBackPressed() method and not calling super.onBackPressed() within that method.

7. What happens to an Activity when the device screen is turned off? Answer: When the device screen is turned off, the onPause() method is called, followed by onStop(). The Activity is not destroyed, but it can be killed by the system when memory is needed elsewhere.

8. What happens to an Activity when a phone call is received?

Answer: When a phone call is received, the onPause() method is called, followed by onStop(). The Activity is not destroyed, but it can be killed by the system when memory is needed elsewhere.

9. What happens to an Activity when a configuration change occurs (like rotation)?

Answer: When a configuration change occurs, the Activity is destroyed and recreated. The onPause(), onStop(), and onDestroy() methods are called, followed by onCreate(), onStart(), and onResume().

10. How can you retain an Activity’s state during a configuration change? Answer: You can retain an Activity’s state during a configuration change by saving the state in the onSaveInstanceState() method and restoring it in onCreate() or onRestoreInstanceState().

11. What happens to an Activity when another Activity is launched on top? Answer: When another Activity is launched on top, the current Activity is paused and stopped, but not destroyed. The onPause() and onStop() methods are called in that order.

12. How can you ensure that an Activity is not destroyed when the user rotates the screen?

Answer: You can ensure that an Activity is not destroyed during a screen rotation by handling the configuration change yourself. This can be done by adding android:configChanges="orientation|screenSize" in the Activity’s declaration in the AndroidManifest.xml.

13. What is the onUserLeaveHint() method in Android?

Answer: The onUserLeaveHint() method is called when the user navigates away from the Activity by pressing the Home button or after a task switch. This method can be overridden to perform actions that should occur only when the user leaves the app out of their own volition.

14. What is the difference between onPause() and onStop()?

Answer: onPause() is called when the Activity is still partially visible, but the user is likely on their way out. onStop(), on the other hand, is called when the Activity is no longer visible.

15. How can you save the state of an Activity before it gets destroyed?

Answer: You can save the state of an Activity before it gets destroyed by implementing the onSaveInstanceState() method and saving the state information as a Bundle.

16. What is the onRestoreInstanceState() method in Android?

Answer: The onRestoreInstanceState() method is called after the onStart() method. It restores the saved state of an Activity from the Bundle that was saved in the onSaveInstanceState() method.

17. What happens to an Activity when the device goes to sleep or when the lock screen appears?

Answer: When the device goes to sleep or when the lock screen appears, the onPause() method is called, followed by onStop(). The Activity is not destroyed, but it can be killed by the system when memory is needed elsewhere.

18. What happens to an Activity when a dialog appears?

Answer: When a dialog appears, the Activity’s onPause() method is called because the Activity loses focus. However, onStop() is not called because the Activity is still visible behind the dialog.

19. What happens to an Activity when you navigate to a different app using the Recent Apps list?

Answer: When you navigate to a different app using the Recent Apps list, the onPause() method is called, followed by onStop(). The Activity is not destroyed, but it can be killed by the system when memory is needed elsewhere.

20. What is the onActivityResult() method in Android?

Answer: The onActivityResult() method is called when an Activity you launched exits, giving you the requestCode you started it with, the resultCode it returned, and any additional data from it.

21. What is the onBackPressed() method in Android?

Answer: The onBackPressed() method is called when the activity has detected the user’s press of the back key. The default implementation simply finishes the current activity, but you can override this to do whatever you want.

22. What is the onUserLeaveHint() method in Android?

Answer: The onUserLeaveHint() method is called when the user navigates away from the activity directly, not because another activity is launched in front of it. This method is typically used to commit unsaved changes to persistent data.

23. What is the onPause() method in Android?

Answer: The onPause() method is called as part of the activity lifecycle when an activity is going into the background, but has not (yet) been killed. The counterpart to onResume().

24. When is onStop() method called in Android?

Answer: onStop() is called when the activity is no longer visible to the user. This may happen because it is being destroyed, or because another activity (either an existing one or a new one) has been resumed and is covering it.

25. What is the onDestroy() method in Android?

Answer: onDestroy() is called before the activity is destroyed. This is the final call that the activity will receive. It could be called either because the activity is finishing (due to the user completely dismissing the activity or due to finish() being called on the activity), or because the system is temporarily destroying the activity due to a configuration change (such as device rotation or multi-window mode).

26. What is the onRestart() method in Android?

Answer: onRestart() is called after your activity has been stopped, prior to it being started again. This is followed by onStart() and onResume().

27. What is the onResume() method in Android?

Answer: onResume() is called when the activity will start interacting with the user. At this point, the activity is at the top of the activity stack, with user input going to it.

28. What is the onStart() method in Android?

Answer: onStart() is called when the activity is becoming visible to the user. It is followed by onResume() if the activity comes to the foreground, or onStop() if it becomes hidden.

29. What is the onCreate() method in Android?

Answer: onCreate() is where you initialize your activity. Most importantly, here you will usually call setContentView(int) with a layout resource defining your UI, and using findViewById(int) to retrieve the widgets in that UI that you need to interact with programmatically.

30. What is the onSaveInstanceState() method in Android?

Answer: onSaveInstanceState() is called to ask the activity to save its current dynamic state, so it can later be reconstructed in a new instance of its process is restarted. If a new instance of the activity is later created, the data you place in the Bundle here will be available in the Bundle given to onCreate(Bundle) and onRestoreInstanceState(Bundle).

31.What is the onRestoreInstanceState() method in Android? Answer: onRestoreInstanceState() is called after onStart() when the activity is being re-initialized from a previously saved state, as given here in savedInstanceState. Most implementations will simply use onCreate(Bundle) to restore their state, but it is sometimes convenient to do it here after all of the initialization has been done or to allow subclasses to decide whether to use your default implementation.

32. What is the onPostCreate() method in Android?

Answer: onPostCreate() is called when activity start-up is complete (after onStart() and onRestoreInstanceState(Bundle) have been called). Applications will generally not implement this method; it is intended for system classes to do final initialization after application code has run.

33. What is the onPostResume() method in Android?

Answer: onPostResume() is called when activity resume is complete (after onResume() has been called). Applications will generally not implement this method; it is intended for system classes to do final initialization after application code has run.

34. What is the onTitleChanged() method in Android?

Answer: onTitleChanged() is called when the activity’s title changes.

35. What is the onChildTitleChanged() method in Android?

Answer: onChildTitleChanged() is called when the title of a child activity changes.

36. What is the onKeyDown() method in Android?

Answer: onKeyDown() is called when a key down event has occurred. If you return true, the event is handled and will not be passed further down the event chain.

37. What is the onKeyLongPress() method in Android?

Answer:onKeyLongPress() is called when a key long press event is up. If you return true, the event is handled and will not be passed further down the event chain.

38. What is the onKeyMultiple() method in Android?

Answer:onKeyMultiple() is called when multiple key events have been fired by the system. This is a common occurrence for keys that are auto-repeated.

39. What is the onKeyUp() method in Android?

Answer: onKeyUp() is called when a key up event has occurred. If you return true, the event is handled and will not be passed further down the event chain.

40. What is the onKeyShortcut() method in Android?

Answer: onKeyShortcut() is called when a key shortcut event has occurred. If you return true, the event is handled and will not be passed further down the event chain.

41. What is the onTouchEvent() method in Android?

Answer: onTouchEvent() is a method that gets called when a touch screen event has occurred. If you return true, the event is handled and will not be passed further down the event chain.

42. What is the onTrackballEvent() method in Android? onTrackballEvent() is a method that gets called when a trackball motion event has occurred. If you return true, the event is handled and will not be passed further down the event chain.

43. What is the onGenericMotionEvent() method in Android? onGenericMotionEvent() is a method that gets called when a generic motion event has occurred. If you return true, the event is handled and will not be passed further down the event chain.

44. What is the onUserInteraction() method in Android? Answer: onUserInteraction() is a method that gets called when the user interacts with the application. It’s often used to reset user inactivity timers or to take some action when the user interacts with your application.

45. What is the onWindowAttributesChanged() method in Android? Answer: onWindowAttributesChanged() is a method that gets called when the current Window of the activity has changed attributes.

46. What is the onWindowFocusChanged() method in Android? Answer: onWindowFocusChanged() is a method that gets called when the current Window of the activity gains or loses focus. This is the best indicator of whether this activity is visible to the user.

47. What is the onCreateThumbnail() method in Android? Answer: Answer:onCreateThumbnail() is a method that gets called when the system needs a new thumbnail for this activity’s task.

48. What is the onCreateDescription() method in Android?

Answer: onCreateDescription() is a method that gets called when the system needs a description of this activity’s current state.

49. What is the onProvideAssistData() method in Android?

Answer: onProvideAssistData() is a method that gets called when the system needs additional information to provide contextual help to the user.

50.What is the onProvideKeyboardShortcuts() method in Android? Answer:onProvideKeyboardShortcuts() is a method that gets called when the system needs to populate the built-in help with information about your application’s keyboard shortcuts.

51. What is an Activity in Android?

Answer: An Activity in Android is a single screen with a user interface. It’s like a window for your application. Each activity can start another activity to perform different actions.

52. What is the lifecycle of an Activity?

Answer: An Activity has several lifecycle methods that are called when the activity’s state changes. These include onCreate(), onStart(), onResume(), onPause(), onStop(), onDestroy(), and onRestart().

53. What is the difference between onPause() and onStop()?

Answer: onPause() is called when the activity is no longer in the foreground but is still visible, while onStop() is called when the activity is no longer visible.

54. What is an Intent?

Answer:An Intent is a messaging object that you can use to request an action from another app component. You can use intents for a wide variety of tasks, but most often they are used to start another activity.

55.What is the difference between startActivity() and startActivityForResult()?

Answer:startActivity() is used to start a new activity without expecting any result back. On the other hand, startActivityForResult() is used when you expect a result back from the new activity.

56. What is a Task in Android?

Answer: A Task is a collection of activities that users interact with when performing a certain job. The activities are arranged in a stack — the back stack) — in the order in which each activity is opened.

57. What is the onSaveInstanceState() method?

Answer:onSaveInstanceState() is a method used to store data before pausing the activity. This data is then passed to onCreate() if the activity needs to be recreated, allowing the app to restore its state.

58. What is a Fragment?

Answer:A Fragment represents a behavior or a portion of user interface in an Activity. You can combine multiple fragments in a single activity to build a multi-pane UI and reuse a fragment in multiple activities.

59.What is the difference between a Fragment and an Activity?

Answer:Both Activity and Fragment are components of Android. However, an Activity is a single, focused thing that the user can do, while a Fragment is a modular part of an activity, which has its own lifecycle, receives its own input events, and can be added or removed while the activity is running.

60. What is Context in Android?

Answer:Context is an abstract class whose implementation is provided by the Android system. It allows access to application-specific resources and classes, as well as calls for application-level operations such as launching activities, broadcasting and receiving intents, etc.

61. What is onActivityResult() in Android?

Answer:onActivityResult() is a method you use to receive the result returned by an activity that was started by startActivityForResult(). It is passed the request code you supplied to startActivityForResult(), a result code it received from the child activity, and an Intent, which can return result data to the caller.

62. What is the difference between finish() and onDestroy()?

Answer:finish() is a method you call to close the current activity. onDestroy(), on the other hand, is a method that is called by the system to notify you that your activity is being removed from the system memory.

63. What is onBackPressed()?

Answer:onBackPressed() is a method called when the activity has detected the user’s press of the back key. The default implementation simply finishes the current activity, but you can override this to do whatever you want.

64. What is onConfigurationChanged()?

Answer: onConfigurationChanged() is a method that gets called by Android system when the device configuration changes while your activity is running. This can occur, for example, when the device screen orientation changes from landscape to portrait.

65. What is the role of the AndroidManifest.xml file?

Answer:AndroidManifest.xml is a central file in an Android project. It presents essential information about the application to the Android system, information the system must have before it can run any of the application’s code.

66. What is an Activity stack?

Answer:An Activity stack (Back stack) is a stack of activities that are currently running and stacked up together. The activity at the top of the stack is the activity running on the screen.

67. What is startActivityFromChild()?

Answer:startActivityFromChild() is a method you call to start an activity from a child activity. The child activity handles the onActivityResult() callback.

68. What is startActivityFromFragment()?

Answer:startActivityFromFragment() is a method you call to start an activity from a fragment. The fragment handles the onActivityResult() callback.

69.What is singleTask launch mode?

Answer:singleTask is a launch mode where the system creates a new task and instantiates the activity at the root of the new task. However, if an instance of the activity already exists in a separate task, the system routes the intent to the existing instance through a call to its onNewIntent() method, rather than creating a new instance.

70. What is singleInstance launch mode?

Answer:singleInstance is a launch mode where a new task will always be created and a new instance will be pushed to the task as the root one. However, if an instance of activity already exists in a separate task, Android will put the existing task to the foreground.

71. What is onNewIntent() in Android?

Answer:onNewIntent() is a method that gets called when the activity receives a new intent while it’s already at the top of the activity stack. This happens when an activity has set its launchMode to singleTop.

72. What is onUserLeaveHint() in Android?

Answer:onUserLeaveHint() is a method that gets called when the user navigates away from the activity directly, not because another activity is launched in front of it. This method is typically used to commit unsaved changes to persistent data.

73. What is onUserInteraction() in Android?

Answer:onUserInteraction() is a method that gets called whenever the user interacts with the application. It’s often used to reset user inactivity timers or to take some action when the user interacts with your application.

74. What is onWindowFocusChanged() in Android?

Answer:onWindowFocusChanged() is a method that gets called when the current Window of the activity gains or loses focus. This is the best indicator of whether this activity is visible to the user.

74. What is onAttachedToWindow() in Android? onAttachedToWindow() is a method that gets called when the window has been attached to the window manager. This is a good place to instantiate objects that contain Paint and Drawable objects that you plan to use with the current window.

75. What is onDetachedFromWindow() in Android?

Answer:onDetachedFromWindow() is a method that gets called when the window has been detached from the window manager. This is a good place to clean up any objects that contain Paint and Drawable objects that you created in onAttachedToWindow().

76. What is onContentChanged() in Android?

Answer:onContentChanged() is a method that gets called when the content view of the screen changes. It’s often used in activities using the Fragments API.

77. What is onCreateDialog() in Android? onCreateDialog() is a method that gets called when a dialog is to be created. It returns an instance of Dialog.

78. What is onPrepareDialog() in Android? onPrepareDialog() is a method that gets called every time a dialog is shown, unlike onCreateDialog() which is only called the very first time a dialog is shown.

79. What is onSearchRequested() in Android?

Answer:onSearchRequested() is a method that gets called when the user signals the desire to start a search by pressing the search key or invoking a search gesture.

80. What is onOptionsItemSelected() in Android?

Answer:onOptionsItemSelected() is a method that gets called whenever an item in your options menu is selected. The default implementation simply returns false to have the normal processing happen (calling the item’s Runnable or sending a message to its Handler as appropriate).

81. What is onOptionsMenuClosed() in Android?

Answer: onOptionsMenuClosed() is a method that gets called whenever the options menu is being closed (either by the user canceling the menu with the back/menu button, or when an item was selected).

82. What is onPrepareOptionsMenu() in Android?

Answer: onPrepareOptionsMenu() is a method that gets called right before the menu is shown, every time it is shown. You can use this method to efficiently enable/disable items or otherwise dynamically modify the contents.

83. What is onPostCreate() in Android?

Answer:onPostCreate() is a method that gets called after onCreate() and after the activity’s primary view has been created. It is often used to finalize the setup of an activity, but post-creation logic here can be moved to onStart().

84. What is onPostResume() in Android?

Answer:onPostResume() is a method that gets called after onResume() and after the activity’s window’s decor view has been marked visible. It is often used to complete the activity setup, such as starting animations.

85. What is onTitleChanged() in Android?

Answer:onTitleChanged() is a method that gets called when the activity’s title changes.

86. What is onChildTitleChanged() in Android?

Answer:onChildTitleChanged() is a method that gets called when the title of a child activity changes.

87. What is onKeyDown() in Android?

Answer: onKeyDown() is a method that gets called when a key down event has occurred. If you return true, the event is handled and will not be passed further down the event chain.

88. What is onKeyLongPress() in Android?

Answer: onKeyLongPress() is a method that gets called when a key long press event is up. If you return true, the event is handled and will not be passed further down the event chain.

89. What is onKeyMultiple() in Android?

Answer:onKeyMultiple() is a method that gets called when multiple key events have been fired by the system. This is a common occurrence for keys that are auto-repeated.

90. What is onKeyUp() in Android?

Answer:onKeyUp() is a method that gets called when a key up event has occurred. If you return true, the event is handled and will not be passed further down the event chain.

91. What is onKeyShortcut() in Android?

Answer:onKeyShortcut() is a method that gets called when a key shortcut event has occurred. If you return true, the event is handled and will not be passed further down the event chain.

92. What is onTouchEvent() in Android?

Answer: onTouchEvent() is a method that gets called when a touch screen event has occurred. If you return true, the event is handled and will not be passed further down the event chain.

93. What is onTrackballEvent() in Android?

Answer: onTrackballEvent() is a method that gets called when a trackball motion event has occurred. If you return true, the event is handled and will not be passed further down the event chain.

94. What is onGenericMotionEvent() in Android?

Answer:onGenericMotionEvent() is a method that gets called when a generic motion event has occurred. If you return true, the event is handled and will not be passed further down the event chain.

95. What is onUserInteraction() in Android?

Answer: onUserInteraction() is a method that gets called when the user interacts with the application. It’s often used to reset user inactivity timers or to take some action when the user interacts with your application.

96. What is onWindowAttributesChanged() in Android? Answer:onWindowAttributesChanged() is a method that gets called when the current Window of the activity has changed attributes.

97. What is onWindowFocusChanged() in Android?

Answer:onWindowFocusChanged() is a method that gets called when the current Window of the activity gains or loses focus. This is the best indicator of whether this activity is visible to the user.

98. What is onCreateThumbnail() in Android?

Answer:onCreateThumbnail() is a method that gets called when the system needs a new thumbnail for this activity’s task.

99.What is onCreateDescription() in Android?

Answer:onCreateDescription() is a method that gets called when the system needs a description of this activity’s current state.

100. What is onProvideAssistData() in Android?

Answer: onProvideAssistData() is a method that gets called when the system needs additional information to provide contextual help to the user.

101. What is onProvideKeyboardShortcuts() in Android? Answer:onProvideKeyboardShortcuts() is a method that gets called when the system needs to populate the built-in help with information about your application’s keyboard shortcuts.

102. What is onEnterAnimationComplete() in Android? Answer:onEnterAnimationComplete() is a method that gets called when the enter animation has completed and the activity is fully visible.

103. What is onTopResumedActivityChanged() in Android? Answer:onTopResumedActivityChanged() is a method that gets called when the top resumed activity changes.

104. What is onVisibleBehindCanceled() in Android? Answer:onVisibleBehindCanceled() is a method that gets called when the activity’s background visibility changes.

105. What is onActionModeFinished() in Android?

Answer:onActionModeFinished() is a method that gets called when an action mode you previously started has been terminated.

106. What is onActionModeStarted() in Android?

Answer:onActionModeStarted() is a method that gets called when an action mode is being started for this window.

107. What is onAttachedToWindow() in Android?

Answer:onAttachedToWindow() is a method that gets called when the window has been attached to the window manager.

108. What is onDetachedFromWindow() in Android?

Answer:onDetachedFromWindow() is a method that gets called when the window has been detached from the window manager.

109.What is onWindowAttributesChanged() in Android? Answer:onWindowAttributesChanged() is a method that gets called when the current Window of the activity has changed attributes.

110. What is onWindowFocusChanged() in Android?

Answer:onWindowFocusChanged() is a method that gets called when the current Window of the activity gains or loses focus. This is the best indicator of whether this activity is visible to the user.

111.What is onCreateThumbnail() in Android?

Answer: onCreateThumbnail() is a method that gets called when the system needs a new thumbnail for this activity’s task.

112.What is onCreateDescription() in Android?

Answer:onCreateDescription() is a method that gets called when the system needs a description of this activity’s current state.

113. What is onProvideAssistData() in Android?

Answer:onProvideAssistData() is a method that gets called when the system needs additional information to provide contextual help to the user.

114. What is onProvideKeyboardShortcuts() in Android? Answer:onProvideKeyboardShortcuts() is a method that gets called when the system needs to populate the built-in help with information about your application’s keyboard shortcuts.

115. What is onEnterAnimationComplete() in Android? Answer:onEnterAnimationComplete() is a method that gets called when the enter animation has completed and the activity is fully visible.

116.What is onTopResumedActivityChanged() in Android?

Answer: onTopResumedActivityChanged() is a method that gets called when the top resumed activity changes.

117. What is onVisibleBehindCanceled() in Android? onVisibleBehindCanceled() is a method that gets called when the activity’s background visibility changes.

118. What is onActionModeFinished() in Android?

Answer:onActionModeFinished() is a method that gets called when an action mode you previously started has been terminated.

119. What is onActionModeStarted() in Android?

Answer:onActionModeStarted() is a method that gets called when an action mode is being started for this window.

120. What is onAttachedToWindow() in Android?

Answer: onAttachedToWindow() is a method that gets called when the window has been attached to the window manager.

121. What is onDetachedFromWindow() in Android?

Answer:onDetachedFromWindow() is a method that gets called when the window has been detached from the window manager.

122. What is onWindowAttributesChanged() in Android? Answer: onWindowAttributesChanged() is a method that gets called when the current Window of the activity has changed attributes.

123.What is onWindowFocusChanged() in Android?

Answer:onWindowFocusChanged() is a method that gets called when the current Window of the activity gains or loses focus. This is the best indicator of whether this activity is visible to the user.

124. What is onCreateThumbnail() in Android?

Answer: onCreateThumbnail() is a method that gets called when the system needs a new thumbnail for this activity’s task.

125.What is onCreateDescription() in Android?

Answer: onCreateDescription() is a method that gets called when the system needs a description of this activity’s current state.

126. What is onProvideAssistData() in Android?

Answer:onProvideAssistData() is a method that gets called when the system needs additional information to provide contextual help to the user.

127. What is onProvideKeyboardShortcuts() in Android? Answer:onProvideKeyboardShortcuts() is a method that gets called when the system needs to populate the built-in help with information about your application’s keyboard shortcuts.

128.What is onEnterAnimationComplete() in Android?

Answer: onEnterAnimationComplete() is a method that gets called when the enter animation has completed and the activity is fully visible.

129.What is onTopResumedActivityChanged() in Android?

Answer: onTopResumedActivityChanged() is a method that gets called when the top resumed activity changes.

130. What is onVisibleBehindCanceled() in Android?

Answer: onVisibleBehindCanceled() is a method that gets called when the activity’s background visibility changes.

131. What is onActionModeFinished() in Android?

Answer:onActionModeFinished() is a method that gets called when an action mode you previously started has been terminated.

132. What is onActionModeStarted() in Android? onActionModeStarted() is a method that gets called when an action mode is being started for this window.

133. What is onAttachedToWindow() in Android?

Answer:onAttachedToWindow() is a method that gets called when the window has been attached to the window manager.

134. What is onDetachedFromWindow() in Android?

Answer:onDetachedFromWindow() is a method that gets called when the window has been detached from the window manager.

134. What is onWindowAttributesChanged() in Android? Answer:onWindowAttributesChanged() is a method that gets called when the current Window of the activity has changed attributes.

135. What is onWindowFocusChanged() in Android?

Answer:onWindowFocusChanged() is a method that gets called when the current Window of the activity gains or loses focus. This is the best indicator of whether this activity is visible to the user.

136. What is onCreateThumbnail() in Android?

Answer: onCreateThumbnail() is a method that gets called when the system needs a new thumbnail for this activity’s task.

137. What is onCreateDescription() in Android?

Answer:onCreateDescription() is a method that gets called when the system needs a description of this activity’s current state.

138. What is onProvideAssistData() in Android?

Answer:onProvideAssistData() is a method that gets called when the system needs additional information to provide contextual help to the user.

139.What is onProvideKeyboardShortcuts() in Android? Answer:onProvideKeyboardShortcuts() is a method that gets called when the system needs to populate the built-in help with information about your application’s keyboard shortcuts.

140. What is onEnterAnimationComplete() in Android?

Answer: onEnterAnimationComplete() is a method that gets called when the enter animation has completed and the activity is fully visible.

141. What is onTopResumedActivityChanged() in Android? Answer:onTopResumedActivityChanged() is a method that gets called when the top resumed activity changes.

142. What is onVisibleBehindCanceled() in Android? Answer:onVisibleBehindCanceled() is a method that gets called when the activity’s background visibility changes.

143. What is onActionModeFinished() in Android?

Answer:onActionModeFinished() is a method that gets called when an action mode you previously started has been terminated.

144. What is onActionModeStarted() in Android?

Answer:onActionModeStarted() is a method that gets called when an action mode is being started for this window.

145. What is onAttachedToWindow() in Android?

Answer:onAttachedToWindow() is a method that gets called when the window has been attached to the window manager.

146. What is onDetachedFromWindow() in Android?

Answer: onDetachedFromWindow() is a method that gets called when the window has been detached from the window manager.

147. What is onWindowAttributesChanged() in Android? Answer:onWindowAttributesChanged() is a method that gets called when the current Window of the activity has changed attributes.

148. What is onWindowFocusChanged() in Android?

Answer:onWindowFocusChanged() is a method that gets called when the current Window of the activity gains or loses focus. This is the best indicator of whether this activity is visible to the user.
