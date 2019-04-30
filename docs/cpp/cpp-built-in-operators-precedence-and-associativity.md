---
title: C++ yerleşik işleçler, öncelik ve İlişkisellik
ms.date: 11/04/2016
helpviewer_keywords:
- operators (C++), hierarchy
- operator precedence
- precedence, operators
- operators (C++), associativity
- multiple operators [C++]
- associativity of operators [C++]
- operators [C++], precedence
- evaluation order
- hierarchy, operator
ms.assetid: 95c1f0ba-dad8-4034-b039-f79a904f112f
ms.openlocfilehash: 0b560913deb57393a8547f0831e0d987eed41ab7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392355"
---
# <a name="c-built-in-operators-precedence-and-associativity"></a>C++ yerleşik işleçler, öncelik ve İlişkisellik

C++ dili tüm C işleçlerini içerir ve birkaç yeni işleç ekler. İşleçler, bir veya daha fazla işlenen üzerinde gerçekleştirilecek bir değerlendirme belirtir.

İşleç *öncelik* birden çok işleç içeren ifadeler işlemlerin sırasını belirtir. İşleç *ilişkilendirilebilirliği* solundakiyle veya sağındakiyle bir bir işlenen aynı önceliğe sahip birden çok işleç içeren bir ifadede gruplandırılır olup olmadığını belirtir. Aşağıdaki tablo C++ işleçlerinin önceliğini ve ilişkilendirilebilirliğini (en yüksekten en düşük öncelikliye) göstermektedir. Başka bir ilişki açıkça parantezlerle zorlanmadıkça aynı öncelik numarasına sahip işleçler eşit önceliğe sahiptir.

### <a name="c-operator-precedence-and-associativity"></a>C++ İşleç Önceliği ve İlişkilendirilebilirliği

|İşleç Açıklaması|İşleç|
|--------------------------|--------------|
|**Grup 1 önceliği, hiçbir ilişkiselliği**|
|[Kapsam çözümü](../cpp/scope-resolution-operator.md)|[::](../cpp/scope-resolution-operator.md)|
|**Grup 2 önceliği, soldan sağa ilişkilendirilebilirlik için**|
|[Üye seçimi (nesne veya işaretçi)](../cpp/member-access-operators-dot-and.md)|[. veya ->](../cpp/member-access-operators-dot-and.md)|
|[Dizi alt simgesi](../cpp/subscript-operator.md)|[&#91;&#93;](../cpp/subscript-operator.md)|
|[İşlev çağrısı](../cpp/function-call-operator-parens.md)|[()](../cpp/function-call-operator-parens.md)|
|[Sonek artırma](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|[++](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Son ek azaltma](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|[--](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Tür adı](../cpp/typeid-operator.md)|[typeid](../cpp/typeid-operator.md)|
|[Sabit tür dönüştürmesi](../cpp/const-cast-operator.md)|[const_cast](../cpp/const-cast-operator.md)|
|[Dinamik tür dönüştürmesi](../cpp/dynamic-cast-operator.md)|[dynamic_cast](../cpp/dynamic-cast-operator.md)|
|[Yeniden yorumlanan tür dönüştürmesi](../cpp/reinterpret-cast-operator.md)|[reinterpret_cast](../cpp/reinterpret-cast-operator.md)|
|[Statik tür dönüştürmesi](../cpp/static-cast-operator.md)|[static_cast](../cpp/static-cast-operator.md)|
|**Sağdan sola birleşme Grup 3 önceliği**|
|[Nesnenin veya türün boyutu](../cpp/sizeof-operator.md)|[sizeof](../cpp/sizeof-operator.md)|
|[Önek artırma](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|[++](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Önek azaltma](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|[--](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Birinin tamamlayıcısı](../cpp/one-s-complement-operator-tilde.md)|[~](../cpp/one-s-complement-operator-tilde.md)|
|[Mantıksal değil](../cpp/logical-negation-operator-exclpt.md)|[\!](../cpp/logical-negation-operator-exclpt.md)|
|[Tekli olumsuzlama](../cpp/unary-plus-and-negation-operators-plus-and.md)|[-](../cpp/unary-plus-and-negation-operators-plus-and.md)|
|[Tekli artı](../cpp/unary-plus-and-negation-operators-plus-and.md)|[+](../cpp/unary-plus-and-negation-operators-plus-and.md)|
|[Adres](../cpp/address-of-operator-amp.md)|[&amp;](../cpp/address-of-operator-amp.md)|
|[Yöneltme](../cpp/indirection-operator-star.md)|[&#42;](../cpp/indirection-operator-star.md)|
|[Nesne oluşturma](../cpp/new-operator-cpp.md)|[new](../cpp/new-operator-cpp.md)|
|[Nesne yok et](../cpp/delete-operator-cpp.md)|[delete](../cpp/delete-operator-cpp.md)|
|[Tür dönüştürme](../cpp/cast-operator-parens.md)|[()](../cpp/cast-operator-parens.md)|
|**Soldan sağa ilişkilendirilebilirlik için Grup 4 önceliği**|
|[İşaretçi-üye (nesneler veya işaretçiler)](../cpp/pointer-to-member-operators-dot-star-and-star.md)|[. &#42; veya ->&#42;](../cpp/pointer-to-member-operators-dot-star-and-star.md)|
|**Grup 5 önceliği, soldan sağa ilişkilendirilebilirlik için**|
|[Çarpma](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[&#42;](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[Bölme](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[/](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[mod](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[%](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|**Grup 6 önceliği, soldan sağa ilişkilendirilebilirlik için**|
|[Toplama](../cpp/additive-operators-plus-and.md)|[+](../cpp/additive-operators-plus-and.md)|
|[Çıkarma](../cpp/additive-operators-plus-and.md)|[-](../cpp/additive-operators-plus-and.md)|
|**Soldan sağa ilişkilendirilebilirlik için Grup 7 öncelik**|
|[Sola kaydırma](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[<<](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|[Sağa kaydırma](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[>>](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|**Grup 8 önceliği, soldan sağa ilişkilendirilebilirlik için**|
|[Küçüktür](../cpp/relational-operators-equal-and-equal.md)|[<](../cpp/relational-operators-equal-and-equal.md)|
|[Büyüktür](../cpp/relational-operators-equal-and-equal.md)|[>](../cpp/relational-operators-equal-and-equal.md)|
|[Küçük veya eşittir](../cpp/relational-operators-equal-and-equal.md)|[<=](../cpp/relational-operators-equal-and-equal.md)|
|[Büyüktür veya eşittir](../cpp/relational-operators-equal-and-equal.md)|[>=](../cpp/relational-operators-equal-and-equal.md)|
|**Grup 9 önceliği, soldan sağa ilişkilendirilebilirlik için**|
|[Eşitlik](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[==](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|[Eşitsizlik](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[\!=](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|**Soldan sağa ilişkilendirilebilirlik için Grup 10 önceliği**|
|[Bit düzeyinde AND](../cpp/bitwise-and-operator-amp.md)|[&amp;](../cpp/bitwise-and-operator-amp.md)|
|**Grup 11 önceliği, soldan sağa ilişkilendirilebilirlik için**|
|[Bit düzeyinde dışlamalı OR](../cpp/bitwise-exclusive-or-operator-hat.md)|[^](../cpp/bitwise-exclusive-or-operator-hat.md)|
|**Grup 12 önceliği, soldan sağa ilişkilendirilebilirlik için**|
|[Bit düzeyinde kapsamalı OR](../cpp/bitwise-inclusive-or-operator-pipe.md)|[&#124;](../cpp/bitwise-inclusive-or-operator-pipe.md)|
|**Grup 13 önceliği, soldan sağa ilişkilendirilebilirlik için**|
|[Mantıksal AND](../cpp/logical-and-operator-amp-amp.md)|[&amp;&amp;](../cpp/logical-and-operator-amp-amp.md)|
|**Soldan sağa ilişkilendirilebilirlik için Grup 14 önceliği**|
|[Mantıksal OR](../cpp/logical-or-operator-pipe-pipe.md)|[&#124;&#124;](../cpp/logical-or-operator-pipe-pipe.md)|
|**Sağdan sola birleşme grubu 15 önceliği**|
|[Koşullu](../cpp/conditional-operator-q.md)|[? :](../cpp/conditional-operator-q.md)|
|**Sağdan sola birleşme grubu 16 önceliği**|
|[Atama](../cpp/assignment-operators.md)|[=](../cpp/assignment-operators.md)|
|[Çarpma ataması](../cpp/assignment-operators.md)|[&#42;=](../cpp/assignment-operators.md)|
|[Bölme ataması](../cpp/assignment-operators.md)|[/=](../cpp/assignment-operators.md)|
|[Modulus atama](../cpp/assignment-operators.md)|[%=](../cpp/assignment-operators.md)|
|[Toplama ataması](../cpp/assignment-operators.md)|[+=](../cpp/assignment-operators.md)|
|[Çıkarma ataması](../cpp/assignment-operators.md)|[-=](../cpp/assignment-operators.md)|
|[Sola kaydırma ataması](../cpp/assignment-operators.md)|[<<=](../cpp/assignment-operators.md)|
|[Sağa kaydırma ataması](../cpp/assignment-operators.md)|[>>=](../cpp/assignment-operators.md)|
|[Bit düzeyinde AND ataması](../cpp/assignment-operators.md)|[&amp;=](../cpp/assignment-operators.md)|
|[Bit düzeyinde kapsamalı OR ataması](../cpp/assignment-operators.md)|[&#124;=](../cpp/assignment-operators.md)|
|[Bit düzeyinde dışlamalı OR ataması](../cpp/assignment-operators.md)|[^=](../cpp/assignment-operators.md)|
|**Sağdan sola birleşme grubu 17 önceliği**|
|[throw ifadesi](../cpp/try-throw-and-catch-statements-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)|
|**Grup 18 önceliği, soldan sağa ilişkilendirilebilirlik için**|
|[Virgül](../cpp/comma-operator.md)|[,](../cpp/comma-operator.md)|

## <a name="see-also"></a>Ayrıca bkz.

[İşleç Aşırı Yüklemesi](operator-overloading.md)