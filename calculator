// 1. Храним цены
let haircutPrice = 0;
let washPrice = 0;
let beardPrice = 0;

// 2. Функция пересчёта суммы
function updateTotal() {
    const total = haircutPrice + washPrice + beardPrice;
    document.getElementById('totalPrice').textContent = total + ' ₽';
}

// 3. Обработчик для СТРИЖКИ
document.querySelectorAll('input[name="haircut"]').forEach(radio => {
    radio.addEventListener('change', function(e) {
        haircutPrice = parseInt(e.target.value) || 0;
        updateRadioStyle();
        updateTotal();
    });
});

// 4. Обработчик для МЫТЬЯ ГОЛОВЫ
document.querySelectorAll('input[name="wash"]').forEach(radio => {
    radio.addEventListener('change', function(e) {
        washPrice = parseInt(e.target.value) || 0;
        updateRadioStyle();
        updateTotal();
    });
});

// 5. Обработчик для БОРОДЫ
document.querySelectorAll('input[name="beard"]').forEach(radio => {
    radio.addEventListener('change', function(e) {
        beardPrice = parseInt(e.target.value) || 0;
        updateRadioStyle();
        updateTotal();
    });
});

// 6. Функция для выделения выбранной радиокнопки
function updateRadioStyle() {
    document.querySelectorAll('.calc-radio-option').forEach(option => {
        const radio = option.querySelector('input[type="radio"]');
        if (radio.checked) {
            option.classList.add('selected');
        } else {
            option.classList.remove('selected');
        }
    });
}

// 7. КНОПКА СБРОСА
document.getElementById('resetButton').addEventListener('click', function() {
    // Сброс стрижки
    document.querySelector('input[name="haircut"][value="0"]').checked = true;
    haircutPrice = 0;
    
    // Сброс мытья
    document.querySelector('input[name="wash"][value="0"]').checked = true;
    washPrice = 0;
    
    // Сброс бороды
    document.querySelector('input[name="beard"][value="0"]').checked = true;
    beardPrice = 0;
    
    // Обновляем вид и сумму
    updateRadioStyle();
    updateTotal();
});

// 8. КНОПКА ЗАПИСИ
document.getElementById('bookButton').addEventListener('click', function() {
    const total = haircutPrice + washPrice + beardPrice;
    if (total === 0) {
        alert('Сначала выбери услуги!');
    } else {
        alert('Запись оформлена! Стоимость: ' + total + ' ₽');
    }
});

// 9. Запуск при загрузке страницы
window.onload = function() {
    updateRadioStyle();
    updateTotal();
};
