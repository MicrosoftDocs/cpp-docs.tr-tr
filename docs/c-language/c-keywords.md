---
title: C Anahtar Sözcükleri
ms.date: 10/09/2018
helpviewer_keywords:
- keywords [C]
- redefining keywords
- Microsoft-specific keywords
ms.assetid: 2d932335-97bf-45cd-b367-4ae00db0ff42
ms.openlocfilehash: e1364e0edacd94efa4ade6c6892a57d619635a39
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326800"
---
# <a name="c-keywords"></a>C Anahtar Sözcükleri

"Anahtar sözcükler" C derleyicisi için özel anlamı olan sözcüklerdir. 7 ve 8. çeviri aşamalarında, tanımlayıcının yazımı ve büyük/küçük harf kullanımı C anahtar sözcüğüyle aynı olamaz. (Ön *Işlemci başvurusunda* [Çeviri aşamaları](../preprocessor/phases-of-translation.md) açıklamasına bakın; tanımlayıcılar hakkında bilgi için bkz. [tanımlayıcılar](../c-language/c-identifiers.md).) C dili aşağıdaki anahtar sözcükleri kullanır:

|||||
|-|-|-|-|
|**Otomatik**|**double**|**int**|**sýný**|
|**break**|**else**|**long**|**değiştirebilirsiniz**|
|**harflerini**|**yardımının**|**kaydolunamadı**|** typedef**|
|**char**|**extern**|**return**|**birleşim**|
|**const**|**float**|**short**|**işaretlenmemiş**|
|**continue**|**for**|**imzalı**|**void**|
|**varsayılanını**|**goto**|**sizeof**|**volatile**|
|**do**|**if**|**static**|**while**|

Anahtar sözcükleri yeniden tanımlayamazsınız. Ancak, C [önişlemci yönergelerini](../preprocessor/preprocessor-directives.md)kullanarak derlemeden önce anahtar sözcüklerin yerine kullanılacak metni belirtebilirsiniz.

**Microsoft'a Özgü**

ANSI C standardı, derleyici uygulamaları için başında iki alt çizgi olan tanımlayıcıların ayrılmasını sağlar. Bu nedenle, Microsoft kuralı Microsoft'a özgü anahtar sözcük adlarından önce iki alt çizgi koymaktır. Bu sözcükler tanımlayıcı adı olarak kullanılamaz. Çift alt çizgilerin kullanımı dahil olmak üzere, adlandırma tanımlayıcıları için ANSI kurallarının açıklaması için bkz. [tanımlayıcılar](../c-language/c-identifiers.md).

Aşağıdaki anahtar sözcükler ve özel tanımlayıcılar, Microsoft C derleyicisi tarafından tanınmaktadır:

|||||
|-|-|-|-|
|**__asm**<sup>3</sup>|**dllimport**<sup>2</sup>|**__int8**<sup>3</sup>|**Naked**<sup>2</sup>|
|**__based**<sup>1, 3</sup>|**__except**<sup>3</sup>|**__int16**<sup>3</sup>|**__stdcall**<sup>3</sup>|
|**__cdecl**<sup>3</sup>|**__fastcall**|**__int32**<sup>3</sup>|**iş parçacığı**<sup>2</sup>|
|**__declspec**<sup>3</sup>|**__finally**<sup>3</sup>|**__int64**<sup>3</sup>|**__try**<sup>3</sup>|
|**dllexport**<sup>2</sup>|**__inline**<sup>3</sup>|**__leave**<sup>3</sup>||

<sup>1</sup> **__based** anahtar sözcüğü 32-bit ve 64-bit hedef derlemeler için sınırlı kullanımları vardır.

<sup>2</sup> **__declspec**ile kullanıldığında özel tanımlayıcılardır; diğer bağlamlarda kullanımları sınırlı değildir.

<sup>3</sup> önceki sürümlerle uyumluluk için, bu anahtar sözcükler hem iki önde gelen alt çizgi ile hem de Microsoft uzantıları etkinleştirildiğinde tek başına bir alt çizgi ile kullanılabilir.

Microsoft uzantıları varsayılan olarak etkinleştirilmiştir. Programlarınızın tamamen taşınabilir olduğundan emin olmak için, derleme sırasında [/za \(Disable Language Extensions](../build/reference/za-ze-disable-language-extensions.md) seçeneğini belirterek Microsoft uzantılarını devre dışı bırakabilirsiniz. Bunu yaptığınızda, Microsoft 'a özgü bazı anahtar sözcükler devre dışı bırakılır.

Microsoft uzantıları etkinleştirildiğinde, programlarınızda yukarıda listelenen anahtar sözcükleri kullanabilirsiniz. ANSI uyumluluğu için bu anahtar sözcüklerin çoğu çift alt çizgi ile başlar. Dört özel durum, **dllexport**, **dllimport**, **naked**ve **thread**yalnızca **__declspec** ile kullanılır ve bu nedenle, önde gelen çift alt çizgi gerektirmez. Geriye dönük uyumluluk için geriye kalan anahtar sözcüklerin tek alt çizgili biçimleri desteklenir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C Öğeleri](../c-language/elements-of-c.md)
