import React, { Component } from 'react';
import { StyleSheet, Switch, View, Text, Image } from 'react-native';
import {useState} from 'react'

export default class App extends Component {
  state = {
    switchValue: false
  }

  render() {
    return (
      <View style={styles.container}>
        <Text style={styles.textStyle}>Switch Example</Text>
        <Image source={this.state.switchValue ? require('./assets/light2.png'):require('./assets/black.png')} style={{width: 250, height:250}} />
        <Switch
          style={{ marginBottom: 10 }}
          value={this.state.switchValue}
          onValueChange={(switchValue) => this.setState({ switchValue })}
        />
        <Text style={styles.textStyle}>{this.state.switchValue ? 'on' : 'off'}</Text>
      </View>
    );
  }
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    alignItems: 'center',
    justifyContent: 'center',
  },
  textStyle: {
    margin: 24,
    fontSize: 25,
    fontWeight: 'bold',
    textAlign: 'center',
    color: '#3498db'
  },
});
