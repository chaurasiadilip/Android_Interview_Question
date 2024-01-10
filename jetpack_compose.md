Interview Questions kobweb
1. Add the API calling library.

[libraries]
kobweb-api = { module = "com.varabyte.kobweb:kobweb-api", version.ref = "kobweb" }
kobweb-core = { module = "com.varabyte.kobweb:kobweb-core ", version.ref = "kobweb" }

[plugins]
serialization-plugin = { id = "org.jetbrains.kotlin.plugin.serialization", version.ref = "kotlin" }
Interview Questions KMM — KMP
1. What is Kotlin Multiplatform (KMP) and how does it differ from other cross-platform development solutions?

Kotlin Multiplatform (KMP) is a cross-platform development framework that allows developers to write code once and use it on multiple platforms, such as Android, iOS, and web.
It differs from other solutions like Flutter and React Native by providing a more native and integrated development experience for each platform while sharing common code.
2. Advantages of Utilizing Kotlin Multiplatform (KMM) in Projects

Code sharing: Encourages code reuse and reduces duplication, leading to faster development.
Faster time-to-market: Accelerates mobile app development by reducing codebase development.
Consistency: Ensures consistency across platforms for better user experience.
Collaboration between Android and iOS teams: Facilitates collaboration between Android and iOS development teams to improve efficiency.
Access to Native APIs: Allows developers to access platform-specific APIs and features.
Reduced maintenance overhead: Shared codebase makes maintenance easier and more efficient.
Existing Kotlin and Android ecosystem: Provides access to libraries, tools, and resources for developers.
Gradual adoption: Facilitates cross-platform development by sharing modules and components.
Performance and efficiency: Generates optimized code for each platform, resulting in efficient and performant applications.
3. Explain Expect and Actual in Platform specific code.

expect is like an announcement you make in your shared code. It’s like saying, “Hey, I need something specific to be done here, but I don’t know how each platform will accomplish it.”
How to Use: You declare a function, interface, class, or property with the expect keyword in your shared code, but you don’t provide an implementation.
Actual is the response to your expect announcement. On each platform, you use actual to say, “Here’s how we’re going to handle what you were expecting.”
How to Use: On each specific platform (Android & iOS), you provide a concrete implementation of what was declared with expect.
Interview Question Jetpack Compose
What is Android Jetpack Compose, and why was it introduced?
Android Jetpack Compose is a modern UI toolkit introduced by Google for building native Android applications. It was introduced to simplify and enhance the UI development process by providing a declarative and reactive approach to building UIs.
Jetpack compose work

The jetpack compose works on a composite design pattern.
This pattern is used while dealing with hierarchical data like a parent-child relationship.
In compose, every view can contain one or more child views within it, and the child views can further have sub-child views.
Configure compose project

androidx.compose:compose-bom: Version manager for Compose libraries.
androidx.compose.ui:ui: Central library of Compose that contains elements for building user interfaces.
androidx.compose.ui:ui-graphics: Provides essential graphic functionalities, such as custom drawings and manipulation of graphic elements.
androidx.compose.ui:ui-tooling-preview: Provides visualization and testing of compositions in the Compose development environment.
buildFeatures — compose true: Enables support for Jetpack Compose in theproject.
composeOptions: Ensures compatibility between the Kotlin and Compose versions during the development step.
2. Explain the difference between View-based UI framework and Jetpack Compose.

The View-based UI framework uses XML layout files and imperative code to create and manage UI components. Jetpack Compose, on the other hand, uses a declarative approach where UI components are described as functions of the application state. Compose simplifies UI development, reduces boilerplate code, and provides a more intuitive way to create interactive UIs.
Imperative means describing how and Declarative means describing what.
Jetpack Compose can draw UI in a declarative way to describe data like the Text("Hello world") composable.
Android XML can draw UI in an imperative way to describe data likes textView.setText("Hello world").
3. What are the basic building blocks of a Jetpack Compose UI?

The basic building blocks of a Jetpack Compose UI are Composables. Composables are functions that describe a UI element or a group of UI elements.

4. What are the advantages of using Jetpack Compose over the traditional View system?

Advantages of Jetpack Compose include:

Declarative UI: Compose allows developers to describe the UI based on the current state, making the code more concise and readable.
Live Previews: Compose offers real-time UI previews in Android Studio, enabling instant visual feedback during development.
Simplified State Management: Compose simplifies state management by automatically recomposing only the affected parts of the UI when the state changes.
Enhanced Performance: Compose leverages efficient rendering and diffing algorithms, resulting in improved performance compared to the traditional View system.
5. What is a Composable function in Jetpack Compose?

A Composable function is a regular Kotlin function annotated with the @Composable annotation. It is the fundamental building block in Jetpack Compose and describes a UI component's appearance and behavior. Composable functions are independent of the activity or fragment lifecycle, making them reusable and testable.
Composable function we thought that it takes an input and return something as output, but internally an action is registered to add the element to the in-memory representation of the composable tree. The registered actions are called ‘emmiting’.
Using Compose, you can build your user interface by defining a set of composable functions that take in data and emit UI elements. A simple example is a Greeting widget, which takes in a String and emits a Text widget which displays a greeting message.
6. How does state management work in Jetpack Compose?

State management in Jetpack Compose revolves around the concept of a mutable state. Compose provides the mutableStateOf function to create observable state objects. When the state changes, Jetpack Compose automatically recomposes only the affected parts of the UI, ensuring efficient UI updates.
7. What is the role of the Modifier in Jetpack Compose?

The modifier is an ordered, immutable collection of modifier elements that decorate or add behavior to Compose UI elements. For example, backgrounds, padding, and click event listeners decorate or add behavior to rows, text, or buttons.
The Modifier is used to customize and apply transformations to UI elements in Jetpack Compose. It allows you to specify properties such as size, padding, alignment, background color, and more. Modifiers can be chained together to apply multiple transformations to a single UI element.
Most Compose UI elements, such as Surface and Text, accept an optional modifier parameter. Modifier parameters tell a UI element how to lay out, display, or behave within its parent layout. Modifiers are regular Kotlin objects.
8. How is navigation handled in Jetpack Compose?

Navigation in Jetpack Compose is handled using the Navigation Compose library. It introduces the concept of navigation graphs, where each screen or destination is represented by a composable function. The navigation graph defines the connections between destinations, and navigation actions can be triggered using predefined navigation methods.
9. Explain the concept of recomposition in Jetpack Compose.

Recomposition is the process of calling your composable functions again when inputs change. This happens when the function’s inputs change. When Compose recomposes based on new inputs, it only calls the functions or lambdas that might have changed, and skips the rest. By skipping all functions or lambdas that don’t have changed parameters, Compose can recompose efficiently.
Recomposition is the process of automatically updating only the parts of the UI that have changed when the state variables of a Composable function are modified. Jetpack Compose tracks the dependencies between Composable functions and their state variables.
When a state variable changes, only the affected Composable functions are recomposed, ensuring efficient UI updates.
10. How can you handle user input and events in Jetpack Compose?

User input and events can be handled using event callbacks and state variables in Jetpack Compose. Composable functions can define event callbacks that are triggered when a user interacts with the UI. These callbacks can modify the state variables, leading to UI recomposition and updates.
11. What is the purpose of ViewModel in Jetpack Compose?

ViewModel in Jetpack Compose is used for managing and preserving UI-related data across configuration changes. It provides a way to separate the UI logic from the UI components and allows sharing data between multiple Composable functions. ViewModels can be accessed using the viewModel or viewModel<>() functions.
12. How does Jetpack Compose integrate with existing Android frameworks and libraries?

Jetpack Compose can be integrated with existing Android frameworks and libraries by using interoperability features. Compose provides compatibility libraries to bridge the gap between Compose and existing View-based UI components. Additionally, Compose supports the embedding of traditional View-based components within Composable functions using the AndroidView or ComposeView APIs.
13. What are the key components of the Jetpack Compose architecture?

The key components of the Jetpack Compose architecture include Composable functions, state management, the Modifier system, navigation with the Navigation Compose library, ViewModel, and integration with existing Android frameworks.
14. How do you perform animations in Jetpack Compose?

Animations in Jetpack Compose can be performed using the animate* family of functions. These functions allow you to animate changes to UI properties, such as size, position, opacity, and color. Jetpack Compose handles the animation updates and UI recomposition automatically.
15. What is the purpose of ConstraintLayout in Jetpack Compose?

ConstraintLayout is nothing but a composable function that can position its children based on the constraints specified. It also takes a modifier as an optional parameter.
ConstraintLayout in Jetpack Compose is used to create complex and responsive layouts.
ConstraintLayout is a layout that allows you to place composables relative to other composables on the screen.
It allows you to define constraints between UI elements, enabling flexible positioning and resizing based on the available space.
ConstraintLayout helps in building dynamic and adaptive UIs.
ConstraintLayout is useful when implementing larger layouts with more complicated alignment requirements.
16. How do you handle theming and styling in Jetpack Compose?

Theming and styling in Jetpack Compose are handled using the MaterialTheme and @Composable functions. MaterialTheme provides a pre-defined set of styles and attributes, while the @Composable function allows for creating custom styles and applying them to UI elements.
17. Explain the concept of side effects in Jetpack Compose.

Side effects in Jetpack Compose refer to operations that have additional effects beyond modifying the UI state. Examples include making network requests, accessing databases, or updating shared preferences. Side effects are handled using functions like LaunchedEffect or DisposableEffect, which allow you to perform these operations while ensuring proper lifecycle management.
18. How can you handle asynchronous operations in Jetpack Compose?

Asynchronous operations in Jetpack Compose can be handled using Kotlin coroutines and the suspend function modifier. You can launch coroutines within Composable functions using LaunchedEffect or other coroutine builders. This allows you to perform asynchronous operations off the main thread and update the UI when the operation completes.
19. What are Compose key events, and how are they used?

Compose key events allow you to handle keyboard events, such as key presses, in Jetpack Compose. You can use the onKeyEvent modifier to listen to key events and define the corresponding actions within Composable functions.
20 . How do you test UI components in Jetpack Compose?

Jetpack Compose provides a testing framework that allows you to write tests for UI components. You can use the @Composable test rule and the composeTestRule to interact with and assert the behavior of Composable functions and UI elements.
21. What is the purpose of remember in Jetpack Compose, and how is it used?

The remember function in Jetpack Compose is used to create and store a value that survives recomposition. It allows you to preserve and reuse expensive computations or expensive objects, optimizing performance by avoiding unnecessary recomputations.
The remember function allows a composable to keep a value in memory across recompositions.
22. What is the role of StateFlow and SharedFlow in Jetpack Compose?

StateFlow and SharedFlow are part of the Kotlin coroutines library and can be used in Jetpack Compose for managing state and asynchronous data streams. StateFlow represents a state value that can be observed for changes, while SharedFlow represents a hot data stream that can be collected by multiple collectors.
23. How can you handle input validation in Jetpack Compose?

Input validation in Jetpack Compose can be handled by combining state management and event callbacks. You can use state variables to hold the input values and define validation logic within event callbacks or helper functions. Based on the validation results, you can update the UI to provide feedback to the user.
24. Explain the concept of lazy composition in Jetpack Compose.

Lazy composition in Jetpack Compose allows you to defer the execution of expensive Composable functions until they are actually needed. It helps optimize performance by only recomposing and rendering UI components when they become visible or relevant to the current state.
25. What are recomposition triggers, and how can you use them?

Recomposition triggers are used to manually trigger recomposition of specific parts of the UI. They allow you to control the timing of UI updates and ensure that only the necessary parts are recomposed. Recomposition triggers can be used in scenarios where you want to force an update, such as handling external events or user interactions.
26. How can you handle keyboard input in Jetpack Compose?

Keyboard input in Jetpack Compose can be handled using the TextField component. It provides an editable text field that allows users to enter text and handles keyboard events, such as input changes or key presses. You can customize the behavior of the TextField using various parameters and modifiers.
27. What is the role of CompositionLocal in Jetpack Compose?

CompositionLocal in Jetpack Compose is used to provide values that can be accessed by the Composable functions in the composition tree. It allows you to pass down values, such as themes, fonts, or other contextual information, without explicitly passing them through function parameters.
28. How do you handle orientation changes in Jetpack Compose?

Orientation changes in Jetpack Compose are handled automatically by recomposing the UI based on the new configuration. Composable functions that define the UI layout and behavior will be recomposed with the updated configuration, allowing the UI to adapt to the new orientation.
29. Explain the concept of accessibility support in Jetpack Compose.

Accessibility support in Jetpack Compose allows you to create UIs that are accessible to users with disabilities. Compose provides accessibility modifiers, such as semantics, screenReaderOnly, and clickable, to enhance the accessibility of UI elements. You can also use setContentDescription to provide meaningful descriptions for screen readers.
30. How can you integrate Jetpack Compose with data binding?

Jetpack Compose can be integrated with data binding by using the observeAsState function. It allows you to observe LiveData objects from the data binding library and use them as state variables within Composable functions. This enables seamless integration between Compose and data binding in mixed projects.
31. What are the best practices for performance optimization in Jetpack Compose?

Some best practices for performance optimization in Jetpack Compose include:
Minimize unnecessary recompositions by using immutable state objects and avoiding excessive state changes.
Use the remember function to cache expensive computations and avoid unnecessary recomputations.
Use the key parameter to explicitly control the identity of Composable functions and optimize the diffing algorithm.
Use LaunchedEffect and other coroutine-based APIs to perform asynchronous operations off the main thread and ensure smooth and responsive user interfaces in Jetpack Compose.
The View-based UI framework uses XML layout files and imperative code to create and manage UI components. Jetpack Compose, on the other hand, uses a declarative approach where UI components are described as functions of the application state. Compose simplifies UI development, reduces boilerplate code, and provides a more intuitive way to create interactive UIs.
32. Explain the side effects of jetpack compose.

Side effect is an operation or action that happens outside the normal flow of the Composable function and can have an impact on the Composable’s behavior or the UI. These side effect handlers are used to manage and control such side effects.
class MainActivity : ComponentActivity() {

    var i=0 //Outside of compose

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            AppTheme {
                Button(onClick = {}){
                    i++//SIDE EFFECT
                    Text(i.toString())
                }
            }
        }
    }
}
Due to composables’ lifecycle and properties such as unpredictable recompositions, executing recompositions of composables in different orders, or recompositions that can be discarded, composables should ideally be side-effect free.
Here are the explanations of the side effect handlers you’ve mentioned in bullet points:
LaunchedEffect
- LaunchedEffect allows you to call suspend functions safely within a composable.
- It launches a coroutine with the provided block of code and ensures that the coroutine is cancelled when the composable leaves the composition.
- It is typically used for performing asynchronous operations or triggering one-time / first, launched or relaunched, or when the key parameter has changed.
- Uses: For showing Snackbar, For re-setting UiStates, For Navigation Events, Starting Animations/Some one-time events
RememberCoroutineScope
- Helpful when you are using coroutines and need to manage the coroutine’s lifecycle within a Composable.
- Allows you to cancel and relaunch a coroutine after a specific event or condition.
- The CoroutineScope object created by rememberCoroutineScope() is a singleton for each composition. This means that if the function is called multiple times within the same composition, it will return the same coroutine scope object.
- For example: Snackbar
RememberUpdatedState
- There are situations where you need to access the latest state of a Composable, even when it changes within a Composable function. Useful when you want to compare and track changes in a Composable’s state between recompositions.
- Often used when you have two tasks, one short and one long, and you want to avoid the long task from repeating every time the short task runs.
- For example: CheckBox, RadioButton on click
DisposableEffect
- Used for cleaning up a Composable to prevent memory leaks and release resources when it is removed from the composition.
- Useful for managing resources such as subscriptions or listeners.
ProduceState
- ProduceState is used to convert non-Compose state, such as Flow, LiveData, or RxJava, into Compose state. It launches a coroutine scoped to the composition and updates the State object based on the emitted values from the non-Compose state source.
- Helps integrate external data sources or non-Composable state into the Composable world.
- It is run background thread.
DerivedStateOf
- Allows you to derive a new state value based on multiple other states.
- Useful for creating computed properties or aggregating information from different parts of your Composable tree.
SnapshotFlow
- Used to convert Composable state into a Flow, which is a reactive stream of data.
- Useful for exposing Composable state as a Flow so that it can be observed and reacted to by external components. This compose function is used to convert a compose state into a flow that emits values whenever a compose state changes.
- Analysis value: Get old and previous value, filter, add or even
val listState = rememberLazyListState()

LazyColumn(state = listState) {
    // ...
}

LaunchedEffect(listState) {
    snapshotFlow { listState.firstVisibleItemIndex }
        .map { index -> index > 0 }
        .distinctUntilChanged()
        .filter { it == true }
        .collect {
            MyAnalyticsService.sendScrolledPastFirstItemEvent()
        }
}
31. CircularProgressIndicator in center Jetpack Compose?

Box(modifier = modifier.fillMaxSize()) {
    CircularProgressIndicator(modifier = Modifier.align(Alignment.Center))
}
32. What is state?

The state function is used to create a mutable state that can be observed, and when the state changes, the composable is recomposed. A state can be read and modified within a composable function.
A state is a value that affects changes, the UI will update to reflect these changes. To make compose recognize state changes, you need to wrap your state values in a state object.
Whenever the composable is listening to a snapshot state, any change in the state will be reflected by the composable.
Changes in the value of a snapshot state propagate as follows:

Compose goes up the UI tree to find the closest common affected scope (restart scope) and triggers re-execution of the composables.
Re-execute the composables affected by the change in state value (recomposition)

33. What is MutableState?

It will return a MutableState<T> object. Compose will then be able to track any changes made to the value and automatically update the UI accordingly.
34. What is remember?

remember{} indicates that a certain value passed to it should be remembered so that the lamda expression is not executed with every recomposition.
mutableStateOf(true) will produce a MutableState<Boolean>
35. What is delegation?

In general terms, “delegation” refers to a scenario where a responsibility or task is assigned to another entity. In Kotlin, delegation allows the transfer of certain functionalities to another class or property with the help of the by keyword.
36. Expain render compose?

This is a unidirectional flow that happens from composition to drawing to produce a frame.
Each frame that is drawn on the screen goes through different phases. Compose renders its composables through three steps:

Composition: What UI to show? Builds a UI tree of compose functions.
Layout: Where to place UI? This phase consists of two steps: measurement and placement. Compose measures the children if any, and place themselves accordingly in the 2D space.
Drawing: How it renders. Rendering it on pixels.
Composition
During the composition phase, the Compose runtime executes your composable functions.
It outputs a tree data structure that represents your UI. This UI tree consists of layout nodes.
Together, these layout nodes hold all the information needed to complete the next phases.
layout phase
Then, during the layout phase, each element in the tree measures its children, if any, and places them in the available 2D space.
drawing phase
Finally, in the drawing phase, each node in the tree draws its pixels on the screen
37. TextField enters the value number of ways to set data.


38. Explain the counter application.

@Composable
fun Counter(count: Int, onIncrement: () -> Unit) {
    Text("$count")
    Button(onClick = { onIncrement() }) {
        Text(text = "Click Me")
    }
}

@Composable
fun HomeScreen() {
    var count by remember { mutableIntStateOf(0) }
    Counter(count = count, onIncrement = { count++ } )
}

/*
@Composable
fun Counter(count: Int, onIncrement: () -> Unit) {
    Text("$count")
    Button(onClick = { onIncrement.invoke() }) {
        Text(text = "Click Me")
    }
}
*/

/*
@Composable
fun Counter(count: Int, onIncrement: (() -> Unit)? = null) {
    Text("$count")
    Button(onClick = { onIncrement?.invoke() }) {
        Text(text = "Click Me")
    }
}
*/
39. Types of KMM Navigation Support Library?

Decompose
voyager
precompose
Appyx
39. What is Surface Composable?

One of the easiest composable is a bloc of UI that is displayed on the screen, which can have a color and background color.
40. What is the Declarative approach?

It means we have a data flow and an events flow. In the compose hierarchy the data flows from top to bottom, meaning the parent composable flows data to its child composable. And the events are triggered from child to parent i.e. bottom to top.
40. Explain the KTX library.

Android KTX is a set of Kotlin extensions that are included with Android Jetpack and other Android libraries. KTX extensions provide concise, idiomatic Kotlin to Jetpack, Android platform, and other APIs. To do so, these extensions leverage several Kotlin language features, including the following:

Extension functions: These are the functions that help us to extend the functionality of the class without getting into the code of that class i.e. you just have to call the function of the class
Extension properties: Kotlin also supports extension properties. But in order to use the extension property in Kotlin, you have to explicitly provide the getter (plus setter for vars).
Lambdas: Lambda functions are anonymous functions that can be passed as arguments to methods, you can return them or you can perform all the operations that you can perform on a regular object.
Named parameters: This is a feature that is not present in some other object-oriented language. Kotlin provides a way to specify the name of the arguments that you are passing while a function call.
Parameter default values
Coroutines
41. What is the difference between inject and get in koin?

inject: lazy evaluated delegated instance
get: eager access for instance
private val signInUseCase by inject<SignInUseCase>()
private val signInUseCase = get<SignInUseCase>()
42. collectAsState

val podcasts = viewModel.podcasts.collectAsState()
Observes viewModel.podcasts containing with the help of .collectAsState(). This means that list of cards will be diffed & recomposed each time the value of viewModel.podcasts changes.
43. What is the SavedStateHandle?

It is an object that we use from ViewModel and that allows us to manage what is saved in this state without having to communicate with the Activity.
It is a collection of key/value elements that we can access as if it were a map.
By using SavedStateHandle, the query value is persisted across process termination, ensuring that the user sees the same set of filtered data before and after re-creation without requiring the Activity or Fragment to manually save, restore, and re-transfer the value to the ViewModel.
SavedStateHandle contains other methods that you may use when interacting with the key-value map:
contains(String key) — Checks if there is a value for the given key.
remove(String key) — removes the value of the given key.
keys() — Returns all the keys contained in the SavedStateHandle.
SavedStateHandleThe usage process is generally as follows:
will be SavedStateHandle used as ViewModel a constructor parameter of
ViewModelSavedStateHandle.getLiveDataInternally , an LiveData object is generated through the method, LiveData and the data in it is the data we want to persist. If it is a fresh start Activity, LiveData the value saved in null; if it is rebuilt, Activity the LiveData value saved in 2 is its own value before the rebuild
getLiveDataThe String parameter passed to the method is a unique one Key, and the key-value pair that is finally saved Bundle in is taken as this value Key, and LiveData the value of is taken as value.
43. DropDown Arrow rated using animation.

var expanded by remember { mutableStateOf(false) }
val angle: Float by animateFloatAsState(targetValue = if (expanded) 180f else 0f)
44. Explain setContent in Jetpack Compose.

The setContent block defines the root view of the activity that we call composable functions.
The setContent block defines the activity's layout where composable functions are called.
Composable functions can only be called from other composable functions.
Jetpack Compose uses a Kotlin compiler plugin to transform these composable functions into the app’s UI elements.
45. Write login Like — Unlike.

Favourite  remember
val (isFavorite, setFavorite) = remember { mutableStateOf(false) }
setFavorite(!isFavorite)
46. Write a code marquee code non-text and text composable.

Text(
      text = "",
      modifier = Modifier.basicMarquee()
)
@OptIn(ExperimentalFoundationApi::class)
@Composable
private fun MarqueeEffect() {
    Box(
        modifier = Modifier.fillMaxSize(),
        contentAlignment = Alignment.Center
    ) {
        val focusRequester = remember { FocusRequester() }
        Text(
            modifier = Modifier
                .basicMarquee(animationMode = MarqueeAnimationMode.WhileFocused)
                .focusRequester(focusRequester)
                .focusable()
                .clickable { focusRequester.requestFocus() },
            text = "Compose has finally added support for Marquee! It's soo easy to implement!"
        )
    }
}
47. Explain FlingBehavior?

A FlingBehavior that performs snapping of items to a given position.

 val lazyListState: LazyListState = rememberLazyListState()

        LazyRow(
            modifier = Modifier.fillMaxWidth(),
            state = lazyListState,
            flingBehavior = rememberSnapperFlingBehavior(lazyListState),
            contentPadding = PaddingValues(8.dp),
            verticalAlignment = Alignment.CenterVertically,
        ) {
            items(items = placeholderItems) { itemMessage: String ->
                PlaceholderCard(itemMessage)
            }
        }
48. Write UI Code.


@ExperimentalMaterial3Api
@Composable
fun CompactWeatherCard(
    nameOfLocation: String,
    shortDescription: String,
    @DrawableRes shortDescriptionIcon: Int,
    weatherInDegrees: String,
    onClick: () -> Unit,
    modifier: Modifier = Modifier
) {
    val weatherWithDegreesSuperscript = remember(weatherInDegrees) {
        "$weatherInDegrees°"
    }
    OutlinedCard(modifier = modifier, onClick = onClick) {
        Row(
            modifier = Modifier
                .fillMaxWidth()
                .padding(16.dp),
            horizontalArrangement = Arrangement.SpaceBetween,
            verticalAlignment = Alignment.CenterVertically
        ) {
            // add weight modifier to the column composable to ensure 
            // that the composable is measured after the other 
            // composable is measured.
            Column(modifier = Modifier.weight(1f)) { 
                Text(
                    text = nameOfLocation,
                    maxLines = 1,
                    overflow = TextOverflow.Ellipsis,
                    style = MaterialTheme.typography.titleLarge,
                    fontWeight = FontWeight.Medium
                )
                ShortWeatherDescriptionWithIconRow(
                    shortDescription = shortDescription,
                    iconRes = shortDescriptionIcon
                )
            }
            Text(
                text = weatherWithDegreesSuperscript,
                style = MaterialTheme.typography.displayMedium
            )
        }
    }
}
49. Setting Scope custom compose.

interface SettingsSectionScope {
    fun item(
        icon: ImageVector? = null,
        title: String,
        subtitle: String? = null,
        endSlot: @Composable () -> Unit = { },
        onClick: (() -> Unit)? = null,
    )

    @Composable
    fun Icon(imageVector: ImageVector) {
        Icon(
            modifier = Modifier
                .size(24.dp),
            painter = rememberVectorPainter(imageVector),
            contentDescription = null
        )
    }
}

private class SettingsSectionScopeImpl : SettingsSectionScope {

    val items = mutableListOf<@Composable () -> Unit>()

    override fun item(
        icon: ImageVector?,
        title: String,
        subtitle: String?,
        endSlot: @Composable () -> Unit,
        onClick: (() -> Unit)?,
    ) {
        items += {
            SettingsItem(
                title = title,
                subtitle = subtitle,
                icon = icon?.let { { Icon(it) } },
                endSlot = endSlot,
                onClick = onClick,
            )
        }
    }
}

@Composable
fun SettingsItem(
    modifier: Modifier = Modifier,
    title: String,
    icon: (@Composable () -> Unit)? = null,
    subtitle: String? = null,
    endSlot: @Composable () -> Unit = { },
    onClick: (() -> Unit)? = null,
) {
    Row(
        modifier = modifier
            .addIf(onClick != null) { Modifier.clickable { onClick?.invoke() } }
            .padding(
                vertical = MaterialTheme.dimens.staticGrid.x4,
                horizontal = MaterialTheme.dimens.staticGrid.x3
            ),
    ) {
        CompositionLocalProvider(LocalContentColor provides MaterialTheme.colorScheme.onSurface) {
            icon?.invoke()
            Column(
                modifier = Modifier
                    .padding(start = MaterialTheme.dimens.staticGrid.x2)
                    .weight(1f)
            ) {
                Text(title)
                if (subtitle != null) {
                    Text(
                        subtitle,
                        color = LocalContentColor.current.copy(alpha = 0.54f),
                        style = MaterialTheme.typography.bodyMedium
                    )
                }
            }
        }
        Box(
            modifier = Modifier
                .padding(
                    end = if (onClick == null) MaterialTheme.dimens.staticGrid.x2 else 0.dp)
        ) {
            endSlot()
        }
        if (onClick != null) {
            Icon(
                modifier = Modifier
                    .align(Alignment.CenterVertically)
                    .padding(start = MaterialTheme.dimens.staticGrid.x1),
                imageVector = Icons.Rounded.ChevronRight,
                tint = MaterialTheme.colorScheme.onSurfaceVariant,
                contentDescription = null
            )
        }
    }
}

@Composable
fun SettingsSection(
    modifier: Modifier = Modifier,
    title: String? = null,
    backgroundColor: Color = MaterialTheme.colorScheme.surface,
    contentColor: Color = MaterialTheme.colorScheme.onSurface,
    content: SettingsSectionScope.() -> Unit,
) {
    Column(
        modifier = modifier,
        verticalArrangement = Arrangement.spacedBy(MaterialTheme.dimens.staticGrid.x2)
    ) {
        if (title != null) {
            Text(text = title, style = MaterialTheme.typography.titleMedium)
        }
        Surface(
            modifier = Modifier.fillMaxWidth(),
            tonalElevation = 0.dp,
            shadowElevation = 2.dp,
            color = backgroundColor,
            contentColor = contentColor,
            shape = MaterialTheme.shapes.large
        ) {
            val scope = remember { SettingsSectionScopeImpl() }
                .apply(content)
                .items
            Column {
                scope.forEach { item ->
                    item()
                }
            }
        }
    }
}
50. How to set KamelImage?

val image: Resource<Painter> = asyncPainterResource(data = "URL")
                KamelImage(
                    resource = image,
                    contentDescription = null,
                    contentScale = ContentScale.Crop,
                    //contentScale = ContentScale.FillBounds
                    modifier = Modifier
                        .fillMaxWidth()
                        .height(200.dp),
                    onLoading = {
                        CircularProgressIndicator(it)
                    },
                    onFailure = {
                        Text(text = "Failed to Load Image")
                    },
                    animationSpec = tween(),
                    modifier = Modifier
                        .size(40.dp)
                        .clip(CircleShape),
                )
51. How to set Image?

channelData?.URL?.let {
                    rememberImagePainter(
                        it
                    )
                }?.let {
                    Image(
                        painter = it,
                        contentDescription = null,
                        modifier = Modifier
                            .size(60.dp)
                            .clip(CircleShape),
                        contentScale = ContentScale.FillBounds
                    )
                }
52. How to set condition Modifier in jetpack compose?

//1 way
fun Modifier.thenIf(
    condition: Boolean,
    vararg modifier: Modifier.() -> Modifier
): Modifier =
    if (condition) {
        var all: Modifier = Modifier
        modifier.forEach {
            all = all.then(it(Modifier))
        }
        then(all)
    } else {
        this
    }

Box(
                        modifier = Modifier
                            .thenIf(
                                condition = true,
                                { border(border = BorderStroke(1.dp, Color.Black)) },
                                { background(Color.LightGray) }
                            )
                    ) {
                        // ...
                    }

//2 Way
fun Modifier.thenIf(condition: Boolean, thanModifier: @Composable Modifier.() -> Modifier): Modifier = composed {
    if (condition) {
        this.thanModifier()
    } else {
        this
    }
}

@Composable
fun MyBox(
    modifier: Modifier =  Modifier,
    isFocused: Boolean
) {
    Box(
        modifier = modifier
            .thenIf(isFocused){
                border(border = BorderStroke(1.dp, Color.Black))
            }
            .thenIf(isFocused){
                background(Color.LightGray)
            }
    ) {
        // ...
    }
}
53. Explain Modifier.composed()

Implement a just-in-time composition of a Modifier that can be used for each element. This approach is suitable for creating stateful modifiers that have individual instance-specific state for every modified element . By doing so, the same Modifier instance can be safely reused for multiple elements , while preserving the element-specific state.

54. Explain Modifier.onSizeChanged

Modifier.onSizeChanged is used for responding to size changes of a composable. This modifier can be particularly useful in scenarios where you need to perform actions or adjust the layout based on the size of a component, which might not be known until runtime.

It Works

The onSizeChanged modifier provides a callback with the new size of the composable whenever it changes.
This size information can be used to make decisions or trigger actions in your UI.
Box(
        modifier = Modifier
            .fillMaxWidth()
            .onSizeChanged { newSize ->
                containerWidth = newSize.width.dp
            },
    ) {
        if (containerWidth < 600.dp) {
        
  }
55. Explain instanceKeeper in Decompose.

Sometimes it might be necessary to preserve state or data in a component when it gets destroyed. This commonly used in Android when configuration changes occur. The ComponentContext interface extends the InstanceKeeperOwner interface, which provides the InstanceKeeper - a multiplatform abstraction for instances retaining.

56. Explain ComponentContext in Decompose.

It is an interface that provides access to various tools, like lifecycle, state preservation, instance retaining (aka Android ViewModel), back button handling, etc. Each component has its own ComponentContext provided by Decompose.

If your component requires ComponentContext, just pass it via constructor. You can also use the delegation pattern to add ComponentContext to this scope.

57. Explain matchParentSize modifier properties.

Box(
            modifier = Modifier
                .width(350.dp)
                .height(400.dp)
                .clip(RoundedCornerShape(20.dp))
                .align(Alignment.Center)
                .background(color = Color.Black)
        ) {
            Column(
                horizontalAlignment= Alignment.CenterHorizontally,
                verticalArrangement = Arrangement.SpaceEvenly,

                modifier = Modifier.matchParentSize()
            ) {
            
            }
57. How to convert Compose Multiplatform iOS code to Kotlin native?

When you use Compose Multiplatform on iOS, the Kotlin code for your UI is compiled to native code using Kotlin/Native. This native code is then used to create a UIKit-based UI that runs on the iOS platform. Compose Multiplatform for iOS provides the Kotlin APIs for building Compose UIs on iOS. This library bridges the gap between the Kotlin/Native code and the UIKit framework.

Compose Multiplatform introduces a prototype for bidirectional interaction at the UI level. With the help of UIKitView, you can seamlessly integrate intricate platform-specific widgets — such as maps, web views, media players, and camera feeds — into your shared user interface. Conversely, employing ComposeUIViewController allows you to nest Compose Multiplatform screens within SwiftUI applications, facilitating a gradual integration of Compose Multiplatform into your iOS apps.

58. Floating point value display after point two value.

Text(text = "%.2f Km".format(distance))
59. Explain the condition modifier.

When building an application, be it small or large, there will often be a need to apply conditions to modifiers. For instance, you may want to change the background color of a button based on whether the input is valid or not.

modifier = Modifier.then(
            if (isValidInput) {
                Modifier.background(Color.Black)
            } else {
                Modifier.background(Color.Gray)
            }
        )
60. What is BOM?

The Bill of Materials (BOM) will allow you to manage versions of all your Compose libraries by specifying only the BOM’s version. The BOM has links to the stable versions of the different Compose libraries, in such a way that all the libraries that you’re using in your app are automatically updated to their new versions.

61. Why use BOM?

BOM helps you to automatically use the latest versions of Compose libraries.
Various Jetpack Compose libraries are moved to independent versioning, so it’s easy to use all of the latest stable versions at the same time.
Using the BOM ensures that the versions of any Compose libraries in your app are compatible.
BOM works with version catalogs too.
62. How does rememberCoroutineScope work in handling side effects?

A composable function that gives reference to a composition-aware coroutine scope.

63. How does SideEffect enable communication with non-Compose code?

SideEffect is used to publish Compose state to non-Compose code. It is invoked on every successful recomposition and can be used to communicate state changes to external libraries or systems that are not managed by Jetpack Compose.

64. What is produceState and how does it convert non-Compose state into Compose state?

produceState is used to convert non-Compose state, such as Flow, LiveData, or RxJava, into Compose state. It launches a coroutine scoped to the composition and updates the State object based on the emitted values from the non-Compose state source.

65. Why use States in Jetpack Compose?

States are a powerful feature of Jetpack Compose that allow developers to create dynamic and interactive UIs with minimal code. By using states, we can update the UI in response to user interactions or changes in data, without having to manage complex UI components manually.

In Compose, state can be managed using the remember function, which creates a variable that survives recomposition, and the mutableStateOf() function, which creates a mutable state object that can be updated. The state can be accessed using the value property or using a property delegate such as var state by remember { mutableStateOf() }.

66. Explain Saveable State?

rememberSaveable { mutableStateOf(0) } comes into play when you need to handle configuration changes, like screen rotations. It keeps the state even if the composable is recomposed due to configuration changes.

rememberSaveable{}, a composable function to restore your UI state after an activity or process is recreated (for example it happens when the screen is rotated in the Android application). We can manage a simple state of view within a compose function itself.

67. Write a custom compose search bar.

@Composable
fun SearchAppBar(
    text: String,
    onTextChange: (String) -> Unit,
    onCloseClicked: () -> Unit,
) {

    val focusRequester = remember { FocusRequester() }

    LaunchedEffect(Unit) {
        focusRequester.requestFocus()
    }

    Surface(
        modifier = Modifier.statusBarsPadding().fillMaxWidth().height(64.dp),
    ) {

        OutlinedTextField(
            value = text,
            onValueChange = { onTextChange(it) },
            leadingIcon = {
                Icon(imageVector = Icons.Default.Search, contentDescription = null)
            },
            trailingIcon = {
                IconButton(onClick = {
                    if (text.isNotEmpty()) {
                        onTextChange("")
                    } else {
                        onCloseClicked()
                    }
                }) {
                    Icon(
                        imageVector = Icons.Default.Close, contentDescription = "Close Icon"
                    )
                }
            },
            placeholder = {
                Text(text = SharedRes.string.search)
            },
            shape = RoundedCornerShape(percent = 30),
            modifier = Modifier.fillMaxWidth().padding(horizontal = 16.dp, vertical = 4.dp)
                .focusRequester(focusRequester = focusRequester)
        )
    }
}
68. Explain the concept of declarative UI in Jetpack Compose.

Declarative UI means describing the UI based on the app’s current state. In Compose, you declare how the UI should look and behave, and the framework automatically updates the UI when the underlying state changes. This is in contrast to imperative UI, where developers specify a sequence of actions to achieve a particular UI state.

In Jetpack Compose, UI components are represented as functions. These functions take the current state of the application as input and return a description of the UI based on that state. The UI is re-evaluated whenever the state changes.

@Composable
fun Greeting(name: String) {
    Text("Hello, $name!")
}
Declarative UI code tends to be more concise and readable compared to imperative UI code. Developers describe what the UI should look like in a specific state, making it easier to understand and maintain.

Jetpack Compose automatically re-evaluates the relevant composable functions when the underlying state changes and updates the UI to reflect the new state.

69. Explain the role of the @Composable annotation in Jetpack Compose.

The @Composable annotation is used to mark functions that define composable UI components. Composable functions are responsible for describing the UI based on the current state. When the state changes, Compose automatically recomposes the UI to reflect the updated state.

70. Type of effect — handlers?

Any Composable enters the composition when attached to the UI tree, and finally leaves the composition when detached from it. Between both events, effects might run. Some effects can outlive this cycle, so you can span an effect across recompositions

I thought we could divide effects in two categories for clarity:

Suspended effect handler: This effect-handler is for suspending functions: LaunchEffect, rememberCoroutineScope, Load data from network to feed some UI state.
Non-suspended effect handler: E.g: Run a side effect to initialize a callback when the Composable enters the composition, dispose it when it leaves. For example: DisposableEffect, SideEffect
71. Explain the Side effect of Composable function.

SideEffect can be defined anywhere inside a Composable function, however, a SideEffect function cannot make any changes to the UI. In other words, a SideEffect only runs specific non-interactive code and does not make any changes to the UI.
SideEffect is a function used in Jetpack Compose’s declarative structure to perform non-interactive tasks. It does not make any changes to the UI but prevents performance issues and makes the application run faster.
 SideEffect {
        //Log, println 
    }
72. Why we write any code outside the scope of any composable function?

It is because Due to composables’ lifecycle and properties such as unpredictable recompositions, executing recompositions of composables.

73. What is the difference between staticCompositionLocalOf and compositionLocalOf?

CompositionLocal starts with the creation of a ProvidableCompositionLocal instance which can be obtained via a call to either the compositionLocalOf() or staticCompositionLocalOf() function. In each case the function accepts a lambda defining a default value to be assigned to the state in the absence of a specific assignment
CompositionLocal is a Jetpack Compose API which allow you to access data from any composable function without passing them via the function’s parameters.
CompositionLocal, you can create objects that are available throughout the UI tree or just a subset of it. You don’t need to pass down the data along all composables, so your data is implicitly available for the composables to use.
Types of

Static CompositionLocal: This CompositionLocal is useful for storing state variable data that is rarely changing. Any change to it will affect the entire tree underneath to be recomposed.
Dynamic CompositionLocal: This CompositionLocal is for storing a state variable data that can change. Any change to it will only cause recomposition on the respective composable function only.
74. How to hide the keyboard in Jetpack Compose?

val keyboardController = LocalSoftwareKeyboardController.current

keyboardController?. hide()
75. Activity 1.9.0-alpha01

ComponentActivity now implements OnUserLeaveHintProvider to allow components to callbacks for onUserLeaveHint events

ComponentActivity has been rewritten in Kotlin.
ActivityResultCaller has been rewritten in Kotlin.
ActivityResultLauncher has been rewritten in Kotlin. As part of that conversion, the getContract method is now an abstract Kotlin property. This is a binary compatible change, but source breaking if your implementation of ActivityResultLauncher is written in Kotlin.
PickVisualMediaRequest now has the same minimum API level of 19 as the PickVisualMedia Activity Result contract.
76. Explain onTaskRemoved()in Service.

The onTaskRemoved method is triggered when the Android system decides to remove your app from memory.
This can happen due to various reasons, such as the user swiping the app away from the background, a system process reclaiming memory, or the app being backgrounded for an extended period.
By implementing the onTaskRemoved method in a service, you can effectively detect when the user has closed your app, even if they don't explicitly terminate it.
77. Types of Injecting Dependencies Koin in Android?

Constructor Injection
By declaring a dependency in your class constructor, you can inject it effortlessly. However, in this scenario, it is essential to inform Koin about the instantiation of your class by defining it within the dependency module.
Property Injection
To inject dependencies into your classes, you can use the ‘by inject()’ delegate provided by Koin. You simply declare a property with the desired type and use the ‘by inject()’ delegate to initialize it.
private val userService: UserService by inject()
userService will be automatically initialized with the instance provided by Koin.

78. What is Koin Framework?

Koin is a lightweight dependency injection framework for Kotlin that simplifies the process of managing dependencies in your KMM project. It enables you to decouple your code and makes it easier to test and maintain.
79. Defining Koin Dependencies.

Koin allows you to perform dependency injection not only within the shared module but also within the Android project itself.
This means you can also utilize the Koin framework natively within your Android project. Therefore, you will define the dependencies for the shared module within the shared module itself, while the dependencies specific to the Android app will be defined within the Android module.
In Koin, dependencies are defined using modules. A module contains the definitions of dependencies and how to create instances of them. You can define a module using the module function and provide a set of dependencies using the single or factory functions.
80. What is Jetpack Datastore?

Jetpack Datastore is a data storage solution provided by Android Jetpack libraries. It offers a modern, efficient, and easy-to-use API for persisting key-value pairs or complex objects.
Datastore supports both synchronous and asynchronous operations, making it suitable for a variety of use cases.
It also provides type safety and automatic serialization/deserialization, reducing the chances of runtime errors.
81. Types of Jetpack Datastore?

The Jetpack Datastore offers two primary types of stores, namely Preferences and Proto DataStore. These stores can be directly utilized from the shared module.

Preferences DataStore is a key-value store that allows you to store simple data types, such as strings, integers, booleans, and floats. It is similar to SharedPreferences but provides a more modern and type-safe API.
Proto DataStore is a store that allows you to store custom data types defined using Protocol Buffers. Protocol Buffers provide a flexible and efficient way to define data structures that can be serialized and deserialized automatically by Datastore.
82. Explain Hilt Component.

Hilt Component: A blueprint for managing dependencies in your app.

Modules:Instruction manuals for creating specific dependencies.
AndroidEntryPoint: A label for parts of your app where you want to use Hilt.
ViewModelInject: Helps inject dependencies into ViewModels easily.
HiltViewModel: Makes it simpler to create and use ViewModels with Hilt.
HiltAndroidApp: Marks the starting point of your app for Hilt setup.
Scoped Annotations: Annotations that control how long dependencies live in your app.
AssistedInject: A way to create things with runtime data more easily.
83. Explain AnimatedContent in Jetpack Compose.

AnimatedContent for more custom transitions between different types of content.

AnimatedContent(
   targetState = state,
   transitionSpec = {
       fadeIn() + slideInVertically(animationSpec = tween(400),
           initialOffsetY = { fullHeight -> fullHeight }) with
       fadeOut(animationSpec = tween(200))
   }
) { targetState ->
   when (targetState) {
  
  }
}

//Sliding question change
AnimatedContent(
    targetState = questionState,
    transitionSpec = {
        // Going forwards in the survey: Set the initial offset to start
        // at the size of the content so it slides in from right to left, and
        // slides out from the left of the screen to -fullWidth
        slideInHorizontally(
            animationSpec = tween(CONTENT_ANIMATION_DURATION),
            initialOffsetX = { fullWidth -> fullWidth }
        ) togetherWith
            slideOutHorizontally(
                animationSpec = tween(CONTENT_ANIMATION_DURATION),
                targetOffsetX = { fullWidth -> -fullWidth }
            )
    }
) { targetState ->
    Question(
        
    )
84. Why use paddingValues in Jetpack Compose?

PaddingValues means giving padding from start, end, top & bottoms.

85. Explain Jetpack Compose Architecture.

Compose works with the combination of seven libraries within android.package.

compose.compiler: Transform the functions written with @Composable annotation.
2. compose.foundation: Implements building blocks for compose(e.g.: Box, Column,Row)
3. compose.animation: Provides tools for building animations in Jetpack Compose.
4. compose.material: Provides a set of Material Design components.
5. compose.material3: Provides set of Material3 components.
6. compose.ui: Fundamental components of ComposeUI that are needed to interact with the device
7. compose.runtime: Contains the core runtime that helps the compiler to generate code

86. How to access coroutines inside the Jetpack Compose?

To launch a coroutine from a Composable function in Compose, you can use the LaunchedEffect composable. LaunchedEffect is a Composable function that takes a key and a lambda as parameters. The lambda is executed asynchronously in a coroutine scope when the key changes.

87. Explain Stability in Compose.

Tools > Android > Layout Inspector show recompose

@Immutable annotation, indicates that all public fields are immutable since they are created, and can be applied to a class. Since the value does not change after creation, the first rule of stability “When a value has changed, it should be notified to the composable.” is ignored. This is a stronger promise than Kotlin’s val keyword. In the case of val, the instance is the same but the inside value can change.

This is a promise to the compose compiler that once the object is constructed, the properties inside it won’t change at runtime.

@Immutable
class ImmutableListWrapper(val values: List<String>)
@Stable, These hold data that is mutable, but notify Composition upon mutating. This renders them stable since Composition is always informed of any changes to state.

The kotlinx.collections.immutable library, which includes those two as well as other PersistentCollection and ImmutableCollection interfaces

@Stable: Use this for classes where the properties might change but in a predictable way. The Compose compiler knows that this object might change, but when it changes, Compose runtime will be notified.

@Immutable: Apply this to classes where once you set the properties, they never change. Compose uses this info to speed up screen updates, knowing these parts are constant.

@Immutable
data class DataList{
    val list: List<String>
}

class ViewModel {
    var datalist: DataList = DataList(listOf())
    fun removeLastItem() {
        val newList = datalist.list.toMutableList().apply {
                removeLast()
            }
        datalist = datalist.copy(
            list = newList
        )
    }
}

fun removeLastItem() {
        datalist.list.removeLast() // <=== you violate your promise of @Immutable!
    }
88. Draw the layout.


Row(
       verticalAlignment = Alignment.CenterVertically
       ) {
             CustomImage(image = images.random())
             CustomImage(image = images.random(), modifier = Modifier.offset(x = (-10).dp))
             CustomImage(image = images.random(), modifier = Modifier.offset(x = (-20).dp) )
             CustomImage(image = images.random(), modifier = Modifier.offset(x = (-30).dp) )
             CustomImage(image = images.random(), modifier = Modifier.offset(x = (-40).dp) )
             CustomImage(image = images.random(), modifier = Modifier.offset(x = (-50).dp) )
         }

@Composable
fun CustomImage(@DrawableRes image: Int, modifier: Modifier = Modifier) {
    Image(
        painter = painterResource(id = image),
        contentDescription = null,
        modifier = modifier.size(DpDimensions.Dp24)
            .clip(CircleShape)
            .border(border = BorderStroke(1.dp, color = Color.White), CircleShape),
        contentScale = ContentScale.Crop,
    )
}
89. Draw the layout bottom box color transparent.

Surface(
        shape = RoundedCornerShape(DpDimensions.Dp20),
        modifier = modifier
            .width(200.dp)
            .height(height),
        onClick = { onClick(collection) }
    ) {
        Box(
            modifier = Modifier
                .fillMaxSize()
                .paint(
                    painter = painterResource(id = collection.image),
                    contentScale = ContentScale.Crop
                )
                .background(
                    brush = Brush.verticalGradient(
                        listOf(
                            Color.Transparent,
                            Color.Transparent,
                            Color.Black
                        )
                    )
                )
                .clip(RoundedCornerShape(DpDimensions.Small)),
            contentAlignment = Alignment.BottomStart
        ) {
            Column(
                modifier = Modifier.padding(DpDimensions.Normal)
            ) {
                Text(
                    text = collection.title,
                    style = MaterialTheme.typography.titleMedium,
                    color = Color.White
                )
            }
        }
    }
90. IST Time to GMT Time in Kotlin.

     val sdfIST = SimpleDateFormat("yyyy-MM-dd'T'HH:mm", Locale.getDefault())
     sdfIST.timeZone = TimeZone.getTimeZone("IST") // Set timezone to IST

     val parsedTimeIST: Date = sdfIST.parse("Enter Time")!!

     val sdfGMT = SimpleDateFormat("yyyy-MM-dd'T'HH:mm", Locale.getDefault())
     sdfGMT.timeZone = TimeZone.getTimeZone("GMT") // Set timezone to GMT

     val timeGMT: String = sdfGMT.format(parsedTimeIST)
     val parsedTimeGMT: Date = sdfGMT.parse(timeGMT)!!
91. Why Side-effects?

The purpose of side effects in Jetpack Compose is to allow for the execution of non-UI related operations that change the state of the app outside of a Composable function in a controlled and predictable manner.
Side effects, such as updating a database or making a network call, should be kept separate from the UI rendering logic to improve the performance and maintainability of the code.
Jetpack Compose provides several Composable functions, such as SideEffect, LaunchedEffect, and DisposableEffect, that enable developers to manage side effects effectively, by decoupling them from the UI rendering logic and executing them in a separate coroutine scope.
92. Cold Flow vs Hot Flow

Cold Flow is a type of Kotlin Flow that emits data only when there is a collector. It doesn't store any data and starts emitting values only when a collector subscribes to it. Each collector receives all the values from the beginning of the Flow independently, as if they have their individual flow.

Hot Flow is a type of Kotlin Flow that emits data continuously, even when there is no collector. It can have multiple collectors, and each collector receives values from where they started collecting. It's like a 1-to-N mapping, where one Flow serves multiple collectors, and each collector receives data based on their individual subscription time.

93. How to handle checkbox in different ways?

//1 Approach
var isChecked by remember {
            mutableStateOf(false)
        }
        Box (modifier = modifier.padding(50.dp)) {
            Checkbox(
                checked = isChecked,
                onCheckedChange = {
                    isChecked = it
                }
            )
        }

//2 Approach
val (isChecked, toggleState) =
            remember { mutableStateOf( false) }

        Box (modifier = modifier.padding(50.dp)) {
            Checkbox(
                checked = isChecked,
                onCheckedChange = toggleState
            )
        }
94. WheelTimePicker in Jetpack Compose

@Composable
fun CustomTimePicker(
    startTime: LocalTime,
    minTime: LocalTime = LocalTime.MIN,
    maxTime: LocalTime = LocalTime.MAX,
    onTimeChange: (LocalTime) -> Unit,
) {
    WheelTimePicker(
        startTime = startTime,
        minTime = minTime,
        maxTime = maxTime,
        timeFormat = TimeFormat.HOUR_24,
        size = DpSize(150.dp, 250.dp),
        rowCount = 5,
        textStyle = MaterialTheme.typography.titleMedium,
        textColor = CustomTheme.colors.text,
        selectorProperties = WheelPickerDefaults.selectorProperties(
            enabled = true,
            shape = RoundedCornerShape(15.dp),
            color = CustomTheme.colors.secondaryBackground,
            border = BorderStroke(1.dp, CustomTheme.colors.active)
        )
    ) { snappedDateTime -> onTimeChange(snappedDateTime) }
}
95. Explain animateContentSize property.

This modifier animates its own size when its child modifier (or the child
composable if it is already at the tail of the chain) changes size.
This allows the parent modifier to observe a smooth size change,
resulting in an overall continuous visual change.

 .animateContentSize(
                    animationSpec = tween(
                        durationMillis = 150,
                        easing = LinearOutSlowInEasing
                    )
                )

.animateContentSize(
              animationSpec = tween(durationMillis = 300,
                   easing = LinearOutSlowInEasing))


var isLoading by remember { mutableStateOf(false) }
val text = if (isLoading) "Delete" else "Loading"

//Text Animation
Button(onClick = { isLoading = !isLoading },
    modifier = Modifier
        .animateContentSize(
              animationSpec = tween(durationMillis = 300,
                   easing = LinearOutSlowInEasing))
) {
    Text(text = text,textAlign = TextAlign.Center)
}

//Dialog Height Animation 
Card(
                modifier = modifier
                    .animateContentSize(
                        animationSpec = spring(
                            dampingRatio = Spring.DampingRatioMediumBouncy,
                            stiffness = Spring.StiffnessLow
                        )
                    )
                    .align(Alignment.Center),
                colors = CardDefaults.cardColors(
                    containerColor = MaterialTheme.colorScheme.onPrimary
                ),
                shape = RoundedCornerShape(10.dp)
            ) { }
96. animateContentSize vs AnimatedContent

AnimatedContent is a composable that allows you to transition between different composables with a smoother and more custom transition effect.

animateContentSize is a property used to change the text, and smooth animation.

97. Which is the property name dismiss dialog on click outside?

@Composable
fun ActionDialog(
    onGoBack: () -> Unit,
) {
    Dialog(onGoBack, DialogProperties(true, dismissOnClickOutside = true)) {
        Column() { }
}
98. Access ViewModel in Kotlin multiplatform using viewModelFactory.

val sharedViewModel =
    getViewModel(key = Unit, viewModelFactory { SharedViewModel(noteDataSource) })
99. How to Initialize CommonMain Context and CoroutineScope in Kotlin Multiplatform.

//CommonMain 
expect class ImageUtil {
    @Composable
    fun initUtil()
}

//Android 
actual class ImageUtil{

    private lateinit var getContent: ActivityResultLauncher<String>
    private lateinit var mContext: Context
    private lateinit var ioScope:CoroutineScope

    @Composable
    actual fun initUtil(){
        val context = LocalContext.current
        ioScope = rememberCoroutineScope()
        mContext = context
    }
}

//access
ImageUtil.initUtil()
100. How to context initialize App level in Kotlin Multiplatform.

//AndroidApp
class MainActivity : ComponentActivity() {
    private val platformUtil = PlatformUtil(this)

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            PreComposeApp {
                NoteTheme {
                    Surface(
                        modifier = Modifier.fillMaxSize(),
                        color = MaterialTheme.colorScheme.background
                    ) {

                        MainView(
                            platformUtil
                        )
                    }
                }
            }
        }
    }
}

//AndroidMain
actual class PlatformUtil(private val context: Context) {
}

//shared
@Composable
fun MainView(platformUtil: PlatformUtil) {

}

expect class PlatformUtil {

}
101. ISO 8601 standards converts to UTC.

import java.time.Instant
import java.time.ZoneOffset
import java.time.format.DateTimeFormatter

fun main() {
    val formatter = DateTimeFormatter.ofPattern ("yyyy-MM-dd'T'HH:mm:ss[.SSS][.SS][.S]X")
    val dateString = "2023-10-11T06:33:52Z"
    val instant = Instant. from(formatter.parse(dateString))
    val hour = instant.atOffset(ZoneOffset.UTC).hour
    val minutes = instant.atOffset(ZoneOffset.UTC).minute
    val seconds = instant.atOffset(ZoneOffset.UTC).second
    println("Hour: $hour, Minutes: $minutes, Seconds: $seconds")
}
102. What is an Annotated String?

Annotated strings offer a versatile toolset for transforming plain text into visually engaging and context-rich content.

103. Types of Testing in Jetpack Compose.

Isolated UI Test → tests a single UI component in isolation ( eg: stateless or reusable component for EmailField or PhoneNumberField).
Integrated UI Test → tests how UI component interacts with other classes (such as ViewModel)
End-to-End Test → tests complete user interaction flows, typically across multiple screens
104. Explain LazyColumn optimization.

compress: Image compress
key: LazyColumn item key set, easy to identifier, key always unique. For example UUID.randomUUID().toString() or Model class already unique key property set.
  key = {
        it.id
  }
Recomposed: model class annotation set Immutable.
105. Once all elements are measured in size during the Layout phase, the tree is walked again and all placement instructions are executed in the — step.

Placement

106. When evaluating your Compose app performance, it is very important to make sure you are running in release mode with R8 optimization enabled.

true

107. On phones, an on-screen element that a user interacts with should have a width and height of at least

48 dp

108. Use — — — to group together actions that relate to the same list item.

custom actions

109. In Compose, you can test a component in isolation.

true

110. Store objects in the composition by using the — — — composable function, which can be used to store both mutable and immutable objects.

remember

111. The NavController component does which of the following:

Keeps track of back stack composable entries
Enables back stack manipulation
Navigates between destination states
112. State is always mutated inside the scope of a composable function.

false: State is always mutated outside the scope of a composable function.

113. When state changes, a recomposition is triggered to:

Display the new data on the screen
Recompose just those composable functions that need to change
114. In Compose, there is no way to update the Ul after it’s been drawn without changing state.

true: The Ul is immutable

115. Which of the following is true about unidirectional data flow (UDF):

There is only one source of truth for the state of a composable.
It’s less likely that you’ll create bugs due to inconsistent states
116. Compose has a special state-tracking system in place that schedules recompositions for any composables that read a particular state.

true

117. Compose uses a single pass layout system.

No. Although Compose aims to measure and layout in a single pass, it can’t always succeed in that. Sometimes Compose needs to know something about the child sizes before finalizing the constraints-for example, a pop-up menu where each menu item is a different size.

118. To adjust an animation’s fraction, which lets the animating value speed up and slow down, use — — —

Easing

119. Rendering a scrollable set of items as they become visible on the screen, rather than all at once, is the main concept behind:

Lazy layouts

120. — — — executes your composable functions, which can emit Ul and create a Ul tree.

Composition

121. How Compose transforms the state into UI.


Composition executes your composable functions which can emit UI, creating a UI tree. For example, executing this SearchResult composable yields a tree like this.


In the layout stage, this tree is worked and each piece of UI is measured and placed on the screen. That is each node determines their width and height and x, y coordinates. Each element is also located within its parent, specified as an (x, y) position, and a size, specified as a width and a height.
In the drawing stage, the UI tree is worked again, and all elements are rendered.

122. Explain Layout stage.


When we move to the layout phase, we use this UI tree as input. The collection of layout nodes contain all the information needed to eventually decide on each node’s size and location in 2D space.

During the Layout phase, the tree is traversed using the following 3 step algorithm:

Measure children: A node measures its children, if any.
Decide own size: Based on those measurements, a node decides on its own size.
Place children: Each child node is placed relative to a node’s own position.
The layout phase consists of two steps: measurement and placement.
The measurement step runs the measure lambda passed to the Layout composable, the MeasureScope.measure method of the LayoutModifier interface, and so on.
The placement step runs the placement block of the layout function, the lambda block of Modifier.offset { … }, and so on.
State reads during each of these steps affect the layout and potentially the drawing phase. When the state value changes, Compose UI schedules the layout phase. It also runs the drawing phase if size or position has changed.
To be more precise, the measurement step and the placement step have separate restart scopes, meaning that state reads in the placement step don’t re-invoke the measurement step before that. However, these two steps are often intertwined, so a state read in the placement step can affect other restart scopes that belong to the measurement step.


At the end of the phase, each layout node will have an assigned width and height, and an x, y coordinate where it should be drawn.

So for our composable, this would work as follows:

The Row measures its children.
First, the Image is measured. It doesn’t have any children so it decides its own size and reports it back to the Row.
Second, the Column is measured. It needs to measure its own children first.
The first Text is measured. It doesn’t have any children so it decides its own size and reports it back to the Column.
The second Text is measured. It doesn’t have any children so it decides its own size and reports it back to the Column.
The Column uses the child measurements to decide its own size. It uses the maximum child width and the sum of the height of its children.
The Column places its children relative to itself, putting them beneath each other vertically.
The Row uses the child measurements to decide its own size. It uses the maximum child height and the sum of the widths of its children. It then places its children.
One key take-away here is that we visited each node only once. With a single pass through the UI tree we were able to measure and place all the nodes. This is great for performance. When the number of nodes in the tree increases, the time spent traversing it increases in a linear fashion. In contrast, if we were to visit each node multiple times, the traversal time would increase exponentially.

123. How to find portrait and Landscape mode in Jetpack Compose?

 val windowSize= calculateWindowSizeClass(this)

when (windowSize.widthSizeClass){
        WindowWidthSizeClass.Compact-> MyRelaxAppPortrait()
        WindowWidthSizeClass.Expanded-> MyRelaxAppLandscape()
    }
124. Write a program search text and change the color with the bottom line.

val searchText = "Compose";

        Text(
            text = buildAnnotatedString {
                val startIndex = "Jetpack Compose".indexOf(searchText, ignoreCase = true)
                if (startIndex != -1) {
                    append("Jetpack Compose".substring(0, startIndex))
                    withStyle(
                        style = SpanStyle(
                            fontWeight = FontWeight.Bold,
                            color = Color.Magenta,
                            textDecoration = TextDecoration.Underline
                        )
                    ) {
                        append("Jetpack Compose".substring(startIndex, startIndex + searchText.length))
                    }
                    append("Jetpack Compose".substring(startIndex + searchText.length))
                } else {
                    append("Jetpack Compose")
                }
            },
            modifier = Modifier.padding(top = 8.dp)
        )
125. LazyItemScope compose

@OptIn(ExperimentalFoundationApi::class)

@Composable
fun LazyItemScope.CardPoster(
    modifier: Modifier = Modifier,
    data: Result,
    loading: Boolean = false,
    onClick: (Result) -> Unit
) = com.compose.food.ui.components.CardPoster(
    modifier.animateItemPlacement(
        animationSpec = tween(durationMillis = 1000)
    ), data, loading, onClick
)

@Composable
fun CardPoster(
    modifier: Modifier = Modifier,
    data: Result,
    loading: Boolean = false,
    onClick: (Result) -> Unit
) {

}
126. Back navigation visible icon.

val isBackStackEmpty = remember { mutableStateOf(false) }

    navHostController?.addOnDestinationChangedListener { _, _, _ ->
        isBackStackEmpty.value = navHostController.previousBackStackEntry == null
    }

navigationIcon = {
            if (!isBackStackEmpty.value) {
                IconButton(
                    onClick = {
                        if (onBackClick == null)
                            navHostController?.navigateUp()
                        else
                            onBackClick.invoke()
                    }
                ) {
                    Icon(
                        imageVector = if (LocalLayoutDirection.current == LayoutDirection.Ltr) Icons.Filled.ArrowBack else Icons.Filled.ArrowForward,
                        contentDescription = "Navigation Back Arrow"
                    )
                }
            }
        },
128. How to return clickable in Jetpack Compose?

var isLoading by remember { mutableStateOf(false) }

modifier.clip(MaterialTheme.shapes.extraLarge)
            .background(
                if (isAddedToMyList || isLoading) Color.Transparent else MaterialTheme
                    .colorScheme.primary
            )
            .clickable {
                if (isLoading) return@clickable
                //if (state().amount.isEmpty()) return@TextButton
                isLoading = true
            }
129. Explain TextOverFlow property.

The `𝗼𝘃𝗲𝗿𝗳𝗹𝗼𝘄: 𝗧𝗲𝘅𝘁𝗢𝘃𝗲𝗿𝗳𝗹𝗼𝘄` which is a part of 𝐓𝐞𝐱𝐭 composable is a property that allows us to change the default behavior for visual overflow. There are three options available in `𝗼𝘃𝗲𝗿𝗳𝗹𝗼𝘄` parameter.
𝑪𝒍𝒊𝒑 — It clip’s the overflowing text to fix its container.
𝑬𝒍𝒍𝒊𝒑𝒔𝒊𝒔 — It uses an ellipsis to indicate that the text has overflowed.
𝑽𝒊𝒔𝒊𝒃𝒍𝒆 — When overflow is visible, text may be rendered outside the bounds of the composable displaying the text.
130. Explain KMP folder structure.

androidLibMain: Android platform-specific KMP logic
commonMain: KMP business logic that does not require any platform-specific code
iosMain: iOS platform-specific KMP logic that has the ability to interact with Apple APIs (ie: UIKit, GCD, etc…)
main: Contains a AndroidManifest.xml file, which defines / as an Android Library. In many ways, it’s like an Xcode.plist.
131. Explain Skippable and Restartable in Jetpack Compose.

Skippable: If the compiler marks a composable as skippable, Compose can skip it during recomposition if all its arguments are equal with their previous values.
Restartable: A composable that is restartable serves as a “scope” where recomposition can start. In other words, the function can be a point of entry for where Compose can start re-executing code for recomposition after state changes.
132. Performance increase in Jetpack compose

var username by remember { mutableStateOf("") }

val isValidPassword by remember {
  derivedStateOf { isUsernameValid(username) }
}

OutlinedTextField(value = username, onValueChange = {username = it} )

Button(onClick = {}, enabled = isValidPassword) {
  Text(text = "Submit")
}

//2 Sorting
@Composable
fun ContactList(messages: List<Message>, comparator: Comparator<Message>) {
    val sortedList = remember(messages, comparator){
      messages.sortedWith(comparator)
    }

    LazyColumn {
        items(sortedList) { message ->
            // ...
        }
    }
}

//3 invoked
@Composable
fun CartItem(onCartQtyUpdate: (cartQty: Int) -> Unit) {
  //Button click 
  onCartQtyUpdate.invoke(product.cartQty - 1)
}

//4 as String
val result: String? = someObject as? String

//5
lateinit var file: File

// To check before using the file
if (!::file.isInitialized) {
    file = File("file_path")
}

//6
val person = Person().apply {
    name = "John"
    age = 30
    city = "New York"
}

//7 null check
name?.let {
    // code block
}

//8
fun processUserData(user: User?) {
    user?.address?.let {
        // code block
    }
}
133. How to set TextField focus, hint color change in Jetpack Compose.

var onFocus by remember {
        mutableStateOf(false)
    }

//BasicTextField properties

//Focus 
modifier = Modifier
                  .fillMaxWidth(0.9f)
                  .onFocusChanged { onFocus = it.isFocused },

//FocusRequest
val focusRequester = remember { FocusRequester() }
modifier = Modifier
                    .focusRequester(focusRequester),

//Focus clear
val focusManager = LocalFocusManager.current
focusManager.clearFocus()

//Hint 
decorationBox = @Composable { innerTextField ->
                    innerTextField.invoke()
                    if (text.isBlank()) {
                        Text(text = "Username", color = Color.DarkGray, fontSize = textStyle.fontSize)
                    }
                }

//Password visibility
@Composable
fun CustomTextField(
    isPassword: Boolean = false
) {
    var textVisibility by remember {
        mutableStateOf(isPassword)
    }

    //Text visible    
    visualTransformation = if (textVisibility) PasswordVisualTransformation() else VisualTransformation.None,
}
134. Explain mutex?

Mutex provide exclusive access to a shared resource. A thread can acquire a mutex, perform its critical section, and release the mutex to allow other threads to access the resource.
When a thread attempts to acquire a mutex that is already locked, it is put to sleep until the mutex is released.
Mutex are suitable for protecting critical sections where sleeping is acceptable.
135. Fast UI develop

val items = (0..20).map { it.toString() }
//items.size

//Destructuring Assignment 
fun main() {
    data class Student(val name: String, val age: Int)
    val students: List<Student> = emptyList()

    students.forEach {
        val name = it.name
        val age = it.age
        println("Name: $name, Age: $age")
    }

    // Using destructuring assignment
    students.forEach { (name, age) ->
        println("Name: $name $age")
    }
}
136. buildAnnotatedString / annotatedString click in Jetpack Compose.

@Composable
fun ClickableTextComponent(value: String, onTextSelected: (String) -> Unit) {
    val initialText = " "
    val privacyPolicyText = ""
    val andText = ""
    val termsAndConditionsText = ""

    val annotatedString = buildAnnotatedString {
        append(initialText)
        withStyle(style = SpanStyle(color = MaterialTheme.colorScheme.primary)) {
            pushStringAnnotation(tag = privacyPolicyText, annotation = privacyPolicyText)
            append(privacyPolicyText)
        }
        append(andText)
        withStyle(style = SpanStyle(color = MaterialTheme.colorScheme.primary)) {
            pushStringAnnotation(tag = termsAndConditionsText, annotation = termsAndConditionsText)
            append(termsAndConditionsText)
        }
    }

    ClickableText(text = annotatedString,
        style = TextStyle(
            color = MaterialTheme.colorScheme.onBackground
        ), onClick = { offset ->

            annotatedString.getStringAnnotations(offset, offset)
                .firstOrNull()?.also { span ->
                    Log.d("ClickableTextComponent", "{${span.item}}")

                    if ((span.item == termsAndConditionsText) || (span.item == privacyPolicyText)) {
                        onTextSelected(span.item)
                    }
                }

        })
}
137. Add to Cart logic / Change Quantity in Kotlin.

data class CartScreenUIState(
    val isLoading: Boolean = true,
    val cartItems: MutableList<CartItem> = mutableListOf()
)

data class CartItem(
    val product: String,
    val quantity: Int,
    val id: String,
    val discount: Number?,
    val price: Number,
    val isFav: Boolean,
    val image: String
)

private val _uiState = MutableStateFlow(CartScreenUIState())
val uiState = _uiState.asStateFlow()

fun onChangeQuantity(productID: String, isIncrease: Boolean) {
        val item = uiState.value.cartItems.find { it.id == productID }
        
        //minium 1 quantity  
        item?.let {
            if (it.quantity == 1 && !isIncrease){
                return
            }
        }

        val newList = uiState.value.cartItems.map {
            it.copy(
                quantity = if (it.id == productID) {
                    if (isIncrease) {
                        it.quantity + 1
                    } else {
                        it.quantity - 1
                    }
                } else {
                    it.quantity
                }
            )
        }
        _uiState.update { it.copy(cartItems = newList.toMutableList()) }
    }

//Extension Function
fun List<CartItem>.calcItemsPrice(): Float {
    var itemsPrice = 0.0f
    this.forEach {
        itemsPrice += (it.discount ?: it.price).toFloat() * it.quantity
    }
    return itemsPrice
}

 Text(
         text = "${cartItems.calcItemsPrice()}$",
         color = MaterialTheme.colorScheme.onBackground,
         style = MaterialTheme.typography.bodySmall
     )
138. Explain Crossfade animation.

Crossfade animates the switch between two layouts with a crossfade effect. Let’s say we want to accomplish that between the non-expanded state only showing the Infinum logo composable and the expanded state that shows only the Infinum text composable. Switching between these composables needs to be done with a crossfade.

139. Grid layout using programming way in Jetpack Compose.

Grid(
                list = dates.items,
                cols = 7,
                rowModifier = Modifier
                    .fillMaxWidth()
                    .padding(bottom = 10.dp),
                colModifier = Modifier.padding(top = 20.dp)
            ) { item ->
                
            }

import androidx.compose.foundation.layout.Arrangement
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.runtime.Composable
import androidx.compose.ui.Modifier

@Composable
fun <T> Grid(
    cols: Int = 1,
    list: List<T>,
    rowModifier: Modifier = Modifier,
    colModifier: Modifier = Modifier,
    child: @Composable (dataModal: T) -> Unit
) {
    val rows = (list.size / cols) + (if (list.size % cols > 0) 1 else 0)

    Column(modifier = colModifier) {
        for (r in 0 until rows) {
            Row(modifier = rowModifier, horizontalArrangement = Arrangement.SpaceBetween) {
                for (cell in 0 until cols) {
                    val i = (r * cols) + cell
                    if (i < list.size) { child(list[i]) } else { break }
                }
            }
        }
    }
}
140. Explain NavController in Jetpack Compose.

The NavController is the central API for the Navigation component. It is stateful and keeps track of the back stack of composables that make up the screens in your app and the state of each screen.

You can create a NavController by using the rememberNavController() method in your composable:

val navController = rememberNavController()
You should create the NavController in the place in your composable hierarchy where all composables that need to reference it have access to it. This follows the principles of state hoisting and allows you to use the NavController and the state it provides via currentBackStackEntryAsState() to be used as the source of truth for updating composables outside of your screens.

141. State, Action, ViewModel in Jetpack Compose.

A state defines a set of data, that will be exposed by the ViewModel at one time
An Action is a function offered by the ViewModel, that let you create a new ViewModel state
ViewModel exposes actions and is the only component allowed to mutate its state
142. What is state in jetpack compose?

A state is an object it can hold our data. If data changes happen, it will update all its subscribed UI widgets. If you want to update the data at runtime in your widgets, you can use the state object.

The @ composable function(s) recomposes itself with the new data when the state/object value is updated and doesn’t affect or update the whole UI.

143. Why it doesn’t update the UI?

It just changes the value of the variable, but our UI needs to refresh.
For auto UI refresh, we need state objects. If we use a state object, our UI will get refreshed automatically when data gets changed. Let’s test the same code with the state object.
The composable are subscribed to a state, and when the value of the state is updated then all the composable who are subscribed to it also update the value.
//With State Object

@Composable
fun MutableStateClick() {
    var clickCount by mutableStateOf(0)//Not recommended
    Column {
        Button(onClick = { clickCount++ }) {
            Text(text = "" + clickCount + " times clicked")
        }
    }
}
144. How rememberUpdatedState works?

It wraps the parameter with remembered MutableState and updates its value on every recomposition. By doing this, the LaunchedEffect is referencing the same instance of the MutableState object instead of the text parameter. So even after recomposition, the LaunchedEffect still references the correct instance, which changes only its internal value.

146. Keeping track of changes

remember, rememberSaveable, rememberUpdatedState, rememberLauncherForActivityResult, rememberCoroutineScope

147. Composition and recompositon in Jetpack Compose.

Composition is the tree structure made up of composables used to describe the UI, accomplished by running composables. When we emit a user interface for the first time, that’s the initial composition. During that initial composition, Jetpack Compose tracks the composables that we called to describe the user interface.
Every time the app’s state changes, a recomposition takes place. It re-runs the composables to update the composition.
148. Get Context in a Jetpack Compose Noncomposable function.

val context = LocalContext.current
149. Explain semantics in Jetpack Compose.

Row(modifier = Modifier.semantics(mergeDescendants = true) {}) { }
Semantics, as the name implies, give meaning to a piece of UI. In this context, a “piece of UI” (or element) can mean anything from a single composable to a full screen.
Imagine you’re building an app, and it has a user interface (UI) with different elements like buttons, text, and images. We can think of this UI as a tree made up of these elements. This tree is called the Composition.
Now, next to this Composition tree, there’s another tree called the Semantics tree.
Properties

contentDescription functions like the old contentDescription, and I anticipate it will be the most common semantic property. Use this for elements like icons that need a description. Before Compose alpha 9, this was accessibilityLabel.
stateDescription describes your element’s state. For example, a radio button might set this to either “on” or “off”. Before Compose alpha 9, this was accessibilityValue.
testTag is a convenient way to tag individual elements so you can later access them in your tests. Since composables have no concept of IDs like we had in the View framework, this is the best way to identify specific pieces of UI in your tests.
150. semantics Vs clearAndSetSemantics in Jetpack Compose.

If an element has no children, you can use semantics to override the default behavior for that element. If an element has children, but you just want it all read as a single logical element use semantics but set the mergeDescendants parameter to true.
If you use mergeDescendants but want certain children to still read, you can also set mergeDescendants to true for those elements and they will not be merged into the parent.
Finally, if you want to have a parent element to have a fully custom contentDescription and don't want the children read, use clearAndSetSemantics.
Remember that even if you use mergeDescendants and a custom contentDescription in a semantics modifier that the system will read both the custom description and the merged descendent description.
151. Explain mutableStateOf in Jetpack Compose.

To create a state, we need to use mutableStateOf() function. In this, the state stores the value on execution, and if any composable is subscribed to it, the composable updates the value if there are any changes.

val mutableState = remember { mutableStateOf (default) }
var name by remember { mutableStateOf("") }
val (name, setName) = remember { mutableStateOf("") }
152. What if we want to share viewModel across a route and clear it as soon as that route ends?

Using viewModel in compose is very common to handle data and states. While sharing viewModels is a very common practice as well.
An example could multi-page form. This can be done via NavBackStackEntry, a step-by-step approach would:

Create our viewModel for the first destination of the route.
Use NavController.previousBackStackEntry to create the viewModel for the rest of the destinations of that route only. For reference see the second image.
One thing to note is while we are navigating within our route and if we pop the backstack, this could potentially break.
P.s For the sake of convenience, we are using extension functions to make the code reusable and readable.
153. How to check keyboard open or not in Jetpack Compose.

val isImeVisible by rememberImeState()

@Composable
fun rememberImeState(): State<Boolean> {
    val imeState = remember {
        mutableStateOf(false)
    }
    val view = LocalView.current
    DisposableEffect(view) {
        val listener = ViewTreeObserver.OnGlobalLayoutListener {
            val isKeyboardOpen = ViewCompat.getRootWindowInsets(view)
                ?.isVisible(WindowInsetsCompat.Type.ime()) ?: true
            imeState.value = isKeyboardOpen
        }

        view.viewTreeObserver.addOnGlobalLayoutListener(listener)
        onDispose {
            view.viewTreeObserver.removeOnGlobalLayoutListener(listener)
        }
    }
    return imeState
}
154. Different way argument pass.

//Multiple argument pass
@Composable
fun Category(onItemClickCategory : ((String,String) -> Unit)?) {
   //onItemClickCategory?.invoke("", "")
}

//Get argument
Category(onItemClickCategory = { route, arguments ->
                
})

//No argument pass 
@Composable
fun DetailWithMealId(backClick: ((Unit) -> Unit)?) {
    backClick?.invoke(Unit)
}

//Get argument
DetailWithMealId(backClick = {
      
})

//BoxScope argument
@Composable
fun GlassBox(
    content: @Composable BoxScope.() -> Unit
) { 
     Box(
        contentAlignment = Alignment.Center
    ) {
        content()
    }
}
155. Shimmer button effect in Jetpack Compose.


    val shimmer = rememberShimmer(
        shimmerBounds = ShimmerBounds.View, theme = defaultShimmerTheme.copy(
            blendMode = BlendMode.DstOut,
            shaderColors = listOf(
                MaterialTheme.colorScheme.surface.copy(alpha = 0f),
                MaterialTheme.colorScheme.surface.copy(alpha = 0.5f),
                MaterialTheme.colorScheme.surface.copy(alpha = 0f),
            ),
            shaderColorStops = listOf(0.0f, 0.5f, 1.0f)
        )
    )

Button(
            modifier = Modifier
                .fillMaxWidth()
                .shimmer(shimmer),
            contentPadding = PaddingValues(12.dp),
            onClick = {
                // Your onClick implementation
            }
        ) {
            Text(text = "Submit", style = TextStyle(fontSize = 16.sp, fontWeight = FontWeight.SemiBold))
        }
Android Basic
What is ADB?
ADB, or Android Debug Bridge, is a versatile command-line tool fostering seamless communication between your computer and Android devices. Embedded within the Android SDK, it’s a must-know for developers, testers, and power users, enabling a myriad of tasks on connected Android devices.

2. Resume and Pause

onResume() is called when the Activity becomes interactive to the user (this means when the Activity becomes the top of its respective Activity stack).
onPause() is called when the Activity becomes non-interactive to the user (the Activity is not at the top of its respective Activity stack).
3. Activities Back Stack

Launch Activity 1: onCreate() , onStart() , onResume() executed for activity 1.
Launch Activity 2: onPause() executed for activity 1. onCreate() , onStart() , onResume() executed for activity 2. onStop() executed for activity 1.
Launch Activity 3: onPause() executed for activity 2. onCreate() , onStart() , onResume() executed for activity 3. onStop() executed for activity 2.
Go back: onPause() , onStop() , onDestroy() executed for activity 3. onStart() , onResume() executed for activity 2.
Launch Activity 4: onPause() executed for activity 2. onCreate() , onStart() , onResume() executed for activity 4 onStop() executed for activity 2.
Go back: onPause() , onStop() , onDestroy() executed for activity 4. onStart() , onResume() executed for activity 2.
Go back: On Android 11 and older, activity 1 would be destroyed on back navigation. On Android 12 and newer, it goes to background and can be brought to foreground later.
4. What happens to an Activity when the Home button is pressed?

When the Home button is pressed, the current Activity is moved to the background, and the onPause() method is called, followed by onStop(). The Activity is not destroyed, but it can be killed by the system when memory is needed elsewhere.

5. What happens to an Activity when the Back button is pressed?

When the Back button is pressed, the current Activity is destroyed, and the previous Activity in the back stack is resumed. The onPause(), onStop(), and onDestroy() lifecycle methods are called in sequence.

6. How can you intercept the Back button press in an Activity?

You can intercept the Back button press by overriding the onBackPressed() method in your Activity. This allows you to perform specific actions before the Activity is finished.

7. What are the lifecycle methods that will get called when we are navigating from Activity A to Activity B?

Activity A goes on onPause and then onStop where as Activity B goes to onCreate onStart then onResume.

8. What are the lifecycle methods that will get a call when pressing the home button from Activity A and resuming from recent apps?

9. When I am in my activity get a phone call what will be the lifecycle of the activity and fragment?

10. What is the lifecycle of Activity when the phone is rotated?

11. Why is ADB a Game-Changer for Android Developers?

Install or uninstall Android applications effortlessly using ADB.
Gain access to logcat, unraveling system logs and application-specific details for effective debugging.
Seamlessly push files from your computer to Android devices or pull files from devices to your computer.
Harness ADB’s tools to profile Android app performance, collect vital data on CPU usage, and more.
Integrate ADB into your automated testing workflows, streamlining the testing process.
Unlock advanced capabilities by leveraging ADB for root access on Android devices, ideal for testing and development.
Kotlin

1. ISO Date convert dd-MM-yyyy in Kotlin.

fun convertDateFormat(isoDate: String): String {
    val inputFormat = SimpleDateFormat("yyyy-MM-dd'T'HH:mm:ss.SSS'Z'", Locale.getDefault())
    val outputFormat = SimpleDateFormat("dd-MM-yyyy", Locale.getDefault())

    try {
        val date = inputFormat.parse(isoDate)
        return outputFormat.format(date!!)
    } catch (e: Exception) {
        e.printStackTrace()
    }

    return ""
}
2. How are Single-Expression Functions Declared?

In Kotlin, a single-expression function is declared using the = sign after the function signature, followed by the expression representing the function's result.

fun add(a: Int, b: Int): Int = a + b
3. What is Android KTX?

Android KTX is a set of Kotlin extensions specifically crafted for Android development. It is an open-source library provided by the Android team to improve the Kotlin programming experience when working with Android APIs. The primary goal of Android KTX is to make Android code more concise and idiomatic in Kotlin.

implementation “androidx.core:core-ktx:1.7.0”
implementation “androidx.collection:collection-ktx:1.3.0”
implementation “androidx.fragment:fragment-ktx:1.6.2”
val textView: TextView = findViewById(R.id.textView)
textView.text = "Hello, Android!"

val value = PreferenceManager.getDefaultSharedPreferences(context).getString("key", "defaultValue")

//Fragement Transaction
supportFragmentManager.transaction {
 replace(R.id.fragmentContainer, MyFragment())
 addToBackStack(null)
}

4. Validation

//PASSWORD VALIDATION
// (?=.*[a-z]): Must contain at least one lowercase letter.
// (?=.*[A-Z]): Must contain at least one uppercase letter.
// (?=.*\d): Must contain at least one digit.
// .{8,}: Must be at least 8 characters long.
private val passwordRegex = Regex("^(?=.*[a-z])(?=.*[A-Z])(?=.*\\d).{8,}$")
5. String translate with argument.

//1 
<string name="resend_code_in_seconds">Resend code in %s s</string>
val text = stringResource(textId, timeStr)

//2
<string name="months_ago_with_number">%s months ago</string>
context.getString(R.string.months_ago_with_number, diffInMonths.toString())
6. Explain data class in Kotlin.

Data classes in Kotlin are defined using the data keyword and are intended to concisely store data.
Automatically Generated Functions: Data classes automatically generate equals(), hashCode(), toString(), and copy() methods, simplifying object comparisons, printing, and cloning.
Component Functions: Enable easy destructuring of these classes.
Immutability & Mutability: They primarily encourage immutable states but can use mutable properties for flexibility.
7. Explain JvmInline in Kotlin?

@JvmInline and value keywords, are designed for wrapping a single value efficiently but with no additional overhead at runtime. Inline classes are immutable.

8. Null Safety

Kotlin addresses the infamous null reference problem by incorporating null safety into its type system.
In Kotlin, variables are non-nullable by default, meaning a variable cannot hold a null value unless explicitly specified.
9. Kotlin 1.9.0

// Kotlin 1.8.0
launch {
    val result = asyncTask()
    // Handle the result
}

// Kotlin 1.9.0
coroutineScope {
    val result = asyncTask()
    // Handle the result
}

// Kotlin 1.8.0
if (value != null && value.isNotEmpty()) {
    // Do something
}

// Safe call operator ?. 
if (value?.isNotEmpty() == true) {
    // Do something
}

// Kotlin 1.8.0
val list = listOf(1, 2, 3, 4, 5)
val squaredList = list.map { it * it }

// Kotlin 1.9.0
val squaredList = listOf(1, 2, 3, 4, 5).mapSquared()
10. Kotlin 2.0.0 Beta-2

// Before Kotlin 2.0.0 Beta-2
val myString: String = "Hello, Kotlin!"

// With Kotlin 2.0.0 Beta-2
val myString = "Hello, Kotlin!"

// Improved coroutine scope
viewModelScope.launch {
    val result = asyncTask()
    // Handle the result
}

// Cancellation made easy
val job = launch {
    try {
        // Coroutine logic
    } finally {
        // Cleanup code
    }
    // More logic
    // ...
    // Coroutine gets cancelled, and cleanup code is executed
}
11. lateinit in kotlin

lateinit in Kotlin is useful in a scenario when we do not want to initialize a variable at the time of the declaration and want to initialize it at some later point in time, but we make sure that we initialize it before use.

private lateinit var mentor: Mentor

if(this::mentor.isInitialized) {
    // access mentor
} else {
    // do something else
}
12. Explain event bus.

In software development, an event bus is a messaging system that facilitates communication between different parts of an application.
It follows the publish-subscribe pattern, where components can subscribe to receive notifications about events published by other components.
This decoupling of components promotes loose coupling and centralized communication, making it easier to manage complex applications and enhance their maintainability.
13. What is Inline Function in Kotlin?

The higher-order functions or lambda expressions, all stored as an object so memory allocation, for both function objects and classes, and virtual calls might introduce runtime overhead. Sometimes we can eliminate the memory overhead by inlining the lambda expression.
In order to reduce the memory overhead of such higher-order functions or lambda expressions, we can use the inline keyword which ultimately requests the compiler to not allocate memory and simply copy the inline code of that function at the calling place.
14. Write a code old and new value check.

import kotlin.properties.Delegates

class Example {
    var name: String by Delegates.observable("<no name>") { _, old, new ->
        println("$old -> $new")
    }
}

fun main() {
    val ex = Example()
    ex.name = "Alice"
    ex.name = "Bob"
}
15. String, StringBuffer and StringBuilder.

String is immutable whereas StringBuffer and StringBuilder are mutable. Hence, if the content is fixed and wouldn’t change frequently then we should use String. String is more memory-efficient than other two classes if content doesn’t change frequently.
StringBuffer is mutable, synchronized,thread safe and less efficient.
StringBuilder is mutable but not synchronized by default, not thread safe and more effiecient.
16. Sequence

A Sequence in Kotlin is a lazily evaluated collection of elements. It allows for more efficient processing of large datasets by computing elements on-demand.

// Creating sequence
val sequence = sequenceOf(1, 2, 3, 4, 5)

// Transforming elements using map
val squaredSequence = sequence.map { it * it }

// Accessing elements after transformation
println("Squared sequence: ${squaredSequence.toList()}")

// Output
Squared sequence: [1, 4, 9, 16, 25]
17. Can a Sequence be mutable in Kotlin?

No, sequences are inherently immutable in Kotlin, but you can apply sequence operations to mutable collections.

18. runCatching in Kotlin.

This is a variation of run. runCatching is literally try…catch block but with important difference.
It encapsulates the result of the block execution into a Result object. Result type, which is a union between a Success type and a Failure type. Its purpose is to encapsulate the result of an action, whether successful or not, allowing it to be processed at a later time.
This encapsulation not only makes the code more readable but also facilitates safe data retrieval.
An added advantage is that results of runCatching blocks exectution can be compared.
run and runCatching are synchronous, and runBlocking and runInterruptible as asynchronous.
 suspend fun createUser(signUpUser: SignUpUser): Boolean {
        return runCatching {
            val user = hashMapOf(
                "name" to signUpUser.name,
                "email" to signUpUser.email
            )
            firestore.collection(USER_COLLECTION).add(user).await()
        }.isSuccess
    }
19. What are Callback Functions?

In Kotlin programming, a callback function is a function that is passed as an argument to another function.
The receiving function then invokes the callback function at an appropriate time during its execution.
This enables the receiving function to execute the callback function asynchronously, providing a way for the caller to handle the result of the function execution.
Use

Callback functions are also commonly used for event handling. An event is an occurrence in a program that is triggered by some external action, such as user input or a timer. Callback functions can be used to handle these events, allowing the program to respond to user input or other external stimuli in real-time.
20. elementAtOrElse, elementAtOrNull in Kotlin.

Returns the element at a specified index or a default value if the index is out of bounds.

val numbers = listOf(1, 2, 3, 4, 5)
val elementAtIndex = numbers.elementAtOrElse(7) { -1 }
// Output: -1
21. getOrElse, getOrNull in Kotlin.

Returns the element at the specified index or a default value if the index is out of bounds.

val numbers = listOf(1, 2, 3, 4, 5)
val element = numbers.getOrElse(7) { -1 }
// Output: -1getOrElse, getOrNull: Returns the element at the specified index or a default value if the index is out of bounds.

val numbers = listOf(1, 2, 3, 4, 5)
val element = numbers.getOrElse(7) { -1 }
// Output: -1
22. none in Kotlin.

Checks if no elements satisfy a condition.

val numbers = listOf(1, 3, 5, 7, 9)
val noneAreEven = numbers.none { it % 2 == 0 }
// Output: true
Platform-specific code
Date convert Kotlin Multiplatform.
//DateFormatter.formatLocalDate(date)

import kotlinx.datetime.LocalDate

expect object DateFormatter {
    fun formatLocalDate(localDate: LocalDate): String
}

//iosMain
actual object DateFormatter {
    actual fun formatLocalDate(localDate: LocalDate): String {

        val date = localDate.toNsDate()
            ?: throw IllegalStateException("Failed to convert LocalDateTime $LocalDateTime to NSDate")

        val formatter = NSDateFormatter().apply {
            dateFormat = "E d, MMM yyyy"
            locale = NSLocale.currentLocale
        }

        return formatter.stringFromDate(date)
    }

    @OptIn(ExperimentalForeignApi::class)
    private fun LocalDate.toNsDate(): NSDate? {
        val calendar = NSCalendar.currentCalendar
        val components = NSDateComponents()
        components.year = this.year.convert()
        components.month = this.monthNumber.convert()
        components.day = this.dayOfMonth.convert()
        return calendar.dateFromComponents(components)
    }
}

//androidMain
actual object DateFormatter {
    actual fun formatLocalDate(localDate: LocalDate): String {
        return localDate.toJavaLocalDate().format(DateTimeFormatter.ofPattern("E d, MMM yyyy"))
            ?: "tdb"
    }
}
