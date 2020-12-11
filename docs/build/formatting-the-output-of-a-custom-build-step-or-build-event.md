---
description: 'Hakkında daha fazla bilgi edinin: özel derleme adımının veya derleme olayının çıktısını biçimlendirme'
title: Özel Derleme Adımının veya Derleme Olayının Çıktısını Biçimlendirme
ms.date: 08/27/2018
helpviewer_keywords:
- builds [C++], build events
- custom build steps [C++], output format
- events [C++], build
- build events [C++], output format
- build steps [C++], output format
- builds [C++], custom build steps
ms.assetid: 92ad3e38-24d7-4b89-90e6-5a16f5f998da
ms.openlocfilehash: c2631e3c6cbd8e66d88527ff75ff7bcac9869b4f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156430"
---
# <a name="formatting-the-output-of-a-custom-build-step-or-build-event"></a>Özel Derleme Adımının veya Derleme Olayının Çıktısını Biçimlendirme

Özel bir derleme adımının veya derleme olayının çıktısı doğru şekilde biçimlendirildiyse, kullanıcılar aşağıdaki avantajları alırlar:

- Uyarı ve hatalar **Çıkış** penceresinde sayılır.

- Çıktı **görev listesi** penceresinde görüntülenir.

- **Çıkış** penceresindeki çıktıya tıkladığınızda ilgili konu başlığı görüntülenir.

- F1 işlemleri **görev listesi** penceresinde veya **Çıkış** penceresinde etkinleştirilir.

Çıkışın biçimi şu olmalıdır:

> {<em>filename</em>**(**<em>satır #</em> \[ **,** <em>sütun #</em>]**)** &#124; *ToolName*} **:** \[ <em>herhangi bir metin</em> ] {**hata** &#124; **uyarısı**} <em>kod + numarası</em>**:**<em>yerelleştirilebilir dize</em> \[ <em>herhangi bir metin</em> ]

Konum:

- {*a* &#124; *b*}, *a* ya da *b* seçimdedir.

- \[<em>öğe</em>] isteğe bağlı bir dize veya parametredir.

- **Kalın** , bir sabit değeri temsil eder.

Örneğin:

> C: \\ *SourceFile. cpp*(134): hata C2143: sözdizimi hatası: '} ' öncesinde '; ' eksik
>
> BAĞLANTı: önemli hata LNK1104: '*SomeLib. lib*' dosyası açılamıyor

## <a name="see-also"></a>Ayrıca bkz.

[Özel Derleme Adımlarını ve Derleme Olaylarını Anlama](understanding-custom-build-steps-and-build-events.md)
