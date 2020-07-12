# react-native-bottomsheet-reanimated
Highly configurable component imitating [native bottom sheet behavior](https://material.io/design/components/sheets-bottom.html#standard-bottom-sheet), with fully native 60 FPS animations!

Built from scratch with [react-native-interactable-reanimted](https://www.npmjs.com/package/react-native-interactable-reanimted) and [react-native-reanimated](https://github.com/kmagiera/react-native-reanimated).

Usable with Expo with no extra native dependencies!

![](media/bottom1.gif)  |  ![](media/bottom2.gif) |  ![](media/bottom3.gif)  |
:---------------:|:----------------:|:-----------------:|


## Installation

Open a Terminal in the project root and run:

```sh
yarn add react-native-bottomsheet-reanimated
```

or if you use `npm`:

```sh
npm install react-native-bottomsheet-reanimated
```

If you are using Expo, you are done.

If you don't use Expo, install and link [react-native-gesture-handler](https://kmagiera.github.io/react-native-gesture-handler/docs/getting-started.html) and [react-native-reanimated](https://github.com/kmagiera/react-native-reanimated).

## Usage

```javascript
import BottomSheet from "react-native-bottomsheet-reanimated";

class Example extends React.Component {

  render() {
    return (
      <View style={styles.container}>
        <BottomSheet
          bottomSheerColor="#FFFFFF"
          // backDropColor="red"
          ref="BottomSheet"
          initialPosition={{ y: 300 }}
          snapPoints={snapPoints}
          isBackDrop={true}
          // isModal
          isBackDropDismisByPress={true}
          isRoundBorderWithTipHeader={true}
          header={
            <View>
              <Text style={styles.text}>Header</Text>
            </View>
          }
          body={
            <View style={styles.body}>
              <Text style={styles.text}>Body</Text>
            </View>
          }
        />
    </View>)
  }
}
```

## Props

| name                      | required | default | description |
| ------------------------- | -------- | ------- | ------------|
| snapPoints                | yes      |         | E.g. `[300, 200, 0]`. Points for snapping of bottom sheet coomponent. They define distance from bottom of the screen. Might be number or percent (as string e.g. `'20%'`) for points or percents of screen height from bottom. Note: Array values must be in descending order. |
| initialPosition               | no       |    0    | Determines initial snap point of bottom sheet. The value is the index from snapPoints. |
| body             | no       |         | Method for rendering scrollable content of bottom sheet. |
| header              | no       |         | Method for rendering non-scrollable header of bottom sheet. |
| bottomSheerColor | no       | `#ffffff`  | for background color of bottom sheet. |
| isBackDrop | no       | `false`  | for show backdrop behind the bottom sheet. |
| isBackDropDismisByPress | no       | `false`  | enable to move bottomsheet to first snappoint by pressing backdrop. |
| isRoundBorderWithTipHeader | no       | `false`  | give round with tip header style to bottomsheet. |
| isModal     | no       | `false`  | to make bottom sheet like modal. |
| isAnimatedYFromParent        | no       |  | If `true` then give animated value to `animatedValueY` props. |
| animatedValueY        | no       |  | If isAnimatedYFromParent will be `true` then it will give animtedY value to `animatedValueY` props. |


## Methods

### `snapTo(index)`

Imperative method on for snapping to snap point in given index. E.g.

```javascript
// Snap to the snap point at index 0 (e.g. 450 in [450, 300, 0])
this.refs.BottomSheet.current.snapTo(9)
```

Here `this.refs.BottomSheet` refers [to the `ref`](https://reactjs.org/docs/react-api.html#reactcreateref) passed to the `BottomSheet` component.

## Example

More complex examples can be found in the `Example` folder. To view the examples in the [Expo app](https://expo.io/), open a Terminal and run:

```sh
yarn
cd Example
yarn
expo start
```

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore -->
<table>
  <tr>
    <td align="center"><a href="https://github.com/nomi9995"><img src="https://avatars3.githubusercontent.com/u/36044436?s=460&u=c7471cd9ccec793c7a0fccc7db475a577ff7969d&v=4" width="100px;" alt="Numan"/><br /><sub><b>Numan</b></sub></a><br /><a href="#infra-Numan" title="Infrastructure (Hosting, Build-Tools, etc)">🚇</a> <a href="https://github.com/nomi9995/react-native-bottomsheet-reanimated/commits?author=nomi9995" title="Code">💻</a></td>
  </tr>
</table>

<!-- ALL-CONTRIBUTORS-LIST:END -->
