---
title: C anahtar sözcükleri | Microsoft Docs
ms.custom: ''
ms.date: 10/09/2018
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
ms.openlocfilehash: d9a5255609c3abb4846ce08a2163407eee6f240c
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161911"
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
|**__asm**<sup>3</sup>|**dllimport**<sup>2</sup>|**__int8**<sup>3</sup>|**naked**<sup>2</sup>|
|**__based**<sup>1, 3</sup>|**__except**<sup>3</sup>|**__int16**<sup>3</sup>|**__stdcall**<sup>3</sup>|
|**__cdecl**<sup>3</sup>|**__fastcall**|**__int32**<sup>3</sup>|**iş parçacığı**<sup>2</sup>|
|**__declspec**<sup>3</sup>|**__finally**<sup>3</sup>|**__int64**<sup>3</sup>|**__try**<sup>3</sup>|
|**dllexport**<sup>2</sup>|**__inline**<sup>3</sup>|**__leave**<sup>3</sup>||

<sup>1</sup> **__based** anahtar sözcüğü için sınırlı kullanımlara sahiptir 32-bit ve 64 bit hedef derlemeler.

<sup>2</sup> ile kullanıldığında özel tanımlayıcılardır bunlar **__declspec**; diğer bağlamlardaki kullanımları sınırlı değildir.

<sup>3</sup> Microsoft uzantıları etkinleştirildiğinde önceki sürümleriyle uyumluluk için bu anahtar sözcükler hem başında iki alt çizgi ve tek bir alt çizgi ile kullanılabilir.

Microsoft uzantıları varsayılan olarak etkindir. Programlarınızın tamamen taşınabilir olmasını sağlamak için Microsoft uzantıları belirterek devre dışı bırakabilirsiniz [/Za \(dil uzantılarını devre dışı bırak)](../build/reference/za-ze-disable-language-extensions.md) derleme sırasında seçeneği. Bunu yaptığınızda, bazı Microsoft'a özgü anahtar sözcükler devre dışı bırakıldı.

Microsoft uzantıları etkinleştirildiğinde, programlarınızda yukarıda listelenen anahtar sözcükleri kullanabilirsiniz. ANSI uyumluluğu için bu anahtar sözcüklerin çoğu çift alt çizgi ile başlar. Dört özel durum **dllexport**, **dllimport**, **naked**, ve **iş parçacığı**, yalnızca kullanılan **__declspec** ve bu nedenle başlarında çift alt çizgi gerektirmez. Geriye dönük uyumluluk için geriye kalan anahtar sözcüklerin tek alt çizgili biçimleri desteklenir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[C Öğeleri](../c-language/elements-of-c.md)
