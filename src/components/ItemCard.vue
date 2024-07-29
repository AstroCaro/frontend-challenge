<template>
  <div class="item">
    <div class="item-header">
      <div class="item-badges">
        <div v-if="item.salePrice > 0" class="sale-badge">ON SALE</div>
        <div class="stock-badge" :class="{ 'no-stock': item.quantity <= 0 }">
          {{ item.quantity > 0 ? 'In stock' : 'No available' }}
        </div>
      </div>
      <div class="item-input">
        <v-input
          type="number"
          color="white"
          :default="item.defaultAmount"
          font-size="12px"
        />
      </div>
    </div>
    <div class="item-image">
      <img :src="item.imagePath" :alt="item.name" />
    </div>
    <div class="item-content">
      <div class="item-info">
        <div class="item-name">{{ item.name }}</div>
        <div class="item-price-content">
          <div v-if="item.salePrice > 0" class="item-sale">${{ item.salePrice }}</div>
          <div class="item-price" :class="{ sale: item.salePrice > 0 }">
            ${{ item.price }}
          </div>
        </div>
      </div>
      <div class="game-icon">
        <img src="../assets/games/swtor.png" alt="Game Logo" />
      </div>
    </div>
    <div class="item-description">
      {{ item.description }}
    </div>
    <div class="item-buttons">
      <v-button label="Details" :full="true" :secondary="true" />
      <v-button label="Add" :full="true" :primary="true" icon="shopping_cart" />
    </div>
  </div>
</template>
<script setup>
import VButton from './VButton.vue';
import VInput from './VInput.vue';
const props = defineProps(['item']);
const item = props.item;
</script>
<style scoped>
.item {
  background: rgba(76, 96, 133, 0.15) 0 0 no-repeat padding-box;
  border-radius: 5px;
  padding: 15px 20px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 220px;
  aspect-ratio: 1/1.5;
  margin: 0 auto;
}
.item-header,
.item-badges,
.item-info,
.item-price-content,
.item-buttons,
.item-content {
  display: flex;
  gap: 8px;
}
.item-header,
.item-content {
  justify-content: space-between;
}

.stock-badge {
  border: 1px solid #39e29d;
  color: #39e29d;
  padding: 8px 10px;
  font-size: 10px;
  font-weight: 200;
  border-radius: 3px;
  line-height: 0;
}

.stock-badge.no-stock {
  border-color: #4f4f4f;
  color: #888888;
}

.item-info {
  flex-direction: column;
}
.item-badges {
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-end;
}
.item-input .input-content {
  padding: 4px;
  max-width: 70px;
  min-height: 50px;
}

.item-input .input-content > input {
  font-size: 10px !important;
}
.item-description {
  font-size: 10px;
  font-weight: 200;
  line-height: 1.5;
  overflow: hidden;
  text-overflow: ellipsis;
  line-clamp: 2;
}
.item-name {
  font-size: 0.9rem;
}
.item-sale,
.item-price {
  font-weight: 500;
  font-size: 13px;
}
.item-price.sale {
  color: rgba(255, 255, 255, 0.5);
  text-decoration: line-through 1px solid red;
}
.item-image {
  width: 80px;
  height: 70px;
}
.item-image > img {
  width: auto;
  height: 70px;
}

.game-icon > img {
  vertical-align: middle;
  width: 30px;
  height: 25px;
  border: 1px solid #39e29d;
  border-radius: 15px;
  padding: 2px;
  object-fit: contain;
}

.cart-icon-container {
  background-color: rgba(0, 0, 0, 0.2);
  border-radius: 0.25rem;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0.3rem 0.4rem;
}

.sale-badge {
  font-size: 11px;
  text-transform: uppercase;
}
.sale-badge::before {
  content: '•';
  margin-right: 0.4rem;
  color: #39e29d;
  font-weight: 700;
}
</style>
