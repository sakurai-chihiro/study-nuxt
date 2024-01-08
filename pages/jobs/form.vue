<template>
  <h2>入力フォーム</h2>
  <div id="addForm" class="p-addForm">
    <input type="checkbox">
    <label for="checkbox1">追加入力項目を表示する</label>
  </div>
  
  <div id="formArea" class="p-formArea">
    <form class="c-form p-form">
      <dl class="c-form__list p-form__list">
        <div class="c-form__item p-form__name">
          <dt class="c-form__title">
            <label class="c-form__label" for="lastName">お名前（姓）<span class="c-required">必須</span></label>
          </dt>
          <dd class="c-form__desc">
            <input class="c-form__input" type="text" id="lastName"  name="lastName">
          </dd>
        </div>
        <div class="c-form__item p-form__name">
          <dt class="c-form__title">
            <label class="c-form__label" for="firstName">お名前（名）<span class="c-required">必須</span></label>
          </dt>
          <dd class="c-form__desc">
            <input class="c-form__input" type="text" id="firstName" name="firstName">
          </dd>
        </div>
        <div class="c-form__item">
          <dt class="c-form__title">
            <label class="c-form__label" for="tell">電話番号</label>
          </dt>
          <dd class="c-form__desc">
            <input class="c-form__input" type="text" id="tell" name="tell">
          </dd>
        </div>
        <div class="c-form__item">
          <dt class="c-form__title">
            <label class="c-form__label" for="email">メールアドレス<span class="c-required">必須</span></label>
          </dt>
          <dd class="c-form__desc">
            <input class="c-form__input" type="text" id="email" name="email">
          </dd>
        </div>
      </dl>
    </form>

    
  </div>
</template>

<style scoped lang="scss">
/* reset */
* {
  box-sizing: border-box;
}
dd {
  margin: 0px;
}

/* component */
.c-form {
  margin-top: 32px;
  padding: 32px;
  background-color: #eee;
  &__list {
    display: flex;
    flex-wrap: wrap;
  }
  &__input {
    width: 100%;
    padding: 10px;
  }
  &__item {
    position: relative;
    display: block;
    width: 100%;
    margin-bottom: 16px;
  }
  &__title {
    position: absolute;
    top: 50%;
    left: 1em;
    transform: translateY(-50%);
  }
}
.c-required {
  color: red;
  font-weight: bold;
  &::before {
    content: "*";
  }
}

/* pages */
.p-addForm {
  max-width: 650px;
  margin: 0 auto;
}
.p-form{
  &__list {
    max-width: 650px;
    margin: 0 auto;
  }
  &__name {
    width: 47%;
  }
  &__name + &__name {
    margin-left: 6%;
  }
}
</style>