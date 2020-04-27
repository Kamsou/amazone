<template>
  <main>
    <div class="container">
      <div class="col_1"></div>
      <div class="col_2">
        <div class="middle_time">
          <h2> Ajouter un nouveau poney</h2>
          <form>
            <!-- Category -->
            <div>
              <label> Catégorie </label>
              <div class="select">
                <select class="">
                  <option value="1">1</option>
                  <option value="2">2</option>
                </select>
                <div class="select_arrow"></div> 
              </div>
            </div>
            
            <!-- Owner -->
            <div>
              <label> Owner </label>
              <div class="select">
                <select>
                  <option value="3">3</option>
                  <option value="4">4</option>
                </select>
                <div class="select_arrow"></div> 
              </div> 
            </div>

            <!-- Title -->
            <div>
              <label>Nom</label>
              <input type="text"/>
            </div>

            <!-- Price -->
            <div>
              <label>Prix</label>
              <input type="number"/>
            </div>

            <!-- Description -->
            <div>
              <label>Description</label>
              <textarea placeholder="Description"></textarea>
            </div>

            <!-- Photo -->
            <div>
              <label>Ajouter une Photo</label>
              <div>
                <label for="">
                  <input type="file" />
                </label>
              </div>
            </div>

            <!-- Photo -->
            <a href="#" class="button_amazon">Ajouter</a>

          </form>
        </div>
      </div>
      <div class="col_3"></div>
    </div>
  </main>
</template>

<script>
  export default {
    
  }
</script>

<style lang="scss" scoped>
.container {
  display: flex;
}
.col_1, .col_3 {
  width: 20%;
}
.col_2 {
width: 60%;
  .middle_time {
    padding: 40px 0 60px 0;
    h2 {
      text-align: center;
    }
    div {
      padding: 10px 0 0 0;
    }
  }
  .select {
  position: relative;
  display: inline-block;
  margin-bottom: 15px;
  width: 100%;
  margin-top: 20px;

    select {
      display: inline-block;
      width: 100%;
      cursor: pointer;
      padding: 10px 15px;
      outline: 0;
      border: 0;
      border-radius: 0;
      background:  #f2f2f2;
      color: black;
      appearance: none;
      -webkit-appearance: none;
      -moz-appearance: none;
    }
    .select_arrow {
      position: absolute;
      top: 23px;
      right: 15px;
      width: 0;
      height: 0;
      pointer-events: none;
      border-style: solid;
      border-width: 8px 5px 0 5px;
      border-color:  #f2f2f2 transparent transparent transparent;
    }
  }
  input, textarea {
    width: 100%;
    outline: 0;
    background: #f2f2f2;
    width: 100%;
    border: 0;
    margin: 20px 0 15px 0;
    padding: 15px;
    box-sizing: border-box;
    font-size: 14px;
  }
}
.button_amazon {
    cursor: pointer;
    text-align: center;
    color: #111;
    box-sizing: border-box;
    display: block;
    position: relative;
    padding: .5rem 1rem;
    font-size: 1rem;
    border-radius: 4px;
    background: linear-gradient(to bottom,#f7dfa5,#f0c14b);
    box-shadow: 0 1px 0 rgba(255,255,255,.4) inset;
    border-color: #997a33;
    border-width: 1px;
    border-style: solid;
    text-decoration: none;
    font-weight: 400;
    &:hover {
      background-image: linear-gradient(#f5d78e,#eeb933);
    }
}
</style>