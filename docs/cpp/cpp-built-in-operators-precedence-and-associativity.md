---
title: "C++ yerleşik işleçleri, öncelik ve birleşim | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 95cbb68740fe43fa8a76624abb57284cb68e7805
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="c-built-in-operators-precedence-and-associativity"></a>C++ yerleşik işleçleri, öncelik ve birleşim

C++ dili tüm C işleçlerini içerir ve birkaç yeni işleç ekler. İşleçler, bir veya daha fazla işlenen üzerinde gerçekleştirilecek bir değerlendirme belirtir.

İşleç *öncelik* birden fazla işleci içeren ifadelerde işlemlerin sırasını belirtir. İşleç *birleşim* , sol taraftaki bir ya da bir alt köşedeki ile işleneni aynı önceliğe sahip birden çok işleç içeren bir ifadede gruplandırılmış olup olmadığını belirtir. Aşağıdaki tablo C++ işleçlerinin önceliğini ve ilişkilendirilebilirliğini (en yüksekten en düşük öncelikliye) göstermektedir. Başka bir ilişki açıkça parantezlerle zorlanmadıkça aynı öncelik numarasına sahip işleçler eşit önceliğe sahiptir.

### <a name="c-operator-precedence-and-associativity"></a>C++ İşleç Önceliği ve İlişkilendirilebilirliği

|İşleç Açıklaması|İşleç|
|--------------------------|--------------|
|**Grup 1 önceliği, hiçbir birleşim**|
|[Kapsam çözümü](../cpp/scope-resolution-operator.md)|[::](../cpp/scope-resolution-operator.md)|
|**Sağ birleşim sol Grup 2 önceliği**|
|[Üye seçimi (nesne veya işaretçi)](../cpp/member-access-operators-dot-and.md)|[. ya da ->](../cpp/member-access-operators-dot-and.md)|
|[Dizi alt simge](../cpp/subscript-operator.md)|[&#91;&#93;](../cpp/subscript-operator.md)|
|[İşlev çağrısı](../cpp/function-call-operator-parens.md)|[()](../cpp/function-call-operator-parens.md)|
|[Sonek arttırma](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|[++](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Sonek azaltma](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|[--](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Tür adı](../cpp/typeid-operator.md)|[TypeId](../cpp/typeid-operator.md)|
|[Sabit tür dönüştürmeleri](../cpp/const-cast-operator.md)|[const_cast](../cpp/const-cast-operator.md)|
|[Dinamik tür dönüştürmeleri](../cpp/dynamic-cast-operator.md)|[dynamic_cast](../cpp/dynamic-cast-operator.md)|
|[Reinterpreted tür dönüştürmeleri](../cpp/reinterpret-cast-operator.md)|[reinterpret_cast](../cpp/reinterpret-cast-operator.md)|
|[Statik tür dönüştürmeleri](../cpp/static-cast-operator.md)|[static_cast](../cpp/static-cast-operator.md)|
|**Sağdan sola birleşim Grup 3 önceliği**|
|[Nesne veya türü boyutu](../cpp/sizeof-operator.md)|[sizeof](../cpp/sizeof-operator.md)|
|[Önek artırma](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|[++](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Önek azaltma](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|[--](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)|
|[Birinin tamamlama](../cpp/one-s-complement-operator-tilde.md)|[~](../cpp/one-s-complement-operator-tilde.md)|
|[Mantıksal değil](../cpp/logical-negation-operator-exclpt.md)|[!](../cpp/logical-negation-operator-exclpt.md)|
|[Tekli değilleme](../cpp/unary-plus-and-negation-operators-plus-and.md)|[-](../cpp/unary-plus-and-negation-operators-plus-and.md)|
|[Birli artı](../cpp/unary-plus-and-negation-operators-plus-and.md)|[+](../cpp/unary-plus-and-negation-operators-plus-and.md)|
|[Adres](../cpp/address-of-operator-amp.md)|[&amp;](../cpp/address-of-operator-amp.md)|
|[Yöneltme](../cpp/indirection-operator-star.md)|[&#42;](../cpp/indirection-operator-star.md)|
|[Nesne oluşturma](../cpp/new-operator-cpp.md)|[new](../cpp/new-operator-cpp.md)|
|[Nesne yok](../cpp/delete-operator-cpp.md)|[delete](../cpp/delete-operator-cpp.md)|
|[Atama](../cpp/cast-operator-parens.md)|[()](../cpp/cast-operator-parens.md)|
|**Sağ birleşim sol Grup 4 önceliği**|
|[İşaretçi-üye (nesneleri veya işaretçileri)](../cpp/pointer-to-member-operators-dot-star-and-star.md)|[. &#42; ya da -> &#42;](../cpp/pointer-to-member-operators-dot-star-and-star.md)|
|**Sağ birleşim sol Grup 5 önceliği**|
|[Çarpma](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[&#42;](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[Bölme](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[/](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|[Modulus](../cpp/multiplicative-operators-and-the-modulus-operator.md)|[%](../cpp/multiplicative-operators-and-the-modulus-operator.md)|
|**Sağ birleşim sol Grup 6 önceliği**|
|[Toplama](../cpp/additive-operators-plus-and.md)|[+](../cpp/additive-operators-plus-and.md)|
|[Çıkarma](../cpp/additive-operators-plus-and.md)|[-](../cpp/additive-operators-plus-and.md)|
|**Sağ birleşim sol Grup 7 önceliği**|
|[Sola kaydırma](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[<<](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|[Sağa kaydırma](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|[>>](../cpp/left-shift-and-right-shift-operators-input-and-output.md)|
|**Sağ birleşim sol Grup 8 önceliği**|
|[Küçüktür](../cpp/relational-operators-equal-and-equal.md)|[<](../cpp/relational-operators-equal-and-equal.md)|
|[Büyüktür](../cpp/relational-operators-equal-and-equal.md)|[>](../cpp/relational-operators-equal-and-equal.md)|
|[Küçük veya eşit](../cpp/relational-operators-equal-and-equal.md)|[<=](../cpp/relational-operators-equal-and-equal.md)|
|[Büyüktür veya eşittir](../cpp/relational-operators-equal-and-equal.md)|[>=](../cpp/relational-operators-equal-and-equal.md)|
|**Sağ birleşim sol Grup 9 önceliği**|
|[Eşitlik](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[==](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|[Eşitsizlik](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|[!=](../cpp/equality-operators-equal-equal-and-exclpt-equal.md)|
|**Sağ birleşim sol Grup 10 önceliği**|
|[Bit düzeyinde AND](../cpp/bitwise-and-operator-amp.md)|[&amp;](../cpp/bitwise-and-operator-amp.md)|
|**Sağ birleşim sol Grup 11 önceliği**|
|[Bit düzeyinde XOR](../cpp/bitwise-exclusive-or-operator-hat.md)|[^](../cpp/bitwise-exclusive-or-operator-hat.md)|
|**Sağ birleşim sol Grup 12 önceliği**|
|[Bit düzeyinde kapsamlı OR](../cpp/bitwise-inclusive-or-operator-pipe.md)|[&#124;](../cpp/bitwise-inclusive-or-operator-pipe.md)|
|**Sağ birleşim sol Grup 13 önceliği**|
|[Mantıksal AND](../cpp/logical-and-operator-amp-amp.md)|[&amp;&amp;](../cpp/logical-and-operator-amp-amp.md)|
|**Sağ birleşim sol Grup 14 önceliği**|
|[Mantıksal OR](../cpp/logical-or-operator-pipe-pipe.md)|[&#124;&#124;](../cpp/logical-or-operator-pipe-pipe.md)|
|**Sağdan sola birleşim Grup 15 önceliği**|
|[Koşullu](../cpp/conditional-operator-q.md)|[? :](../cpp/conditional-operator-q.md)|
|**Sağdan sola birleşim Grup 16 önceliği**|
|[Atama](../cpp/assignment-operators.md)|[=](../cpp/assignment-operators.md)|
|[Çarpma atama](../cpp/assignment-operators.md)|[&#42;=](../cpp/assignment-operators.md)|
|[Bölme atama](../cpp/assignment-operators.md)|[/=](../cpp/assignment-operators.md)|
|[Mod atama](../cpp/assignment-operators.md)|[%=](../cpp/assignment-operators.md)|
|[Toplama atama](../cpp/assignment-operators.md)|[+=](../cpp/assignment-operators.md)|
|[Çıkarma ataması](../cpp/assignment-operators.md)|[-=](../cpp/assignment-operators.md)|
|[Sola kaydırma ataması](../cpp/assignment-operators.md)|[<<=](../cpp/assignment-operators.md)|
|[Sağa kaydırma ataması](../cpp/assignment-operators.md)|[>>=](../cpp/assignment-operators.md)|
|[Bit düzeyinde AND atama](../cpp/assignment-operators.md)|[&amp;=](../cpp/assignment-operators.md)|
|[Bit düzeyinde kapsamlı OR ataması](../cpp/assignment-operators.md)|[&#124;=](../cpp/assignment-operators.md)|
|[Bit düzeyinde özel OR ataması](../cpp/assignment-operators.md)|[^=](../cpp/assignment-operators.md)|
|**Sağdan sola birleşim Grup 17 önceliği**|
|[throw deyimi](../cpp/try-throw-and-catch-statements-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)|
|**Sağ birleşim sol Grup 18 önceliği**|
|[Virgül](../cpp/comma-operator.md)|[,](../cpp/comma-operator.md)|

## <a name="see-also"></a>Ayrıca Bkz.

[İşleç Aşırı Yüklemesi](operator-overloading.md)


