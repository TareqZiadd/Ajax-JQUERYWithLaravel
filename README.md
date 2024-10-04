# Ajax-JQUERYWithLaravel

create :




<script>
//

let formElement = document.getElementById('form-id'); // جميع عناصر النموذج الآن في هذا المتغير
let messageElement = document.getElementById('show-message');

// تصحيح اسم المتغير ليكون 'formElement' بدلًا من 'formVariable'
formElement.addEventListener('submit', function(e) {
    // يتم استدعاء هذه الدالة عند نقر المستخدم على زر الإرسال
    e.preventDefault();

    let input = document.querySelector('input[name="name"]');
    let token = document.querySelector('input[name="_token"]');

    // استخدام jQuery في هذا الجزء
    $.ajax({
        url: $(formElement).attr('action'), // يجلب URL الموجود في سمة "action" للنموذج
        method: "POST",  // يجب أن تكون POST بحروف كبيرة
        headers: {
            'X-CSRF-TOKEN': $(token).val(),
            'Accept': 'application/json',
            'Content-Type': 'application/json'
        },
        data: JSON.stringify({ name: $(input).val() }),  // تحويل البيانات إلى JSON
        success: function(data) {
            $(messageElement).removeClass('d-none');  // عرض الرسالة

            if (data.status) {
                $(messageElement).removeClass('alert-danger').addClass('alert-success');
                $(input).val('');  // إعادة تعيين الحقل إذا كانت الاستجابة ناجحة
            } else {
                $(messageElement).removeClass('alert-success').addClass('alert-danger');
            }

            $(messageElement).text(data.message);  // عرض الرسالة المستلمة
        }
    });
});
</script>

--------------------------------------------------------------------------------------------------------
بلجافا سكريبت العادية
----------------------------------------------------------------------------------------------------------

يمكنك استخدام classList لإضافة أو إزالة أو تبديل الفئات بسهولة. على سبيل المثال:
element.classList.add('class-name') لإضافة فئة.
element.classList.remove('class-name') لإزالة فئة.



لاحظ عند ' متغيرات



    let input = document.querySelector('input[name="name"]'); الانبوت
    let token = document.querySelector('input[name="_token"]');   التوكين اللي راجع

    let formElement = document.getElementById('form-id'); // جميع عناصر النموذج الآن في هذا المتغير
let messageElement = document.getElementById('show-message');  //رسالة الخطأ او الصح




