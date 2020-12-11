---
description: Microsoft 'a özgü değiştiriciler hakkında daha fazla bilgi edinin
title: Microsoft'a özgü değiştiriciler
ms.date: 08/16/2018
ms.assetid: 22c7178c-f854-47fa-9de6-07d23fda58e1
ms.openlocfilehash: dd82bf22da99e864a7b4898da1a99a12c3ad3de4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161630"
---
# <a name="microsoft-specific-modifiers"></a>Microsoft'a özgü değiştiriciler

Bu bölümde, aşağıdaki alanlarda C++ için Microsoft 'a özgü uzantılar açıklanmaktadır:

- [Temel adresleme](based-addressing.md), diğer işaretçilerin kaydırılacağı taban olarak bir işaretçi kullanma yöntemi

- [İşlev çağırma kuralları](calling-conventions.md)

- [__Declspec](declspec.md) anahtar sözcüğüyle tanımlanmış genişletilmiş depolama sınıfı öznitelikleri

- [__W64](w64.md) anahtar sözcüğü

## <a name="microsoft-specific-keywords"></a>Microsoft 'a özgü anahtar sözcükler

Microsoft 'a özgü birçok anahtar sözcük türetilmiş türler oluşturmak için bildirimcileri değiştirmek üzere kullanılabilir. Bildirimciler hakkında daha fazla bilgi için bkz. [bildiriciler](./declarations-and-definitions-cpp.md).

|Sözcükle|Anlamı|Türetilmiş türleri biçimlendirmek için kullanılır mi?|
|-------------|-------------|---------------------------------|
|[__based](based-grammar.md)|Aşağıdaki ad, bildirimde bulunan 32 bit tabanına 32 bitlik bir konum bildirir.|Evet|
|[__cdecl](cdecl.md)|Aşağıdaki ad, C adlandırma ve çağırma kurallarını kullanır.|Evet|
|[__declspec](declspec.md)|Aşağıdaki ad, Microsoft 'a özgü bir depolama sınıfı özniteliğini belirtir.|Hayır|
|[__fastcall](fastcall.md)|İzleyen ad, kullanılabilir olduğunda, bağımsız değişken geçirme yığını yerine kayıtları kullanan bir işlev bildirir.|Evet|
|[__restrict](extension-restrict.md)|__Declspec ([Restrict](restrict.md)) ile benzerdir, ancak değişkenlerde kullanım için.|Hayır|
|[__stdcall](stdcall.md)|Aşağıdaki ad, Standart çağırma kuralına uyan bir işlevi belirtir.|Evet|
|[__w64](w64.md)|Bir veri türünü 64 bit derleyicide daha büyük olarak işaretler.|Hayır|
|[__unaligned](unaligned.md)|Bir türe veya diğer verilere yönelik işaretçinin Hizalanmadığını belirtir.|Hayır|
|[__vectorcall](vectorcall.md)|Aşağıdaki ad, kullanılabilir olduğunda, bağımsız değişken geçirme yığını yerine, varsa, çağrı yapan bir işlevi bildirir.|Evet|

## <a name="see-also"></a>Ayrıca bkz.

[C++ dil başvurusu](cpp-language-reference.md)
