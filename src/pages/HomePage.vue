<template>
  <div class="main-content">
    <div class="home">
      <div class="home-title-content">
        <div class="home-title">Buy SWTOR Items</div>
      </div>

      <div class="home-filter-content">
        <div class="flex-1">
          <v-select placeholder="Select a game" color="white" icon="joystick" />
        </div>
        <div class="flex-2">
          <v-input type="text" placeholder="Search" color="white" icon="search" />
        </div>
        <div class="flex-1">
          <div class="select-group">
            <v-select
              placeholder="Price"
              option="All"
              src="src/assets/icons/item-bag.svg"
            />
            <v-select
              placeholder="Item type"
              option="All"
              src="src/assets/icons/feather.svg"
            />
          </div>
        </div>
      </div>
      <div class="items-list">
        <div class="home-filter-order">
          <div class="summary">
            <span>Showing 15 from 125 </span>
          </div>
          <div>
            <v-select
              class="item-order"
              placeholder="Sort by"
              option="Featured"
              src="src/assets/icons/filter.svg"
            />
          </div>
        </div>
        <div class="items-list-grid">
          <ItemCard v-for="item in items" :key="item.id" :item="item" />
        </div>
        <div class="home-pagination">
          <v-button icon="chevron_left" :outline="true" />
          <v-button label="1" :primary="true" />
          <v-button label="2" />
          <v-button label="3" />
          <v-button label="..." />
          <v-button label="11" />
          <v-button icon="chevron_right" :outline="true" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import VSelect from '@/components/VSelect.vue';
import VInput from '@/components/VInput.vue';
import VButton from '@/components/VButton.vue';
import ItemCard from '@/components/ItemCard.vue';
import shopItems from '@/data/shop-items.json';

const items = ref(shopItems);
</script>

<style scoped>
.main-content {
  padding-bottom: 40px;
  padding-top: 30px;
  margin-top: 72px;
  position: relative;
}
.home {
  margin-left: auto;
  margin-right: auto;
  max-width: 640px;
}
.home-title {
  font-weight: 600;
  font-size: 40px;
  letter-spacing: 1.28px;
  padding: 0 20px;
  text-align: center;
}
.items-container {
  padding: 3rem 0;
  text-align: left;
}
.items-container h1 {
  font-size: 2.5rem;
  font-weight: 600;
  line-height: 1.5;
}
.items-list {
  border: 1px solid #4c6085;
  background-color: var(--color-background);
  border-radius: 5px;
  padding: 32px;
  width: 100%;
}
.items-list-grid {
  display: grid;
  gap: 20px;
  grid-template-columns: repeat(1, minmax(0, 1fr));
  max-width: 220px;
  margin: 0 auto;
  padding: 0px 0px 40px 0px;
}
.home-filter-content,
.home-filter-order {
  display: flex;
  gap: 1rem;
  margin: 1rem 0;
  flex-direction: column;
  padding: 20px;
}

.home-filter-order {
  flex-direction: row;
  justify-content: center;
  align-items: center;
  margin: 18px auto;
  padding: 0px;
}

.home-filter-order .summary {
  display: none;
}
.home-filter-content .flex-1 {
  flex: 1;
}
.home-filter-content .flex-2 {
  flex: 2;
}
.home-filter-content .flex-3 {
  flex: 3;
}

.select-group {
  display: flex;
}

.select-group > div {
  border-radius: 0px;
  border-right: 1px solid #4c6085;
  width: 100%;
  padding: 0px 4px 0px 0px;
}
.select-group > div:first-child {
  border-top-left-radius: 4px;
  border-bottom-left-radius: 4px;
}
.select-group > div:last-child {
  border-top-right-radius: 4px;
  border-bottom-right-radius: 4px;
  border-right: 0;
}
.home-pagination {
  display: flex;
  justify-content: center;
  gap: 5px;
}
.home-pagination a {
  color: #fff;
  font-size: 16px;
  height: 35px;
  width: 35px;
}
.item-order {
  width: 220px;
}

@media (min-width: 640px) {
  .items-list-grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
    max-width: calc(220px * 2 + 18px);
  }
  .home-filter-order .summary {
    display: block;
  }
  .home-filter-order {
    justify-content: space-between;
    width: calc(220px * 2 + 18px);
  }
}
@media (min-width: 768px) {
  .home {
    max-width: 768px;
  }
  .items-list-grid {
    grid-template-columns: repeat(3, minmax(0, 1fr));
    max-width: calc(220px * 3 + 18px * 2);
  }
  .home-pagination a {
    height: 40px;
    width: 40px;
  }
  .home-pagination {
    gap: 10px;
  }
  .home-filter-order {
    justify-content: space-between;
    width: calc(220px * 3 + 18px * 2);
  }
  .home-filter-order .summary {
    display: block;
  }
  .main-content {
    padding-bottom: 80px;
    padding-top: 110px;
    margin-top: 72px;
    position: relative;
  }
  .home-title {
    text-align: start;
  }
}
@media (min-width: 1024px) {
  .home {
    max-width: 1024px;
  }
  .items-list {
    padding: 50px;
  }
  .items-container {
    padding: 7rem 0;
  }
  .items-list-grid {
    grid-template-columns: repeat(4, minmax(0, 1fr));
    max-width: calc(220px * 4 + 18px * 3);
  }
  .home-filter-order {
    justify-content: space-between;
    width: calc(220px * 4 + 18px * 3);
  }
}
@media (min-width: 1280px) {
  .home {
    max-width: 1280px;
  }
  .home-filter-content {
    flex-direction: row;
    padding: 0px;
  }
  .items-list-grid {
    grid-template-columns: repeat(5, minmax(0, 1fr));
    max-width: calc(220px * 5 + 18px * 4);
  }
  .home-filter-order {
    justify-content: space-between;
    width: calc(220px * 5 + 16px * 4);
  }
  .home-title {
    padding: 0;
  }
}
</style>
