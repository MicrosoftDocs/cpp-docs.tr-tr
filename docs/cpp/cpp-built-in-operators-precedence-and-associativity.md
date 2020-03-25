---
title: C++Yerleşik Işleçler, öncelik ve Ilişkilendirilebilirlik
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
ms.openlocfilehash: 36e7ce77e24366be10b75f5bb4f8830363594301
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180413"
---
# <a name="c-built-in-operators-precedence-and-associativity"></a>C++Yerleşik Işleçler, öncelik ve Ilişkilendirilebilirlik

C++ dili tüm C işleçlerini içerir ve birkaç yeni işleç ekler. İşleçler, bir veya daha fazla işlenen üzerinde gerçekleştirilecek bir değerlendirme belirtir.

İşleç *önceliği* , birden fazla işleç içeren ifadelerde işlem sırasını belirtir. İşleç *ilişkilendirilebilirliği* , aynı önceliğe sahip birden çok işleç içeren bir ifadede, bir işlenenin sol veya sağ taraftaki bir ile gruplanıp gruplandırılmadığını belirtir. Aşağıdaki tablo C++ işleçlerinin önceliğini ve ilişkilendirilebilirliğini (en yüksekten en düşük öncelikliye) göstermektedir. Başka bir ilişki açıkça parantezlerle zorlanmadıkça aynı öncelik numarasına sahip işleçler eşit önceliğe sahiptir.

### <a name="c-operator-precedence-and-associativity"></a>C++ İşleç Önceliği ve İlişkilendirilebilirliği

|İşleç Açıklaması|İşleç|
|--------------------------|--------------|
|**Grup 1 önceliği, birleşim yok**|
|[Kapsam çözümleme](../cpp/scope-resolution-operator.md)|[::](../cpp/scope-resolution-operator.md)|
|**Grup 2 önceliği, soldan sağa ilişkilendirilebilirlik**|
|[Üye seçimi (nesne veya işaretçi)](../cpp/member-access-operators-dot-and.md)|[. veya->](../cpp/member-access-operators-dot-and.md)|
|[Dizi indisi](../cpp/subscript-operator.md)|[&#91;&#93;](../cpp/subscript-operator.md)|
|[İşlev çağrısı](../cpp/function-call-operator-parens.md)|[()](../cpp/function-call-operator-parens.md)|
|[Sonek artışı](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|[++](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Sonek azaltma](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|[--](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Tür adı](../cpp/typeid-operator.md)|[typeid](../cpp/typeid-operator.md)|
|[Sabit tür dönüştürme](../cpp/const-cast-operator.md)|[const_cast](../cpp/const-cast-operator.md)|
|[Dinamik tür dönüştürme](../cpp/dynamic-cast-operator.md)|[dynamic_cast](../cpp/dynamic-cast-operator.md)|
|[Yeniden yorumlanan tür dönüştürmesi](../cpp/reinterpret-cast-operator.md)|[reinterpret_cast](../cpp/reinterpret-cast-operator.md)|
|[Statik tür dönüştürme](../cpp/static-cast-operator.md)|[static_cast](../cpp/static-cast-operator.md)|
|**Grup 3 önceliği, sağdan sola ilişkilendirilebilirliği**|
|[Nesnenin veya türün boyutu](../cpp/sizeof-operator.md)|[sizeof](../cpp/sizeof-operator.md)|
|[Önek artışı](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|[++](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Ön ek azaltma](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|[--](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Birinin tamamlayıcısı](../cpp/one-s-complement-operator-tilde.md)|[~](../cpp/one-s-complement-operator-tilde.md)|
|[Mantıksal değil](../cpp/logical-negation-operator-exclpt.md)|[!](../cpp/logical-negation-operator-exclpt.md)|
|[Birli olumsuzlama](../cpp/unary-plus-and-negation-operators-plus-and.md)|[-](../cpp/unary-plus-and-negation-operators-plus-and.md)|
|[Birli artı](../cpp/unary-plus-and-negation-operators-plus-and.md)|[+](../cpp/unary-plus-and-negation-operators-plus-and.md)|
|[Adres-/](../cpp/address-of-operator-amp.md)|[&amp;](../cpp/address-of-operator-amp.md)|
|[Yöneltme](../cpp/indirection-operator-star.md)|[&#42;](../cpp/indirection-operator-star.md)|
|[Nesne oluştur](../cpp/new-operator-cpp.md)|[new](../cpp/new-operator-cpp.md)|
|[Nesneyi yok et](../cpp/delete-operator-cpp.md)|[sil](../cpp/delete-operator-cpp.md)|
|[Amaz](../cpp/cast-operator-parens.md)|[()](../cpp/cast-operator-parens.md)|
|**Grup 4 önceliği, soldan sağa ilişkilendirilebilirliği**|
|[Üye işaretçisi (nesneler veya işaretçiler)](../cpp/pointer-to-member-operators-dot-star-and-star.md)|[. &#42; veya->&#42;](../cpp/pointer-to-member-operators-dot-star-and-star.md)|
|**Grup 5 önceliği, soldan sağa ilişkilendirilebilirliği**|
|[Anda](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[&#42;](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[Bölmenin](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[/](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[Matematiksel](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[%](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|**Grup 6 önceliği, soldan sağa ilişkilendirilebilirlik**|
|[Ek olarak](../cpp/additive-operators-plus-and.md)|[+](../cpp/additive-operators-plus-and.md)|
|[StrA](../cpp/additive-operators-plus-and.md)|[-](../cpp/additive-operators-plus-and.md)|
|**Grup 7 önceliği, soldan sağa ilişkilendirilebilirliği**|
|[Sola kaydırma](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[<<](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|[Sağa kaydırma](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[>>](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|**Grup 8 önceliği, soldan sağa ilişkilendirilebilirlik**|
|[Küçüktür](../cpp/relational-operators-equal-and-equal.md)|[<](../cpp/relational-operators-equal-and-equal.md)|
|[Şundan büyüktür](../cpp/relational-operators-equal-and-equal.md)|[>](../cpp/relational-operators-equal-and-equal.md)|
|[Küçüktür veya eşittir](../cpp/relational-operators-equal-and-equal.md)|[<=](../cpp/relational-operators-equal-and-equal.md)|
|[Büyük veya eşittir](../cpp/relational-operators-equal-and-equal.md)|[>=](../cpp/relational-operators-equal-and-equal.md)|
|**Grup 9 önceliği, soldan sağa ilişkilendirilebilirliği**|
|[Eþit](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[==](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|[Olmama](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[!=](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|**Grup 10 önceliği soldan sağa ilişkilendirilebilirliği**|
|[Bit düzeyinde AND](../cpp/bitwise-and-operator-amp.md)|[&amp;](../cpp/bitwise-and-operator-amp.md)|
|**Grup 11 önceliği, soldan sağa ilişkilendirilebilirlik**|
|[Bit düzeyinde dışlamalı veya](../cpp/bitwise-exclusive-or-operator-hat.md)|[^](../cpp/bitwise-exclusive-or-operator-hat.md)|
|**Grup 12 önceliği, soldan sağa ilişkilendirilebilirliği**|
|[Bit düzeyinde kapsamlı veya](../cpp/bitwise-inclusive-or-operator-pipe.md)|[&#124;](../cpp/bitwise-inclusive-or-operator-pipe.md)|
|**Grup 13 önceliği, soldan sağa ilişkilendirilebilirliği**|
|[Mantıksal AND](../cpp/logical-and-operator-amp-amp.md)|[&amp;&amp;](../cpp/logical-and-operator-amp-amp.md)|
|**Grup 14 önceliği, soldan sağa ilişkilendirilebilirliği**|
|[Mantıksal OR](../cpp/logical-or-operator-pipe-pipe.md)|[&#124;&#124;](../cpp/logical-or-operator-pipe-pipe.md)|
|**Grup 15 önceliği, sağdan sola ilişkilendirilebilirliği**|
|[Oluştur](../cpp/conditional-operator-q.md)|[? :](../cpp/conditional-operator-q.md)|
|**Grup 16 öncelik, sağdan sola ilişkilendirilebilirlik**|
|[Atama](../cpp/assignment-operators.md)|[=](../cpp/assignment-operators.md)|
|[Çarpma ataması](../cpp/assignment-operators.md)|[&#42;=](../cpp/assignment-operators.md)|
|[Bölüm atama](../cpp/assignment-operators.md)|[/=](../cpp/assignment-operators.md)|
|[Mod ataması](../cpp/assignment-operators.md)|[%=](../cpp/assignment-operators.md)|
|[Toplama ataması](../cpp/assignment-operators.md)|[+=](../cpp/assignment-operators.md)|
|[Çıkarma ataması](../cpp/assignment-operators.md)|[-=](../cpp/assignment-operators.md)|
|[Sola kaydırma ataması](../cpp/assignment-operators.md)|[<<=](../cpp/assignment-operators.md)|
|[Sağa kaydırma ataması](../cpp/assignment-operators.md)|[>>=](../cpp/assignment-operators.md)|
|[Bit düzeyinde AND ataması](../cpp/assignment-operators.md)|[&amp;=](../cpp/assignment-operators.md)|
|[Bit düzeyinde kapsamlı veya atama](../cpp/assignment-operators.md)|[&#124;=](../cpp/assignment-operators.md)|
|[Bit düzeyinde dışlamalı veya atama](../cpp/assignment-operators.md)|[^=](../cpp/assignment-operators.md)|
|**Grup 17 önceliği, sağdan sola ilişkilendirilebilirliği**|
|[throw ifadesi](../cpp/try-throw-and-catch-statements-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)|
|**Grup 18 öncelik, soldan sağa ilişkilendirilebilirlik**|
|[Virgülle](../cpp/comma-operator.md)|[,](../cpp/comma-operator.md)|

## <a name="see-also"></a>Ayrıca bkz.

[İşleç Aşırı Yüklemesi](operator-overloading.md)
