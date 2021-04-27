<template>
    <div class="container">
        <textarea
            v-model="inputMessage"
            class="inputMessage"
            maxlength="160"
        />
        <div class="buttons-group">
            <h2>Convert to</h2>
            <div class="convert-btn" @click="convertToBasicLeet">
                Basic L33t
            </div>
            <div class="convert-btn" @click="convertToAdvancedLeet">
                Advanced L33t
            </div>
        </div>
        <div class="outputMessage">
            {{ outputMessage }}
        </div>
    </div>
</template>

<script>
    import * as dictionary from '@/leet-dictionary'
    export default {
        name: 'MessageConverter',
        data() {
            return {
                inputMessage: '',
                outputMessage: ''
            }
        },
        methods: {
            convertToBasicLeet() {
                this.outputMessage = ''
                let lettersArray = this.inputMessage.toLowerCase().split('')
                lettersArray.map(letter => {
                    if (dictionary.alphabetBasic.hasOwnProperty(letter)) {
                        this.outputMessage += dictionary.alphabetBasic[letter]
                    } else {
                        this.outputMessage += letter
                    }
                })
            },
            convertToAdvancedLeet() {
                this.outputMessage = ''
                let lettersArray = this.inputMessage.split('')
                lettersArray.map(letter => {
                    if (dictionary.alphabetAdvanced.hasOwnProperty(letter)) {
                        this.outputMessage += dictionary.alphabetAdvanced[letter]
                    } else {
                        this.outputMessage += letter
                    }
                })
            },
            getAllLetterVars(target) {
                const letterVars = dictionary[target]
                const randomNumber = Math.floor(Math.random() * letterVars.length)
                return letterVars[randomNumber]
            }
        }
    }
</script>

<style scoped>
.container {
    display: flex;
}
.inputMessage,
.outputMessage {
	width: 475px;
	resize: none;
	height: 300px;
	font-size: 1.5rem;
	padding: 1rem;
}
.inputMessage {
	border: 1px solid #407076;
}
.outputMessage {
	background-color: #c1cad6;
	color: #407076;
}
.buttons-group {
	padding: 1rem 0;
	display: flex;
    flex-direction: column;
    align-items: center;
}
.convert-btn {
	font-size: 1.2rem;
    font-weight: 600;
	padding: 0.5rem 1rem;
    margin: 0 1rem;
	background-color: #dde1e4;
	color: #407076;
	border: none;
	border-radius: 10px;
	cursor: pointer;
    text-align: center;
	transition: all 0.15s ease-in-out;
}
.convert-btn + .convert-btn {
    margin-top: 1rem;
}
.convert-btn:hover {
	background-color: #bdbfc0;
}
.convert-btn:active {
	transform: scale(0.9);
}
</style>
