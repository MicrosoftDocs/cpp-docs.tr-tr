---
title: C anahtar sözcükleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- keywords [C]
- redefining keywords
- Microsoft-specific keywords
ms.assetid: 2d932335-97bf-45cd-b367-4ae00db0ff42
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 80c1f0d4ac5d843732771281202612e31a4073c2
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860894"
---
# <a name="c-keywords"></a>C Anahtar Sözcükleri

"Anahtar sözcükler" C derleyicisi için özel anlamı olan sözcüklerdir. 7 ve 8. çeviri aşamalarında, tanımlayıcının yazımı ve büyük/küçük harf kullanımı C anahtar sözcüğüyle aynı olamaz. (Bir açıklamasını görmek [çeviri aşamaları](../preprocessor/phases-of-translation.md) içinde *önişlemci başvurusu*; tanımlayıcılarla ilgili bilgi için bkz: [tanımlayıcıları](../c-language/c-identifiers.md).) C dili, aşağıdaki anahtar sözcükleri kullanır:

|||||
|-|-|-|-|
|**auto**|**double**|**int**|**struct**|
|**break**|**else**|**long**|**switch**|
|**case**|**enum**|**Kaydolun**|**tür tanımı**|
|**char**|**extern**|**return**|**birleşim**|
|**const**|**float**|**short**|**İşaretsiz**|
|**continue**|**for**|**İmzalı**|**void**|
|**default**|**goto**|**sizeof**|**volatile**|
|**do**|**Eğer**|**static**|**while**|

Anahtar sözcükleri yeniden tanımlayamazsınız. Ancak, C kullanarak derlemeden önce anahtar sözcükler için değiştirilecek metni belirtebilirsiniz [önişlemci yönergeleri](../preprocessor/preprocessor-directives.md).

**Microsoft'a özgü**

ANSI C standardı, derleyici uygulamaları için başında iki alt çizgi olan tanımlayıcıların ayrılmasını sağlar. Bu nedenle, Microsoft kuralı Microsoft'a özgü anahtar sözcük adlarından önce iki alt çizgi koymaktır. Bu sözcükler tanımlayıcı adları kullanılamaz. Çift alt çizgi kullanımı gibi tanımlayıcıları ANSI açıklaması için adlandırma kuralları için bkz: [tanımlayıcıları](../c-language/c-identifiers.md).

Aşağıdaki anahtar sözcükler ve özel tanımlayıcılar, Microsoft C derleyicisi tarafından tanınmaktadır:

|||||
|-|-|-|-|
|**__asm**|**dllimport**<sup>2</sup>|**__int8**|**naked**<sup>2</sup>|
|**__based**<sup>1</sup>|**__except**|**__int16**|**__stdcall**|
|**__cdecl**|**__fastcall**|**__int32 türünün int**|**iş parçacığı**<sup>2</sup>|
|**__declspec**|**__finally**|**__int64**|**__try**|
|**dllexport**<sup>2</sup>|**__inline**|**__leave**||

<sup>1</sup> **__based** anahtar sözcüğü için sınırlı kullanımlara sahiptir 32-bit ve 64 bit hedef derlemeler.

<sup>2</sup> ile kullanıldığında özel tanımlayıcılardır bunlar **__declspec**; diğer bağlamlardaki kullanımları sınırlı değildir.

Microsoft uzantıları varsayılan olarak etkindir. Programlarınızın tamamen taşınabilir olmasını sağlamak için derleme sırasında /Za seçeneğini (ANSI uyumluluğu için derleme) belirterek Microsoft uzantılarını devre dışı bırakabilirsiniz. Bunu yaptığınızda, Microsoft'a özgü anahtar sözcükler devre dışı bırakıldı.

Microsoft uzantıları etkinleştirildiğinde, programlarınızda yukarıda listelenen anahtar sözcükleri kullanabilirsiniz. ANSI uyumluluğu için bu anahtar sözcüklerin çoğu çift alt çizgi ile başlar. Dört özel durum **dllexport**, **dllimport**, **naked**, ve **iş parçacığı**, yalnızca kullanılan **__declspec** ve bu nedenle başlarında çift alt çizgi gerektirmez. Geriye dönük uyumluluk için geriye kalan anahtar sözcüklerin tek alt çizgili biçimleri desteklenir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[C Öğeleri](../c-language/elements-of-c.md)
