---
description: 'Daha fazla bilgi edinin: C++ yerleşik işleçleri, önceliği ve ilişkilendirilebilirliği'
title: C++ yerleşik işleçleri, önceliği ve ilişkilendirilebilirlik
ms.date: 07/23/2020
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
ms.openlocfilehash: ff8ae84a62ef47449364d0815922326d7b8566d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253968"
---
# <a name="c-built-in-operators-precedence-and-associativity"></a>C++ yerleşik işleçleri, önceliği ve ilişkilendirilebilirlik

C++ dili tüm C işleçlerini içerir ve birkaç yeni işleç ekler. İşleçler, bir veya daha fazla işlenen üzerinde gerçekleştirilecek bir değerlendirme belirtir.

## <a name="precedence-and-associativity"></a>Öncelik ve ilişkisellik

İşleç *önceliği* , birden fazla işleç içeren ifadelerde işlem sırasını belirtir. İşleç *ilişkilendirilebilirliği* , aynı önceliğe sahip birden çok işleç içeren bir ifadede, bir işlenenin sol veya sağ taraftaki bir ile gruplanıp gruplandırılmadığını belirtir.

## <a name="alternative-spellings"></a>Alternatif yazımlar

C++, bazı işleçler için alternatif yazımlar belirler. C 'de alternatif yazımlar üst bilgide makrolar olarak sağlanır \<iso646.h> . C++ ' da, bu alternatifler anahtar kelimeleridir ve \<iso646.h> ya da c++ eşdeğeri kullanım \<ciso646> dışıdır. Microsoft C++ ' da, [`/permissive-`](../build/reference/permissive-standards-conformance.md) [`/Za`](../build/reference/za-ze-disable-language-extensions.md) Alternatif yazımların etkinleştirilmesi için veya derleyici seçeneği gereklidir.

## <a name="c-operator-precedence-and-associativity-table"></a>C++ işleç önceliği ve ilişkilendirilebilirlik tablosu

Aşağıdaki tablo C++ işleçlerinin önceliğini ve ilişkilendirilebilirliğini (en yüksekten en düşük öncelikliye) göstermektedir. Başka bir ilişki açıkça parantezlerle zorlanmadıkça aynı öncelik numarasına sahip işleçler eşit önceliğe sahiptir.

| İşleç Açıklaması | Operatör | Yapıyı |
|--|--|--|
| **Grup 1 önceliği, birleşim yok** |
| [Kapsam çözümlemesi](../cpp/scope-resolution-operator.md) | [`::`](../cpp/scope-resolution-operator.md) |
| **Grup 2 önceliği, soldan sağa ilişkilendirilebilirlik** |
| [Üye seçimi (nesne veya işaretçi)](../cpp/member-access-operators-dot-and.md) | [`.` veya `->`](../cpp/member-access-operators-dot-and.md) |
| [Dizi alt simgesi](../cpp/subscript-operator.md) | [`[]`](../cpp/subscript-operator.md) |
| [İşlev çağrısı](../cpp/function-call-operator-parens.md) | [`()`](../cpp/function-call-operator-parens.md) |
| [Sonek artışı](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md) | [`++`](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md) |
| [Sonek azaltma](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md) | [`--`](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md) |
| [Tür adı](../cpp/typeid-operator.md) | [`typeid`](../cpp/typeid-operator.md) |
| [Sabit tür dönüştürme](../cpp/const-cast-operator.md) | [`const_cast`](../cpp/const-cast-operator.md) |
| [Dinamik tür dönüştürme](../cpp/dynamic-cast-operator.md) | [`dynamic_cast`](../cpp/dynamic-cast-operator.md) |
| [Yeniden yorumlanan tür dönüştürmesi](../cpp/reinterpret-cast-operator.md) | [`reinterpret_cast`](../cpp/reinterpret-cast-operator.md) |
| [Statik tür dönüştürme](../cpp/static-cast-operator.md) | [`static_cast`](../cpp/static-cast-operator.md) |
| **Grup 3 önceliği, sağdan sola ilişkilendirilebilirliği** |
| [Nesnenin veya türün boyutu](../cpp/sizeof-operator.md) | [`sizeof`](../cpp/sizeof-operator.md) |
| [Önek artışı](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md) | [`++`](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md) |
| [Ön ek azaltma](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md) | [`--`](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md) |
| [Birinin tamamlayıcısı](../cpp/one-s-complement-operator-tilde.md) | [`~`](../cpp/one-s-complement-operator-tilde.md) | **`compl`** |
| [Mantıksal değil](../cpp/logical-negation-operator-exclpt.md) | [`!`](../cpp/logical-negation-operator-exclpt.md) | **`not`** |
| [Tekli olumsuzlama](../cpp/unary-plus-and-negation-operators-plus-and.md) | [`-`](../cpp/unary-plus-and-negation-operators-plus-and.md) |
| [Birli artı](../cpp/unary-plus-and-negation-operators-plus-and.md) | [`+`](../cpp/unary-plus-and-negation-operators-plus-and.md) |
| [Şunun adresi:](../cpp/address-of-operator-amp.md) | [`&`](../cpp/address-of-operator-amp.md) |
| [Yöneltme](../cpp/indirection-operator-star.md) | [`*`](../cpp/indirection-operator-star.md) |
| [Nesne oluştur](../cpp/new-operator-cpp.md) | [`new`](../cpp/new-operator-cpp.md) |
| [Nesneyi yok et](../cpp/delete-operator-cpp.md) | [`delete`](../cpp/delete-operator-cpp.md) |
| [Amaz](../cpp/cast-operator-parens.md) | [`()`](../cpp/cast-operator-parens.md) |
| **Grup 4 önceliği, soldan sağa ilişkilendirilebilirliği** |
| [Üye işaretçisi (nesneler veya işaretçiler)](../cpp/pointer-to-member-operators-dot-star-and-star.md) | [`.*` veya `->*`](../cpp/pointer-to-member-operators-dot-star-and-star.md) |
| **Grup 5 önceliği, soldan sağa ilişkilendirilebilirliği** |
| [Çarpma](../cpp/multiplicative-operators-and-the-modulus-operator.md) | [`*`](../cpp/multiplicative-operators-and-the-modulus-operator.md) |
| [Bölüm](../cpp/multiplicative-operators-and-the-modulus-operator.md) | [`/`](../cpp/multiplicative-operators-and-the-modulus-operator.md) |
| [Mod](../cpp/multiplicative-operators-and-the-modulus-operator.md) | [`%`](../cpp/multiplicative-operators-and-the-modulus-operator.md) |
| **Grup 6 önceliği, soldan sağa ilişkilendirilebilirlik** |
| [Toplama](../cpp/additive-operators-plus-and.md) | [`+`](../cpp/additive-operators-plus-and.md) |
| [Çıkarma](../cpp/additive-operators-plus-and.md) | [`-`](../cpp/additive-operators-plus-and.md) |
| **Grup 7 önceliği, soldan sağa ilişkilendirilebilirliği** |
| [Sola kaydırma](../cpp/left-shift-and-right-shift-operators-input-and-output.md) | [`<<`](../cpp/left-shift-and-right-shift-operators-input-and-output.md) |
| [Sağa kaydırma](../cpp/left-shift-and-right-shift-operators-input-and-output.md) | [`>>`](../cpp/left-shift-and-right-shift-operators-input-and-output.md) |
| **Grup 8 önceliği, soldan sağa ilişkilendirilebilirlik** |
| [Küçüktür](../cpp/relational-operators-equal-and-equal.md) | [`<`](../cpp/relational-operators-equal-and-equal.md) |
| [Büyüktür](../cpp/relational-operators-equal-and-equal.md) | [`>`](../cpp/relational-operators-equal-and-equal.md) |
| [Küçüktür veya eşittir](../cpp/relational-operators-equal-and-equal.md) | [`<=`](../cpp/relational-operators-equal-and-equal.md) |
| [Büyük veya eşittir](../cpp/relational-operators-equal-and-equal.md) | [`>=`](../cpp/relational-operators-equal-and-equal.md) |
| **Grup 9 önceliği, soldan sağa ilişkilendirilebilirliği** |
| [Eşitlik](../cpp/equality-operators-equal-equal-and-exclpt-equal.md) | [`==`](../cpp/equality-operators-equal-equal-and-exclpt-equal.md) |
| [Eşitsizlik](../cpp/equality-operators-equal-equal-and-exclpt-equal.md) | [`!=`](../cpp/equality-operators-equal-equal-and-exclpt-equal.md) | **`not_eq`** |
| **Grup 10 önceliği soldan sağa ilişkilendirilebilirliği** |
| [Bit düzeyinde AND](../cpp/bitwise-and-operator-amp.md) | [`&`](../cpp/bitwise-and-operator-amp.md) | **`bitand`** |
| **Grup 11 önceliği, soldan sağa ilişkilendirilebilirlik** |
| [Bit düzeyinde dışlamalı veya](../cpp/bitwise-exclusive-or-operator-hat.md) | [`^`](../cpp/bitwise-exclusive-or-operator-hat.md) | **`xor`** |
| **Grup 12 önceliği, soldan sağa ilişkilendirilebilirliği** |
| [Bit düzeyinde kapsamalı OR](../cpp/bitwise-inclusive-or-operator-pipe.md) | [`|`](../cpp/bitwise-inclusive-or-operator-pipe.md) | **`bitor`** |
| **Grup 13 önceliği, soldan sağa ilişkilendirilebilirliği** |
| [Mantıksal AND](../cpp/logical-and-operator-amp-amp.md) | [`&&`](../cpp/logical-and-operator-amp-amp.md) | **`and`** |
| **Grup 14 önceliği, soldan sağa ilişkilendirilebilirliği** |
| [Mantıksal OR](../cpp/logical-or-operator-pipe-pipe.md) | [`||`](../cpp/logical-or-operator-pipe-pipe.md) | **`or`** |
| **Grup 15 önceliği, sağdan sola ilişkilendirilebilirliği** |
| [Koşullu](../cpp/conditional-operator-q.md) | [`? :`](../cpp/conditional-operator-q.md) |
| **Grup 16 öncelik, sağdan sola ilişkilendirilebilirlik** |
| [Atama](../cpp/assignment-operators.md) | [`=`](../cpp/assignment-operators.md) |
| [Çarpma ataması](../cpp/assignment-operators.md) | [`*=`](../cpp/assignment-operators.md) |
| [Bölme ataması](../cpp/assignment-operators.md) | [`/=`](../cpp/assignment-operators.md) |
| [Mod ataması](../cpp/assignment-operators.md) | [`%=`](../cpp/assignment-operators.md) |
| [Toplama ataması](../cpp/assignment-operators.md) | [`+=`](../cpp/assignment-operators.md) |
| [Çıkarma ataması](../cpp/assignment-operators.md) | [`-=`](../cpp/assignment-operators.md) |
| [Sola kaydırma ataması](../cpp/assignment-operators.md) | [`<<=`](../cpp/assignment-operators.md) |
| [Sağa kaydırma ataması](../cpp/assignment-operators.md) | [`>>=`](../cpp/assignment-operators.md) |
| [Bit düzeyinde AND ataması](../cpp/assignment-operators.md) | [`&=`](../cpp/assignment-operators.md) | **`and_eq`** |
| [Bit düzeyinde kapsamalı OR ataması](../cpp/assignment-operators.md) | [`|=`](../cpp/assignment-operators.md) | **`or_eq`** |
| [Bit düzeyinde dışlamalı veya atama](../cpp/assignment-operators.md) | [`^=`](../cpp/assignment-operators.md) | **`xor_eq`** |
| **Grup 17 önceliği, sağdan sola ilişkilendirilebilirliği** |
| [throw ifadesi](../cpp/try-throw-and-catch-statements-cpp.md) | [`throw`](../cpp/try-throw-and-catch-statements-cpp.md) |
| **Grup 18 öncelik, soldan sağa ilişkilendirilebilirlik** |
| [Virgül](../cpp/comma-operator.md) | [,](../cpp/comma-operator.md) |

## <a name="see-also"></a>Ayrıca bkz.

[İşleç aşırı yüklemesi](operator-overloading.md)
