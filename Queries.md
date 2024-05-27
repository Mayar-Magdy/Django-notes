
## Reverse Relations

Django provides a way to access related objects in a reverse direction. When you define a ForeignKey in a model, Django automatically creates a reverse relationship. By default, this reverse relation is named using the model name followed by `_set`.

```python
b.entry_set.all()  # Returns all Entry objects related to Blog.
```

في Django، لما بتعملي علاقة بين موديلين باستخدام ForeignKey، Django بيخلقلك طريقة تقدري توصلي بيها للأوبجكتس المرتبطة بالاتجاه العكسي. ده بيسمى reverse relation. يعني لو عندك موديل اسمه Blog وموديل تاني اسمه Entry وفيه ForeignKey لـ Blog، Django بيخلقلك طريقة تقدري تجيبي بيها كل الـ Entry اللي مرتبطة بـ Blog معين.

هنا `b` ده مثال لأوبجكت من نوع Blog. و `entry_set` ده الاسم الافتراضي اللي Django بيديه للـ reverse relation. الـ `_set` ده بيتضاف لاسم الموديل اللي عنده الـ ForeignKey. ولما تستخدمي `b.entry_set.all()`، ده بيجيبلك كل الـ Entry اللي مرتبطة بالـ Blog اللي `b` ده بيمثله.

يعني ببساطة، الـ reverse relation ده بيسمحلك تجيبي البيانات من الجهة التانية للعلاقة. فبدل ما تروحي لـ Entry وتسأليه عن الـ Blog بتاعه، أنتِ بتروحي لـ Blog وتسأليه عن كل الـ Entry المرتبطة به.

