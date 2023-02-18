<template>
  <div class="project__cards-item flex flex-jc-sb">
    <div class="card-image">
      <img
        :src="require(`@/assets/img/projects/${img}`)"
        :alt="'image for Allan\'s ' + title + ' project'"
        width="500"
        height="280"
      />
    </div>

    <div class="card-text">
      <div class="title-wrapper flex flex-ai-c flex-jc-sb">
        <h4>{{ title }}</h4>
        <small v-if="!isCollab">{{ tag }}</small>
        <small v-else class="flex flex-ai-c with-icon"
          >{{ tag }}
          <svg
            fill="currentColor"
            width="25"
            height="25"
            viewBox="0 0 1024 1024"
            xmlns="http://www.w3.org/2000/svg"
            class="icon"
          >
            <path
              d="M824.2 699.9a301.55 301.55 0 0 0-86.4-60.4C783.1 602.8 812 546.8 812 484c0-110.8-92.4-201.7-203.2-200-109.1 1.7-197 90.6-197 200 0 62.8 29 118.8 74.2 155.5a300.95 300.95 0 0 0-86.4 60.4C345 754.6 314 826.8 312 903.8a8 8 0 0 0 8 8.2h56c4.3 0 7.9-3.4 8-7.7 1.9-58 25.4-112.3 66.7-153.5A226.62 226.62 0 0 1 612 684c60.9 0 118.2 23.7 161.3 66.8C814.5 792 838 846.3 840 904.3c.1 4.3 3.7 7.7 8 7.7h56a8 8 0 0 0 8-8.2c-2-77-33-149.2-87.8-203.9zM612 612c-34.2 0-66.4-13.3-90.5-37.5a126.86 126.86 0 0 1-37.5-91.8c.3-32.8 13.4-64.5 36.3-88 24-24.6 56.1-38.3 90.4-38.7 33.9-.3 66.8 12.9 91 36.6 24.8 24.3 38.4 56.8 38.4 91.4 0 34.2-13.3 66.3-37.5 90.5A127.3 127.3 0 0 1 612 612zM361.5 510.4c-.9-8.7-1.4-17.5-1.4-26.4 0-15.9 1.5-31.4 4.3-46.5.7-3.6-1.2-7.3-4.5-8.8-13.6-6.1-26.1-14.5-36.9-25.1a127.54 127.54 0 0 1-38.7-95.4c.9-32.1 13.8-62.6 36.3-85.6 24.7-25.3 57.9-39.1 93.2-38.7 31.9.3 62.7 12.6 86 34.4 7.9 7.4 14.7 15.6 20.4 24.4 2 3.1 5.9 4.4 9.3 3.2 17.6-6.1 36.2-10.4 55.3-12.4 5.6-.6 8.8-6.6 6.3-11.6-32.5-64.3-98.9-108.7-175.7-109.9-110.9-1.7-203.3 89.2-203.3 199.9 0 62.8 28.9 118.8 74.2 155.5-31.8 14.7-61.1 35-86.5 60.4-54.8 54.7-85.8 126.9-87.8 204a8 8 0 0 0 8 8.2h56.1c4.3 0 7.9-3.4 8-7.7 1.9-58 25.4-112.3 66.7-153.5 29.4-29.4 65.4-49.8 104.7-59.7 3.9-1 6.5-4.7 6-8.7z"
            />
          </svg>
        </small>
      </div>
      <div class="description-wrapper">
        <p>{{ description }}</p>
      </div>
      <ul class="about-wrapper flex">
        <li v-for="(tag, index) in aboutTags" :key="index">
          <small>{{ tag }}</small>
        </li>
      </ul>
      <ul class="links-wrapper flex">
        <li class="repo-link" v-if="repoLink">
          <a
            :href="repoLink"
            target="_blank"
            aria-label="view GitHub repository"
          >
            <!-- Uploaded to: SVG Repo, www.svgrepo.com, Generator: SVG Repo Mixer Tools -->
            <svg
              fill="currentColor"
              width="24px"
              height="24px"
              viewBox="0 0 1920 1920"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M1873.256 674.212c0-122.468-35.728-230.622-106.325-321.88 15.712-57.683 32.5-171.972-20.77-313.703-5.596-15.066-17.864-26.796-33.146-32.07-19.155-6.564-122.144-30.347-328.552 110.953-84.157-22.169-172.94-33.576-264.844-34.114-91.582.538-180.366 11.945-264.306 34.114C648.689-23.68 545.7-.005 526.437 6.56c-15.282 5.165-27.55 17.003-33.146 32.177-53.162 141.623-36.374 255.912-20.555 313.594-70.704 91.582-106.54 199.629-106.54 321.88 0 422.826 221.905 557.131 432.188 605.666-46.49 50.903-95.24 125.158-105.68 219.537-71.78 26.044-257.633 78.13-325.109-44.015-3.013-5.596-73.394-137.641-215.017-148.08-25.075 1.184-84.587 4.305-101.052 54.346-18.51 55.961 39.495 97.716 67.906 117.41.538.323 55.745 31.962 93.841 132.045.969 4.628 23.783 114.72 134.951 181.55 87.492 52.731 202.319 63.493 341.252 32.284 0 23.46-.323 48.212-.43 63.386l-.324 31.101H796.34l.215-29.81c1.937-161.532 2.045-164.653-30.778-181.656-12.484-6.457-27.012-7.964-40.356-3.659-136.243 41.002-246.98 40.033-320.052-2.798-70.488-41.54-85.985-108.908-88.89-119.67-3.875-10.653-8.072-20.662-12.269-30.24 126.987 145.713 372.138 77.161 463.289 33.792 18.833-8.825 30.778-27.765 30.778-48.535 0-149.372 148.295-244.182 149.802-245.15 19.371-12.16 28.949-35.19 23.998-57.36-4.95-22.276-23.352-39.065-46.06-41.755-223.626-26.796-452.204-109.338-452.204-518.388 0-106.325 33.577-198.983 99.76-275.175 12.915-15.067 16.681-36.052 9.579-54.562-9.793-25.397-36.482-112.782-.323-234.819 35.729 4.09 110.845 24.321 231.16 110.307 13.344 9.578 30.455 12.376 46.383 7.856 80.497-23.568 170.356-36.267 259.248-36.805 89.321.538 179.073 13.237 259.786 36.805 15.927 4.52 32.93 1.722 46.382-7.856 121.176-86.631 196.4-106.433 230.73-110.63 36.482 122.145 9.793 209.745 0 235.142-7.21 18.51-3.444 39.603 9.578 54.562 66.076 75.977 99.545 168.527 99.545 275.175 0 409.157-229.115 491.161-453.173 517.527-20.985 2.475-38.634 16.896-44.984 37.02-6.456 20.017-.538 42.078 15.067 56.284 6.35 5.703 14.958 12.483 25.074 20.231 51.333 39.28 137.211 105.034 137.211 259.571 0 85.448-1.399 354.273-1.399 354.273l107.617.539s1.399-269.257 1.399-354.812c0-141.838-56.499-229.976-110.845-285.937 210.39-48.427 431.65-182.517 431.65-604.696"
                fill-rule="evenodd"
              />
            </svg>
          </a>
        </li>

        <li class="live-site-link" v-if="liveLink">
          <a :href="liveLink" target="_blank" aria-label="view live site">
            <!-- Uploaded to: SVG Repo, www.svgrepo.com, Generator: SVG Repo Mixer Tools -->
            <svg
              width="24"
              height="24"
              viewBox="0 0 64 64"
              xmlns="http://www.w3.org/2000/svg"
              stroke-width="3"
              stroke="currentColor"
              fill="none"
            >
              <path
                d="M55.4 32v21.58a1.81 1.81 0 0 1-1.82 1.82H10.42a1.81 1.81 0 0 1-1.82-1.82V10.42a1.81 1.81 0 0 1 1.82-1.82H32M40.32 8.6H55.4v15.58M19.32 45.72 54.61 8.91"
              />
            </svg>
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  props: [
    "title",
    "tag",
    "description",
    "aboutTags",
    "liveLink",
    "repoLink",
    "img",
    "isCollab",
  ],
};
</script>

<style scoped>
.project__cards-item {
  padding: 0 var(--p-step-1);
  gap: 2rem;
}

.project__cards-item:not(:last-child) {
  margin-bottom: var(--m-step-1);
}

.project__cards-item:nth-child(even) {
  flex-direction: row-reverse;
}

.card-image {
  width: fit-content;
  height: fit-content;
}

.card-image img {
  box-shadow: var(--project-card-shadow);
}

.card-text {
  max-width: 33.75rem;
  width: 100%;
}

.title-wrapper {
  margin-top: 2rem;
  margin-bottom: var(--m-step--2);
}

.title-wrapper small.with-icon {
  gap: 0.625rem;
}

.description-wrapper {
  font-size: 1rem;
  margin-bottom: 1.875rem;
}

.about-wrapper {
  gap: 1.375rem;
  margin-bottom: 1rem;
}

.links-wrapper {
  gap: 0.5rem;
}

.links-wrapper li {
  position: relative;
  width: 2.5rem;
  height: 2.5rem;
  border-radius: 50px;
  overflow: hidden;
}

.links-wrapper li a {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding: 1.875rem;
  transition: all var(--transition-200);
}

.links-wrapper li a svg {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.links-wrapper li a:hover {
  background-color: var(--project-link-bg-color);
  color: var(--project-link-text-color);
}

@media (max-width: 960px) {
  .project__cards-item {
    flex-direction: column !important;
  }

  .card-image {
    margin: 0 auto;
  }

  .card-image img {
    max-width: 100%;
    height: auto;
  }

  .card-text {
    max-width: 100%;
  }
}

@media (max-width: 768px) {
  .project__cards-item {
    padding: 0;
    gap: 0;
  }

  .card-text {
    padding: 0 1rem;
  }
}

@media (max-width: 420px) {
  .title-wrapper {
    flex-direction: column;
    align-items: flex-start;
  }

  .title-wrapper h4 {
    margin-bottom: 0.375rem;
  }
}
</style>