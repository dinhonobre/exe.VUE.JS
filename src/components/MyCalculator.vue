<script>
export default {
  name: 'MyCalculator',  // Certifique-se de que está assim
    data() {
        return {
        input: '',
        buttons: ['7', '8', '9', '/', '4', '5', '6', '*', '1', '2', '3', '-', '0', '.', '=', '+'],
        };
    },
    methods: {
        handleButtonClick(button) {
        if (button === '=') {
            try {
            this.input = eval(this.input);
            } catch (error) {
            this.input = 'Erro';
            }
        } else {
            this.input += button;
        }
        },
    },
    };
</script>
