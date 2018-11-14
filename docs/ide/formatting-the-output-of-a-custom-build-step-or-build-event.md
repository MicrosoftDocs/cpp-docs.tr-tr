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
ms.openlocfilehash: 333d3af92da2388b42f51f197dee5da82900022d
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51330417"
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

[Özel Derleme Adımlarını ve Derleme Olaylarını Anlama](../ide/understanding-custom-build-steps-and-build-events.md)