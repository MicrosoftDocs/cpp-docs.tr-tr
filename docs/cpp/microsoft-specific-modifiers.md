---
title: Microsoft'a özgü değiştiriciler
ms.date: 08/16/2018
ms.assetid: 22c7178c-f854-47fa-9de6-07d23fda58e1
ms.openlocfilehash: 2d65c0fe99895949d537ccf4368df2add3ff91ad
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857430"
---
# <a name="microsoft-specific-modifiers"></a>Microsoft'a özgü değiştiriciler

Bu bölüm, aşağıdaki alanlarda Microsoft'a özel C++ uzantılarını açıklar:

- [Temel adresleme](based-addressing.md), diğer işaretçilerin kaydırılacağı taban olarak bir işaretçi kullanma yöntemi

- [İşlev çağırma kuralları](calling-conventions.md)

- [__Declspec](declspec.md) anahtar sözcüğüyle tanımlanmış genişletilmiş depolama sınıfı öznitelikleri

- [__W64](w64.md) anahtar sözcüğü

## <a name="microsoft-specific-keywords"></a>Microsoft'a özgü anahtar sözcükler

Microsoft'a özgü anahtar sözcüklerin çoğu, bildirimcileri türetilmiş türler biçimlendirecek şekilde değiştirmek için kullanılabilir. Bildirimciler hakkında daha fazla bilgi için bkz. [bildiriciler](overview-of-declarators.md).

|Anahtar sözcüğü|Açıklama|Türetilmiş Türler Oluşturmak için kullanılır?|
|-------------|-------------|---------------------------------|
|[__based](based-grammar.md)|İzleyen ad, bildirimdeki 32-bit tabana ilişkin bir 32-bit uzaklığı bildirir.|Evet|
|[__cdecl](cdecl.md)|İzleyen ad, C adlandırma ve çağırma kurallarını kullanır.|Evet|
|[__declspec](declspec.md)|İzleyen ad, Microsoft'a özgü bir depolama sınıfı özniteliğini belirtir.|Hayır|
|[__fastcall](fastcall.md)|İzleyen ad, kullanılabilir olduğunda, bağımsız değişken geçirme yığını yerine kayıtları kullanan bir işlev bildirir.|Evet|
|[__restrict](extension-restrict.md)|__Declspec ([Restrict](restrict.md)) ile benzerdir, ancak değişkenlerde kullanım için.|Hayır|
|[__stdcall](stdcall.md)|İzleyen ad, standart çağırma kuralına uyan bir işlevi belirtir.|Evet|
|[__w64](w64.md)|Bir veri türünü 64 bit derleyicide daha büyük olarak işaretler.|Hayır|
|[__unaligned](unaligned.md)|Bir tür veya başka veriler için bir işaretçinin hizalanmadığını belirtir.|Hayır|
|[__vectorcall](vectorcall.md)|İzleyen ad, kullanılabilir olduğunda, bağımsız değişken geçirme yığını yerine SSE kayıtları da dahil olmak üzere kayıtları kullanan bir işlev bildirir.|Evet|

## <a name="see-also"></a>Ayrıca bkz.

[C++ Dil Başvurusu](cpp-language-reference.md)
