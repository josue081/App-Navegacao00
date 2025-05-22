// App.js
import React from 'react';
import { Button, Text, View, StyleSheet } from 'react-native';
import { NavigationContainer } from '@react-navigation/native';
import { createStackNavigator } from '@react-navigation/stack';

const Stack = createStackNavigator();

function HomeScreen({ navigation }) {
  return (
    <View style={styles.homeContainer}>
      <Text style={styles.title}>Bem-vindo ao Meu App!</Text>
      <Text style={styles.subtitle}>Aqui você pode navegar para seu perfil.</Text>
      <Button
        title="Ir para a Tela Perfil"
        color="#003366"
        onPress={() => navigation.navigate('Perfil')}
      />
    </View>
  );
}

function PerfilScreen({ navigation }) {
  return (
    <View style={styles.perfilContainer}>
      <Text style={styles.title}>Olá, essa é a Tela de Perfil!</Text>
      <Text style={styles.info}>Nome: Josué Moraes</Text>
      <Text style={styles.info}>Email: josue.moraes23@etepd.com</Text>
      <Text style={styles.info}>Curso: Desenvolvimento Mobile</Text>
      <View style={{ marginTop: 20 }}>
        <Button
          title="Voltar para Home"
          color="#006600"
          onPress={() => navigation.goBack()}
        />
      </View>
    </View>
  );
}

const styles = StyleSheet.create({
  homeContainer: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#ADD8E6', // azul claro
    padding: 20,
  },
  perfilContainer: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#90EE90', // verde claro
    padding: 20,
  },
  title: {
    fontSize: 26,
    fontWeight: 'bold',
    marginBottom: 15,
  },
  subtitle: {
    fontSize: 16,
    marginBottom: 30,
    color: '#333',
  },
  info: {
    fontSize: 18,
    marginVertical: 4,
  },
});

export default function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator initialRouteName="Home">
        <Stack.Screen name="Home" component={HomeScreen} />
        <Stack.Screen name="Perfil" component={PerfilScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}
