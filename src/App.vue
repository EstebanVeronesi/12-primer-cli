<template>
  <div id="app">
    <Header title="Portfolio GH" />
    <Container />
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header';
import Footer from './components/Footer';
import Container from './components/Container';

export default {
  components: {
    Header,
    Footer,
    Container
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto&family=Source+Serif+Pro:ital,wght@1,300&display=swap');

* {
  margin: 0;
  padding: 0;
  font-family: 'Roboto', sans-serif;
}
</style>
