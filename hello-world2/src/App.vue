<template>
  <div>
    <GreetComponent name ='divya' hero-Name='wonder woman'/>
    <GreetComponent name ='disha' hero-Name='batman'/>
    <GreetComponent :name ='name' :hero-Name='channel'/>
    <ArticleComponent title="Article Title" :likes="50" :isPublished="true"/>
    <h2> App Component username: {{ name }}</h2>
    
    <ComponentC />
    <input type="text" v-model="userClass">
    <CardComponent ><h2>card content</h2></CardComponent>
    <CardComponent >Card Content</CardComponent>
    <CardComponent>
      <img src="https://picsum.photos/200" alt="image">
    </CardComponent>
    
    <CardComponent>
      <template v-slot:header>
        <h2>This is the Card Header</h2>
      </template>
      <template v-slot:default>
      <p><img src="https://picsum.photos/200" alt="image"></p>
      </template>
      <template v-slot:footer>
        <button>Click Me</button>
      </template>
    </CardComponent>
    
    <NameListComponent >
      <template v-slot:default="{ firstName, lastName }">
        {{ firstName }} {{ lastName }}
      </template>
      
    </NameListComponent>
    
    <NameListComponent >
      <template v-slot:default="{ firstName, lastName }">
        {{ lastName }} {{ firstName }}
      </template>
      
    </NameListComponent>

    <NameListComponent >
      <template v-slot:default="{ firstName}">
        {{ firstName }} 
      </template>

    </NameListComponent>
  <h3>App component text
  <ChildStylesComponent /></h3>

  <button @click="activeTab = 'TabAComponent'">Tab A</button>
  <button @click="activeTab = 'TabBComponent'">Tab B</button>
  <button @click="activeTab = 'TabCComponent'">Tab C</button>

<keep-alive>
  <component :is="activeTab"/>
</keep-alive>

<Teleport to="#portal-root">
  <PortalComponent />
</teleport>

  <PostListComponent />
  <br>
  <CreatePostComponent />
  <br>  
  <ParentComponent />
  <br>
  <TemplateRefComponent />
  <br>
  <ClickCounterComponent />
  <br>
  <HoverCounterComponent />
  <br>
  <DataComponent />
  <br>
  <DemoOneComponent />
  <br>
  <DemoTwoComponent />
  <br>
  <MethodsComponent />
  <br>  
  <VModelComponent />
  <br>
  <ComputedComponents />
  <br>
  <WatchComponents />
  <br>
  <ProvideInjectComponent />
  <br>
  <PersonComponent />
  </div>


</template>

<script>
import GreetComponent from './components/GreetComponent.vue'
import ArticleComponent from './components/ArticleComponent.vue'
import ComponentC from './components/ComponentC.vue' 
import CardComponent from './components/CardComponent.vue'
import NameListComponent from './components/NameListComponent.vue'
import ChildStylesComponent from './components/ChildStylesComponent.vue'
import TabAComponent from './components/TabAComponent.vue'
import TabBComponent from './components/TabBComponent.vue'
import TabCComponent from './components/TabCComponent.vue' 
import PortalComponent from './components/PortalComponent.vue'  
import PostListComponent from './components/PostListComponent.vue'
import CreatePostComponent from './components/CreatePostComponent.vue'
import ParentComponent from './components/ParentComponent.vue'
import TemplateRefComponent from './components/TemplateRefComponent.vue'
import ClickCounterComponent from './components/ClickCounterComponent.vue'
import HoverCounterComponent from './components/HoverCounterComponent.vue'
import DataComponent from './components/DataComponent.vue'
import DemoOneComponent from './components/DemoOneComponent.vue'  
import DemoTwoComponent from './components/DemoTwoComponent.vue'
import MethodsComponent from './components/MethodsComponent.vue'
import VModelComponent from './components/VModelComponent.vue'
import ComputedComponents from './components/ComputedComponents.vue'
import WatchComponents from './components/WatchComponents.vue'
import ProvideInjectComponent from './components/ProvideInjectComponent.vue'
import PersonComponent from './components/PersonComponent.vue'

export default {
  name: 'App',
  components: {
    GreetComponent,
    ArticleComponent,
    ComponentC,
    CardComponent,
    NameListComponent,
    ChildStylesComponent,
    TabAComponent,
    TabBComponent,
    TabCComponent,
    PortalComponent,
    PostListComponent,
    CreatePostComponent,
    ParentComponent,
    TemplateRefComponent,
    ClickCounterComponent,
    HoverCounterComponent,
    DataComponent,
    DemoOneComponent,
    DemoTwoComponent,
    MethodsComponent,
    VModelComponent,
    ComputedComponents,
    WatchComponents,
    ProvideInjectComponent,
    PersonComponent,
    
  },
  data() {
    return {
      name: 'divya',
      channel: 'vue channel',
      userClass: '',
      activeTab: 'TabAComponent',
    }
  },
  provide(){
  return {
    username: this.name,
  }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h3 {
  color:orchid;
}
</style>
