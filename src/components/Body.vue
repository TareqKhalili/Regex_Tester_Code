<template>


    <div class="inputArea">


        <div class="expression">
            <input type="text" @keyup="evaluate" placeholder="Expression" v-model="exp" id="exp">
            <input type="text" @keyup="evaluate" placeholder="Flags" v-model="flags" id="flags">
            <button class="save" @click="save">Save</button>
        </div>


        <input type="text" @keyup="evaluate" :placeholder="exp" v-model="text" id="text">


    </div>


    <div :class="['outputArea', exp == '' ? 'hide' : '' ]">


        <div v-for="res in result" :key="res.id">
            <div class="output">
                {{ res }}
            </div>
        </div>

        
    </div>
  
    
</template>

<script>
export default {
    name: "Body",


    props: ['savedExps', 'savedFlags'],


    data() {
        return {
            exp: "",
            flags: "",
            text: "Here is -some- 123 ex@ample text",
            result: "",
        }
    },


    methods: {
        evaluate() {
            let exp = new RegExp(this.exp, this.flags);
            this.result = exp.exec(this.text);
        },
        save() {
            localStorage.setItem(this.exp, this.flags);
            this.savedExps.push(this.exp);
            this.savedFlags.push(this.flags);
        },
    },


}
</script>

<style>

.inputArea {
    display: flex;
    flex-direction: column;
    width: 100%;    
    justify-content: center;
}


input {
    width: 70%;
    margin: 40px auto 0px;
    font-size: 20px;
    padding: 10px;
    outline: none;
    box-shadow: rgba(0, 0, 0, 0.16) 0px 3px 6px, rgba(0, 0, 0, 0.23) 0px 3px 6px;
    border: none;
    border-radius: 10px;
}


.expression {
    margin: 0 auto;
    display: flex;
    width: 80%;
    align-items: baseline;
}


.expression #exp {
    width: 70%;
}


.expression #flags {
    width: 20%;
    margin: 0px 5px;
}


.savedExpressions {
    width: 100%;
}


.savedExpressions table {
    margin: 15px auto 0px;
    width: 70%;
    box-shadow: rgba(0, 0, 0, 0.16) 0px 3px 6px, rgba(0, 0, 0, 0.23) 0px 3px 6px;
}


.savedExpressions td, .savedExpressions th {
    font-size: 20px;
}


.outputArea {
    display: flex;
    flex-wrap: wrap;
    width: 70%;
    height: auto;
    margin: 0 auto;
}


.output {    
    margin: 30px 10px 10px;
    padding: 15px;
    box-shadow: rgba(50, 50, 105, 0.15) 0px 2px 5px 0px, rgba(0, 0, 0, 0.05) 0px 1px 1px 0px;
}


.sheet {
    width: 100%;
    padding: 30px;
    display: flex;
    justify-content: center;
    transform: translateX(0%);
    transition: .3s;
}


table {
    margin: 20px 5px;
    width: 300px;
    border-collapse: collapse;
    transition: .3s;
}


td, tr, th {
    border: 1px solid rgba(0, 0, 0, 0.377);
    padding: 10px;
    font-size: 15px;
    letter-spacing: 2px;
    font-weight: bold;
}


.hidden {
    transform: translateX(-150%);
}


#viewSheet, .save {
    box-shadow: rgba(60, 64, 67, 0.3) 0px 1px 2px 0px, rgba(60, 64, 67, 0.15) 0px 1px 3px 1px;
    border: none;
    border-radius: 10px;
    background: rgba(20, 33, 61, 0.795);
    color: white;
    font-weight: 500;
    cursor: pointer;
    padding: 15px;
    margin: 20px;
    font-size: 20px;
    transition: .3s;
}


#viewSheet:hover, .save:hover {
    background: rgb(20,33,61);;
}


.save {
    margin: 30px 10px 10px;
    padding: 10px;

}


.hide {
    display: none;
}


</style>