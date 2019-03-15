---
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
ms.openlocfilehash: b0e9a7514704742524f97e55c06ef47c7b36631b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823766"
---
# <a name="formatting-the-output-of-a-custom-build-step-or-build-event"></a>Özel Derleme Adımının veya Derleme Olayının Çıktısını Biçimlendirme

Özel derleme adımının veya derleme olayının çıktısını doğru biçimlendirilmişse, kullanıcılar aşağıdaki avantajlardan yararlanabilirsiniz:

- Uyarıları ve hataları sayılır **çıkış** penceresi.

- Çıktı görünür **görev listesi** penceresi.

- Çıktıda tıklayarak **çıkış** penceresi ilgili konuya görüntüler.

- F1 işlemleri etkinleştirilir **görev listesi** penceresi veya **çıkış** penceresi.

Çıkış biçiminde olması:

> {<em>filename</em>**(**<em>satırı #</em> \[ **,** <em>sütun #</em>]**)** &#124; *toolname*} **:** \[ <em>herhangi bir metin</em> ] {**hata** &#124;  **Uyarı**} <em>kod + sayı</em>**:**<em>yerelleştirilebilir dize</em> \[ <em>herhangi bir metin</em> ]

Konum:

- {*bir* &#124; *b*} bir seçimdir herhangi birinin *bir* veya *b*.

- \[<em>öğe</em>] bir isteğe bağlı dize veya parametre.

- **Kalın** bir sabit değer temsil eder.

Örneğin:

> C:\\*sourcefile.cpp*(134): hata C2143: söz dizimi hatası: eksik ';' önce '}'
>
> BAĞLANTI: LNK1104 önemli hatası: dosya açılamıyor '*somelib.lib*'

## <a name="see-also"></a>Ayrıca bkz.

[Özel Derleme Adımlarını ve Derleme Olaylarını Anlama](understanding-custom-build-steps-and-build-events.md)