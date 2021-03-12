<template>
  <div class="container-fluid px-0">
    <article class="main-image">
      <section>
        <div class="user-thumb mb-5">
          <div class="layer2"></div>
          <div class="layer3"></div>
          <div class="layer5"><span>Meow!</span></div>
        </div>
        <h1>Hi, I'm Ken Lo.</h1>
        <span
          >I'm currently a Final Year Student at The Open University of Hong
          Kong. My interests include VueJS, ReactJS, NodeJS, CSS.</span
        >
        <button class="btn btn-xl btn-light" @click="scrollTo('find-more')">
          About Me
        </button>
      </section>
    </article>

    <article id="find-more" class="white-section">
      <section>
        <h3 class="mb-5">About Me</h3>
        <span>I love Front-end.</span>
        <span
          >I like to <b>create</b> smart user interface,
          <b>code</b> beautifully, and <b>catch up</b> with the latest
          technologies.
        </span>
      </section>
    </article>

    <article id="offers" class="blue-section">
      <section class="container">
        <h2 class="mb-5">I'm interested in ...</h2>
        <div class="row">
          <div
            class="col-lg-3 col-md-6 mb-5 mb-lg-0"
            v-for="(offer, index) in offers"
            :key="index"
          >
            <div class="icon mx-auto">
              <i class="fab" :class="offer.icon"></i>
            </div>
            <h4>{{ offer.title }}</h4>
          </div>
        </div>
      </section>
    </article>

    <article class="second-image">
      <section>
        <h2>Here is what I built!</h2>
        <button
          class="btn btn-xl btn-dark"
          @click="scrollTo('recent-projects')"
        >
          Latest Works
        </button>
      </section>
    </article>

    <article id="recent-projects" class="white-section">
      <section class="container">
        <h3>Latest Works</h3>
        <div class="row no-gutters">
          <div
            class="col-lg-12 pb-5"
            v-for="(project, index) in recentProjects"
            :key="index"
          >
            <div href="" class="portfolio-item">
              <span class="caption">
                <span class="caption-content">
                  <h2>{{ project.title }}</h2>
                  <p class="mb-0">{{ project.description }}</p>
                </span>
              </span>
              <img
                class="img-fluid"
                :src="require('../assets/' + project.img)"
                alt=""
              />
            </div>
          </div>
        </div>
      </section>
    </article>

    <article class="blue-section">
      <section class="contianer">
        <h3>
          “Design is not just what it looks like and feels like. Design is how
          it works.”
        </h3>
        <span class="author">Steve Jobs</span>
      </section>
    </article>

    <article class="footer">
      <section class="contianer">
        <h3>Contact Me &#128570;</h3>
        <div class="row">
          <div
            class="col-4 mt-3 mb-5 mb-lg-0"
            v-for="(contact, index) in contacts"
            :key="index"
          >
            <div class="icon mx-auto">
              <a :href="contact.url" target="_blank">
                <i :class="contact.icon"></i>
              </a>
            </div>
          </div>
        </div>
        <h5 class="mt-5">Portfolio v0.1</h5>
      </section>
    </article>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      offers: [
        {
          icon: "fa-vuejs",
          title: "VueJS",
        },
        {
          icon: "fa-react",
          title: "ReactJS",
        },
        {
          icon: "fa-node-js",
          title: "NodeJS",
        },
        {
          icon: "fa-css3-alt",
          title: "CSS",
        },
      ],
      recentProjects: [
        {
          img: "tccp_app.jpg",
          title: "TONGUE TECH",
          description: "An APP for Tuition Center Comparison Platform",
        },
        {
          img: "tccp_cms.png",
          title: "TONGUE TECH",
          description:
            "A Content Management System for Tuition Center Comparison Platform",
        },
        {
          img: "hklife.png",
          title: "SOLUTION FOREST",
          description: "A Website Prototype for Hai Kang Life",
        },
        {
          img: "wifi.png",
          title: "LINKSURE",
          description: "An Internal Management System for LinkSure",
        },
      ],
      contacts: [
        {
          icon: "fas fa-envelope",
          url: "mailto:kenlobus@gmail.com",
        },
        {
          icon: "fab fa-github",
          url: "https://github.com/kenvlo",
        },
        {
          icon: "fab fa-linkedin",
          url: "https://www.linkedin.com/in/kenlobus/",
        },
      ],
    };
  },
  methods: {
    scrollTo(element) {
      const el = document.querySelector("#" + element);
      el.scrollIntoView({
        behavior: "smooth",
        block: "start",
      });
    },
  },
};
</script>

<style lang="scss">
@import url("https://use.fontawesome.com/releases/v5.10.0/css/all.css");
@import url("https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css");

article {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  padding: 0 10px;
}

.btn-xl {
  padding: 20px 35px;
  font-family: serif;
  font-size: 1.25rem;
}

.main-image,
.second-image {
  min-height: 100vh;
  background-size: cover;
  padding: 0 10px;
  text-align: center;

  h1 {
    font-size: 5rem;
    font-weight: bold;
    margin-bottom: 30px;
  }

  h2 {
    font-size: 3rem;
    font-weight: bold;
    margin-bottom: 30px;
  }

  span {
    display: block;
    padding-bottom: 30px;
    font-size: 1.6rem;
    font-weight: bold;
  }

  @media (max-width: 992px) {
    h1 {
      font-size: 4rem;
      font-weight: bold;
      margin-bottom: 30px;
    }

    span {
      display: block;
      padding-bottom: 30px;
      font-size: 1.5rem;
      font-weight: bold;
    }
  }

  @media (max-width: 768px) {
    h1 {
      font-size: 3rem;
      font-weight: bold;
      margin-bottom: 30px;
    }

    span {
      display: block;
      padding-bottom: 30px;
      font-size: 1.4rem;
      font-weight: bold;
    }
  }

  @media (max-width: 576px) {
    h1 {
      font-size: 2rem;
      font-weight: bold;
      margin-bottom: 30px;
    }

    span {
      display: block;
      padding-bottom: 30px;
      font-size: 1.3rem;
      font-weight: bold;
    }
  }
}

.user-thumb {
  width: 200px;
  height: 200px;
  margin: 0 auto;
  margin-top: 100px;
  position: relative;
  cursor: pointer;

  @media (max-width: 576px) {
    display: none;
  }

  .layer2,
  .layer3 {
    position: absolute;
    border-radius: 50%;
    overflow: hidden;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  .layer2 {
    width: 193px;
    height: 193px;
    background: #313131;
    z-index: 2;
    transition: all 0.45s cubic-bezier(0.68, -0.55, 0.265, 1.55);
  }

  .layer3 {
    width: 180px;
    height: 180px;
    background-image: url("../assets/avatar.jpg");
    background-size: 100% 100%;
    z-index: 3;
    transition: all 0.45s cubic-bezier(0.68, -0.55, 0.265, 1.55);
    border: 0px solid white;
  }

  .layer5 {
    position: absolute;
    top: 10px;
    left: 10px;
    width: 180px;
    height: 180px;
    border-radius: 50%;
    background: rgba(0, 0, 0, 0);
    z-index: 4;
    overflow: hidden;
    text-align: center;
    line-height: 120px;
    opacity: 1;
    transition: all 0.45s cubic-bezier(0.68, -0.55, 0.265, 1.55);
    transition-delay: 0.15s;

    span {
      position: absolute;
      top: 60%;
      left: 50%;
      transform: translate(200%, -50%);
      color: white;
      opacity: 0;
      transition: all 0.25s cubic-bezier(0.68, -0.55, 0.265, 1.55);
      transition-delay: 0.45s;
    }
  }

  &:hover,
  &:active {
    .layer1 {
      width: 119px;
      height: 119px;
      transition: all 0.45s cubic-bezier(0.68, -0.55, 0.265, 1.55);
    }
    .layer2 {
      width: 114px;
      height: 114px;
      transition: all 0.45s cubic-bezier(0.68, -0.55, 0.265, 1.55);
    }
    .layer3 {
      background-size: 140% 140%;
      border: 4px solid gold;
      transition: all 0.45s cubic-bezier(0.68, -0.55, 0.265, 1.55);
    }
    .layer5 {
      background: rgba(0, 0, 0, 0.5);
      transition: all 0.45s cubic-bezier(0.68, -0.55, 0.265, 1.55);
      transition-delay: 0.15s;
      span {
        transform: translate(-50%, -50%);
        opacity: 1;
        transition: all 0.25s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        transition-delay: 0.45s;
      }
    }
  }





}

.main-image {
  background: url("../assets/main_image.jpg") center center;
}

.second-image {
  background: url("../assets/markus-spiske-wFsbpYoGjOI-unsplash.jpg") center
    center;
}

.white-section {
  padding: 120px 10px;
  background-color: #fff;
  text-align: center;

  h3 {
    font-size: 2rem;
    font-weight: bold;
  }

  span {
    display: block;
    padding-bottom: 30px;
    font-size: 1.25rem;
  }

  @media (max-width: 992px) {
    h2 {
      font-size: 1.65rem;
    }

    span {
      padding-bottom: 20px;
    }
  }

  @media (max-width: 768px) {
    h2 {
      font-size: 1.25rem;
    }

    span {
      padding-bottom: 5px;
    }
  }

  @media (max-width: 576px) {
    h2 {
      font-size: 1.2rem;
    }

    span {
      padding-top: 15px;
      padding-bottom: 0px;
    }
  }

  b {
    color: #1d809f;
  }

  .row {
    padding-top: 50px;
  }

  .portfolio-item {
    display: block;
    position: relative;
    overflow: hidden;

    .caption {
      display: flex;
      height: 100%;
      width: 100%;
      position: absolute;
      top: 0;
      bottom: 0;
      z-index: 1;
      background-color: rgba($color: #000000, $alpha: 0.2);
      transition: transform 0.2s linear;

      .caption-content {
        text-align: left;
        color: #fff;
        margin: auto 2rem 2rem;
      }

      @media (max-width: 992px) {
        span {
          padding-bottom: 20px;
          font-size: 1rem;
        }
      }

      @media (max-width: 768px) {
        span {
          padding-bottom: 5px;
          font-size: 0.75rem;
        }
      }

      @media (max-width: 576px) {
        span {
          padding-top: 15px;
          padding-bottom: 0px;
          font-size: 0.5rem;
        }
      }
    }

    img {
      transition: transform 0.2s linear;
    }

    &:hover {
      img {
        transform: scale(0.9);
      }

      .caption {
        transform: scale(0.9);
        background-color: rgba($color: #000000, $alpha: 0.5);
      }
    }
  }
}

.blue-section {
  padding: 120px 10px;
  background-color: #1d809f;
  color: #fff;
  text-align: center;

  h3 {
    font-size: 2rem;
    font-weight: bold;
    margin-bottom: 30px;
  }

  h4 {
    font-size: 1.6rem;
    padding-top: 20px;
  }

  .author {
    font-size: 1.7rem;
  }

  .icon {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 120px;
    height: 120px;
    background-color: #fff;
    color: #1d809f;
    border-radius: 50%;

    i {
      font-size: 4rem;
    }
  }

  @media (max-width: 992px) {
    h3 {
      font-size: 1.7rem;
    }

    .author {
      font-size: 1.5rem;
    }
  }

  @media (max-width: 768px) {
    h3 {
      font-size: 1.5rem;
    }

    .author {
      font-size: 1.3rem;
    }
  }

  @media (max-width: 576px) {
    h3 {
      font-size: 1.3rem;
    }

    .author {
      font-size: 1.1rem;
    }
  }
}

.footer {
  padding: 120px 10px;
  background-color: #fff;
  text-align: center;

  h3 {
    font-size: 2rem;
    font-weight: bold;
  }

  .icon {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 75px;
    height: 75px;
    background-color: #000;
    border-radius: 50%;

    i {
      font-size: 2.2rem;
      color: #fff;
    }
  }

  @media (max-width: 992px) {
    .icon {
      width: 70px;
      height: 70px;

      i {
        font-size: 2rem;
      }
    }
  }

  @media (max-width: 768px) {
    .icon {
      width: 60px;
      height: 60px;

      i {
        font-size: 1.8rem;
      }
    }
  }

  @media (max-width: 576px) {
    .icon {
      width: 50px;
      height: 50px;

      i {
        font-size: 1.6rem;
      }
    }
  }
}
</style>
