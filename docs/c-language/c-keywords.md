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
ms.openlocfilehash: 98d815a8b0d185ccfb2ea89f653cd34d54fbd6ed
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32388246"
---
# <a name="c-keywords"></a>C Anahtar Sözcükleri
"Anahtar sözcükler" C derleyicisi için özel anlamı olan sözcüklerdir. 7 ve 8. çeviri aşamalarında, tanımlayıcının yazımı ve büyük/küçük harf kullanımı C anahtar sözcüğüyle aynı olamaz. (Bir açıklamasını görmek [çeviri aşamaları](../preprocessor/phases-of-translation.md) içinde *önişlemci başvurusu*; tanımlayıcıları hakkında bilgi için bkz: [tanımlayıcıları](../c-language/c-identifiers.md).) C dili, aşağıdaki anahtar sözcükleri kullanır:  
  
|||||  
|-|-|-|-|  
|**auto**|**double**|**int**|**struct**|  
|**break**|**else**|**long**|**switch**|  
|**Durumu**|**enum**|**Kaydetme**|**TypeDef**|  
|**char**|**extern**|**return**|**birleşim**|  
|**const**|**float**|**short**|**İmzasız**|  
|**continue**|**for**|**İmzalı**|**void**|  
|**default**|**goto**|**sizeof**|**volatile**|  
|**do**|**Eğer**|**static**|**while**|  
  
 Anahtar sözcükleri yeniden tanımlayamazsınız. Bununla birlikte, anahtar kelimeleri derleme önce C kullanarak atanması metin belirtebilirsiniz [önişlemci yönergeleri](../preprocessor/preprocessor-directives.md).  
  
 **Microsoft özel**  
  
 ANSI C standardı, derleyici uygulamaları için başında iki alt çizgi olan tanımlayıcıların ayrılmasını sağlar. Bu nedenle, Microsoft kuralı Microsoft'a özgü anahtar sözcük adlarından önce iki alt çizgi koymaktır. Bu sözcükleri tanımlayıcı adları olarak kullanılamaz. ANSI açıklaması için adlandırma kuralları için tanımlayıcıları çift alt çizgi, kullanımı dahil olmak üzere, bkz: [tanımlayıcıları](../c-language/c-identifiers.md).  
  
 Aşağıdaki anahtar sözcükler ve özel tanımlayıcılar, Microsoft C derleyicisi tarafından tanınmaktadır:  
  
|||||  
|-|-|-|-|  
|**__asm**|**dllimport**2|**__int8**|**naked**2|  
|**__based**1|**__except**|**__int16**|**__stdcall**|  
|**__cdecl**|**__fastcall**|**__int32**|**iş parçacığı**2|  
|**__declspec**|**__finally**|**__int64**|**__try**|  
|**dllexport**2|**__inline**|**__leave**||  
  
 1. **__Based** anahtar sözcüğü kullanan 32 bit ve 64 bit hedef derlemelerine sınırlı.  
  
 2. Bunlar birlikte kullanıldığında özel tanımlayıcılardır **__declspec**; kullanımlarını diğer bağlamlarda sınırlı değildir.  
  
 Microsoft uzantıları varsayılan olarak etkindir. Programlarınızın tamamen taşınabilir olmasını sağlamak için derleme sırasında /Za seçeneğini (ANSI uyumluluğu için derleme) belirterek Microsoft uzantılarını devre dışı bırakabilirsiniz. Bunu yaptığınızda, Microsoft'a özgü anahtar sözcükler devre dışı bırakılır.  
  
 Microsoft uzantıları etkinleştirildiğinde, programlarınızda yukarıda listelenen anahtar sözcükleri kullanabilirsiniz. ANSI uyumluluğu için bu anahtar sözcüklerin çoğu çift alt çizgi ile başlar. Dört özel durumları, **dllexport**, **dllimport**, **naked**, ve **iş parçacığı**, yalnızca kullanılan **__declspec** ve bu nedenle başında çift alt çizgi gerektirmez. Geriye dönük uyumluluk için geriye kalan anahtar sözcüklerin tek alt çizgili biçimleri desteklenir.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Öğeleri](../c-language/elements-of-c.md)