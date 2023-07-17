<script setup>
import { ref, onMounted } from 'vue';
const logoSrc = "/src/assets/images/logo_transparent.png";
const menuItems = [
  {
    id: "menu-item-16",
    title: "About",
    link: "#about",
    active: true,
  },
  {
    id: "menu-item-23",
    title: "Projects",
    link: "#projects",
    active: false,
  },
  {
    id: "menu-item-20",
    title: "Blog",
    link: "#latest-news",
    active: false,
  },
  {
    id: "menu-item-22",
    title: "Our Team",
    link: "#team",
    active: false,
  },
];
const description = "lldy is a great one-page theme, perfect for developers and designers but also for someone who just wants a new website for his business. Try it now!";
const learnMoreLink = "https://6492f0d520f7ac007a0633c5--bejewelled-gelato-b82b43.netlify.app/";
const downloadLink = "https://6492f0d520f7ac007a0633c5--bejewelled-gelato-b82b43.netlify.app/";

const sectionDescription = "It is an amazing one-page theme with great features that offers an incredible experience. It is easy to install, make changes, adapt for your business. A modern design with clean lines and styling for a wide variety of content, exactly how a business design should be. You can add as many images as you want to the main header area and turn them into a slider.";
const projects = [
  {
    id: "illdy_project-3",
    title: "[Illdy] - Project",
    link: "https://google.com",
    imageUrl: "/src/assets/images/front-page-project-4.jpg",
  },
  {
    id: "illdy_project-4",
    title: "[Illdy] - Project",
    link: "https://6492f0d520f7ac007a0633c5--bejewelled-gelato-b82b43.netlify.app/",
    imageUrl: "/src/assets/images/front-page-project-3.jpg",
  },
  {
    id: "illdy_project-5",
    title: "[Illdy] - Project",
    link: "#",
    imageUrl: "/src/assets/images/front-page-project-2.jpg",
  },
  {
    id: "illdy_project-6",
    title: "[Illdy] - Project",
    link: "https://colorlibhub.com/illdy/",
    imageUrl: "/src/assets/images/front-page-project-1.jpg",
  },
]
const services = [
  {
    id: "illdy_service-2",
    title: "Web Design",
    description: "Consectetur adipiscing elit. Praesent molestie urna hendrerit erat tincidunt tempus. Aliquam a leo risus. Fusce a metus non augue dapibus porttitor at in mauris. Pellentesque commodo...",
    color: "#f18b6d",
    iconClass: "fa fa-pencil",
  },
  {
    id: "illdy_service-3",
    title: "Web Development",
    description: "Consectetur adipiscing elit. Praesent molestie urna hendrerit erat tincidunt tempus. Aliquam a leo risus. Fusce a metus non augue dapibus porttitor at in mauris. Pellentesque commodo...",
    color: "#f1d204",
    iconClass: "fa fa-code",
  },
  {
    id: "illdy_service-4",
    title: "SEO Analysis",
    description: "Consectetur adipiscing elit. Praesent molestie urna hendrerit erat tincidunt tempus. Aliquam a leo risus. Fusce a metus non augue dapibus porttitor at in mauris. Pellentesque commodo...",
    color: "#6a4d8a",
    iconClass: "fa fa-search",
  },
];

const footerColumns = [
  {
    id: "text-5",
    elementId: "text-5",
    extraClass: "",
    title: "PRODUCTS",
    items: [
      { id: 1, title: "Our work", link: "#" },
      { id: 2, title: "Club", link: "#" },
      { id: 3, title: "News", link: "#" },
      { id: 4, title: "Announcement", link: "#" },
    ],
  },
  {
    id: "text-6",
    elementId: "text-6",
    extraClass: "",
    title: "INFORMATION",
    items: [
      { id: 1, title: "Pricing", link: "#" },
      { id: 2, title: "Terms", link: "#" },
      { id: 3, title: "Affiliates", link: "#" },
      { id: 4, title: "Blog", link: "#" },
    ],
  },
  {
    id: "text-7",
    elementId: "text-7",
    extraClass: "",
    title: "SUPPORT",
    items: [
      { id: 1, title: "Documentation", link: "#" },
      { id: 2, title: "FAQs", link: "#" },
      { id: 3, title: "Forums", link: "#" },
      { id: 4, title: "Contact", link: "#" },
    ],
  },
  {
    id: "empty-column",
    elementId: "",
    extraClass: "col-md-3 col-sm-6 col-xs-12",
    title: "",
    items: [],
  },
];
const teamMembers = [
  {
    id: "illdy_person-5",
    elementId: "illdy_person-5",
    extraClass: "",
    name: "Mark Lawrance",
    position: "Web Designer",
    description: "Creative, detail-oriented, always focused.",
    color: "#f18b6d",
    image: "/src/assets/images/front-page-team-1.jpg",
    socialLinks: [
      { id: 1, title: "Facebook", link: "#", iconClass: "fa fa-facebook" },
      { id: 2, title: "Twitter", link: "#", iconClass: "fa fa-twitter" },
      { id: 3, title: "LinkedIn", link: "#", iconClass: "fa fa-linkedin" },
    ],
  },
  {
    id: "illdy_person-4",
    elementId: "illdy_person-4",
    extraClass: "",
    name: "Jane Stenton",
    position: "SEO Specialist",
    description: "Curious, tech-geek, and gets serious when it comes to work.",
    color: "#f1d204",
    image: "/src/assets/images/front-page-team-2.jpg",
    socialLinks: [
      { id: 1, title: "Facebook", link: "#", iconClass: "fa fa-facebook" },
      { id: 2, title: "Twitter", link: "#", iconClass: "fa fa-twitter" },
      { id: 3, title: "LinkedIn", link: "#", iconClass: "fa fa-linkedin" },
    ],
  },
  {
    id: "illdy_person-2",
    elementId: "illdy_person-2",
    extraClass: "",
    name: "John Smith",
    position: "Developer",
    description: "Enthusiastic, passionate with a great sense of humor.",
    color: "#6a4d8a",
    image: "/src/assets/images/front-page-team-3.jpg",
    socialLinks: [
      { id: 1, title: "Facebook", link: "#", iconClass: "fa fa-facebook" },
      { id: 2, title: "Twitter", link: "#", iconClass: "fa fa-twitter" },
      { id: 3, title: "LinkedIn", link: "#", iconClass: "fa fa-linkedin" },
    ],
  },
];



const latestPosts = [
  {
    id: 1,
    title: 'We Have Made Illdy Theme SEO Friendly',
    link: 'https://colorlibhub.com/illdy/we-have-made-illdy-theme-seo-friendly/',
    image: '/src/assets/images/photo-1449168013943-3a15804bb41c-360x213.jpg',
    description: 'Illdy One Page WordPress theme is fully SEO friendly and is ready to help you achieve the highest rankings...',
  },
  {
    id: 2,
    title: 'Stunning One Page WordPress Theme For Masses',
    link: 'https://colorlibhub.com/illdy/stunning-one-page-wordpress-theme-masses/',
    image: '/src/assets/images/photo-1450101215322-bf5cd27642fc-360x213.jpg',
    description: 'This theme is not just free, it is free for private and commercial use since it is licensed under GPL...',
  },
  {
    id: 3,
    title: 'Hello world!',
    link: 'https://colorlibhub.com/illdy/hello-world/',
    image: '/src/assets/images/photo-1447687643809-e05fd462f350-360x213.jpg',
    description: 'Welcome to colorlib.com. This is our first post around Illdy WordPress theme. Now show that you can make out of it...',
  },
];

let showResponsiveMenu = false;
function toggleResponsiveMenu() {
  showResponsiveMenu = !showResponsiveMenu;
}

</script>

<template>
  <div class="home page-template-default page page-id-126 wp-custom-logo elementor-default elementor-kit-297">
    <div class="pace-overlay"></div>
    <header id="header" class="header-front-page"
      :style="{ backgroundImage: 'url(https://picsum.photos/1380)', backgroundAttachment: 'fixed' }">
      <!-- Top Header -->
      <div class="top-header">
        <div class="container">
          <div class="row">
            <div class="col-sm-4 col-xs-8">
              <a title="Illdy Theme Demo">
                <img class="header-logo-img" :src="logoSrc" width />
              </a>
            </div>
            <div class="col-sm-8 col-xs-4">
              <nav class="header-navigation">
                <ul id="menu-illdy-main" class="clearfix">
                  <li v-for="menuItem in menuItems" :key="menuItem.id"
                    :class="{ 'current-menu-item': menuItem.active, 'current_page_item': menuItem.active }">
                    <a :href="menuItem.link" aria-current="page">{{ menuItem.title }}</a>
                  </li>
                </ul>
              </nav>
              <button class="open-responsive-menu" @click="toggleResponsiveMenu">
                <i class="fa fa-bars"></i>
              </button>
            </div>
          </div>
        </div>
      </div>

      <!-- Responsive Menu -->
      <nav class="responsive-menu" v-show="showResponsiveMenu">
        <ul>
          <li v-for="menuItem in menuItems" :key="menuItem.id">
            <a :href="menuItem.link" aria-current="page">{{ menuItem.title }}</a>
          </li>
        </ul>
      </nav>

      <!-- Bottom Header -->
      <div class="bottom-header front-page">
        <div class="container">
          <div class="row">
            <div class="col-sm-12">
              <h1>
                Clean<span class="span-dot">.</span>Slick<span class="span-dot">.</span>Pixel Perfect
              </h1>
            </div>
            <div class="col-sm-8 col-sm-offset-2">
              <div class="section-description">
                {{ description }}
              </div>
              <a :href="learnMoreLink" title="Learn more" class="header-button-one">Learn more</a>
              <a :href="downloadLink" title="Download" class="header-button-two">Download</a>
            </div>
          </div>
        </div>
      </div>
    </header>
    <section id="about" class="front-page-section">
      <!-- Section Header -->
      <div class="section-header">
        <div class="container">
          <div class="row">
            <div class="col-sm-12">
              <h3>About</h3>
            </div>
            <div class="col-sm-10 col-sm-offset-1">
              <div class="section-description">
                {{ sectionDescription }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section id="projects" class="front-page-section">
      <!-- Section Header -->
      <div class="section-header">
        <div class="container">
          <div class="row">
            <div class="col-sm-12">
              <h3>Projects</h3>
            </div>
            <div class="col-sm-10 col-sm-offset-1">
              <div class="section-description">
                You'll love our work. Check it out!
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Section Content -->
      <div class="section-content">
        <div class="container-fluid">
          <div class="row inline-columns">
            <div v-for="project in projects" :key="project.id" :id="project.elementId"
              class="col-sm-3 col-xs-6 no-padding widget_illdy_project">
              <a :href="project.link" :title="project.title" class="project" data-fancybox="gallery"
                :style="{ backgroundImage: 'url(' + project.imageUrl + ')' }">
                <span class="project-overlay"></span>
              </a>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section id="services" class="front-page-section">
      <!-- Section Header -->
      <div class="section-header">
        <div class="container">
          <div class="row">
            <div class="col-sm-12">
              <h3>Services</h3>
            </div>
            <div class="col-sm-10 col-sm-offset-1">
              <div class="section-description">
                In order to help you grow your business, our carefully selected experts can advise you in the following
                areas:
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Section Content -->
      <div class="section-content">
        <div class="container">
          <div class="row inline-columns">
            <div v-for="service in services" :key="service.id" :id="service.elementId"
              class="col-sm-4 widget_illdy_service">
              <div class="service" :data-service-color="service.color">
                <div class="service-icon"><i :class="service.iconClass"></i></div>
                <div class="service-title">
                  <h5>{{ service.title }}</h5>
                </div>
                <div class="service-entry">
                  {{ service.description }}
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section id="latest-news" class="front-page-section">
      <div class="section-header">
        <div class="container">
          <div class="row">
            <div class="col-sm-12">
              <h3>Latest News</h3>
            </div>
            <div class="col-sm-10 col-sm-offset-1">
              <div class="section-description">
                If you are interested in the latest articles in the industry, take a sneak peek at our blog. You have
                nothing to lose!
              </div>
            </div>
          </div>
        </div>
      </div>
      <a href="https://colorlibhub.com/illdy/blog-2/" title="See blog" class="latest-news-button">
        <i class="fa fa-chevron-circle-right"></i>See blog
      </a>
      <div class="section-content">
        <div class="container">
          <div class="row blog-carousel">
            <div class="illdy-blog-post col-md-4 col-sm-6 col-xs-12">
              <div class="post" style="
                            ">
                <div class="post-image"
                  style="background-image: url(&#x27;/src/assets/images/photo-1449168013943-3a15804bb41c-360x213.jpg&#x27;);">
                </div>
                <h5><a href="https://colorlibhub.com/illdy/we-have-made-illdy-theme-seo-friendly/"
                    title="We Have Made Illdy Theme SEO Friendly" class="post-title">We Have Made Illdy Theme SEO
                    Friendly</a></h5>
                <div class="post-entry">
                  Illdy One Page WordPress theme is fully SEO friendly and is ready to help you to achieve the highest
                  rankings&hellip; </div>
                <a href="https://colorlibhub.com/illdy/we-have-made-illdy-theme-seo-friendly/" title="Read more"
                  class="post-button"><i class="fa fa-chevron-circle-right"></i>Read more </a>
              </div>
            </div>
            <div class="illdy-blog-post col-md-4 col-sm-6 col-xs-12">
              <div class="post" style="
                            ">
                <div class="post-image"
                  style="background-image: url(&#x27;/src/assets/images/photo-1450101215322-bf5cd27642fc-360x213.jpg&#x27;);">
                </div>
                <h5><a href="https://colorlibhub.com/illdy/stunning-one-page-wordpress-theme-masses/"
                    title="Stunning One Page WordPress Theme For Masses" class="post-title">Stunning One Page WordPress
                    Theme For Masses</a></h5>
                <div class="post-entry">
                  This theme is not just free, it is free for private and commercial use since it is licensed under
                  GPL&hellip; </div>
                <a href="https://colorlibhub.com/illdy/stunning-one-page-wordpress-theme-masses/" title="Read more"
                  class="post-button"><i class="fa fa-chevron-circle-right"></i>Read more </a>
              </div>
            </div>
            <div class="illdy-blog-post col-md-4 col-sm-6 col-xs-12">
              <div class="post" style="
                            ">
                <div class="post-image"
                  style="background-image: url(&#x27;/src/assets/images/photo-1447687643809-e05fd462f350-360x213.jpg&#x27;);">
                </div>
                <h5><a href="https://colorlibhub.com/illdy/hello-world/" title="Hello world!" class="post-title">Hello
                    world!</a></h5>
                <div class="post-entry">
                  Welcome to colorlib.com. This is our first post around Illdy WordPress theme. Now show that you can make
                  out of it.&hellip; </div>
                <a href="https://colorlibhub.com/illdy/hello-world/" title="Read more" class="post-button"><i
                    class="fa fa-chevron-circle-right"></i>Read more </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section id="team" class="front-page-section">
      <div class="section-header">
        <div class="container">
          <div class="row">
            <div class="col-sm-12">
              <h3>Team</h3>
            </div>
            <div class="col-sm-10 col-sm-offset-1">
              <div class="section-description">
                Meet the people that are going to take your business to the next level.
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="section-content">
        <div class="container">
          <div class="row inline-columns">
            <div v-for="person in teamMembers" :key="person.id"
              :class="`col-sm-4 col-sm-offset-0 col-xs-10 col-xs-offset-1 widget_illdy_person ${person.extraClass}`">
              <div :id="person.elementId" class="person clearfix" :data-person-color="person.color">
                <div class="person-image">
                  <img :src="person.image" :alt="person.name" :title="person.name" />
                </div>
                <div class="person-content">
                  <h6>{{ person.name }}</h6>
                  <p class="person-position">{{ person.position }}</p>
                  <p>{{ person.description }}</p>
                  <ul class="person-content-social clearfix">
                    <li v-for="social in person.socialLinks" :key="social.id">
                      <a :href="social.link" :title="social.title" target="_blank" rel="nofollow">
                        <i :class="social.iconClass"></i>
                      </a>
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <footer id="footer">
      <div class="container">
        <div class="row">
          <div v-for="column in footerColumns" :key="column.id"
            :class="`col-md-3 col-sm-6 col-xs-12 ${column.extraClass}`">
            <div :id="column.elementId" class="widget widget_text">
              <div class="widget-title">
                <h5>{{ column.title }}</h5>
              </div>
              <div class="textwidget">
                <ul>
                  <li v-for="item in column.items" :key="item.id">
                    <a :href="item.link" :title="item.title">{{ item.title }}</a>
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </footer>
    <div class="bottom-footer">
      <div class="container">
        <p class="copyright">
          <span>
            <a href="https://github.com/mashudkarim85" title="Illdy" target="_blank">Blackboard</a>.</span>
          <span class="bottom-copyright" data-customizer="copyright-credit">© Copyright 2023. All Rights
            Reserved.</span>
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.pace .pace-progress {
  background-color: #f1d204;
  color: #f1d204;
}

.pace .pace-activity {
  box-shadow: inset 0 0 0 2px #f1d204, inset 0 0 0 7px #ffffff;
}

.pace-overlay {
  background-color: #ffffff;
}

.recentcomments a {
  display: inline !important;
  padding: 0 !important;
  margin: 0 !important;
}

.header-logo-img {
  height: 120px;
}
#header.header-front-page .bottom-header .header-button-one {
  background-color: rgba(0, 0, 0, 0.2);
}

#header.header-front-page .bottom-header .header-button-one:hover,
#header.header-front-page .bottom-header .header-button-one:focus {
  background-color: rgba(0, 0, 0, 0.1);
}

#header.header-front-page .bottom-header h1 {
  color: #ffffff;
}

#header.header-front-page .bottom-header .section-description {
  color: #ffffff;
}

#projects:before {
  background-image: url(/src/assets/images/pattern.png) !important;
}

#projects:before {
  background-size: auto !important;
}

#projects:before {
  background-repeat: repeat !important;
}

#testimonials:before {
  background-image: url(/src/assets/images/testiomnials-background.jpg) !important;
}

#testimonials:before {
  background-attachment: scroll !important;
}</style>
