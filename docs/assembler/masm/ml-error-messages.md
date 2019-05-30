---
title: ML Hata İletileri
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- vc.errors.ml
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
ms.openlocfilehash: adf2c509c3d8d9110ddb757f809a4bca9199df7a
ms.sourcegitcommit: af580f3a11b19d22288424eac7ceae1bc24ab312
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66355321"
---
# <a name="ml-error-messages"></a>ML Hata İletileri

MASM bileşenler tarafından oluşturulan hata iletileri üç kategoriye ayrılır:

- **Önemli hatalar.** Bu yardımcı programı, normal işlemini tamamlamasını engelleyen önemli bir sorun gösterir.

- **Önemli olmayan hataları.** Yardımcı programı, kendi işlemi tamamlanabilir. Aksi halde sonuç istediğinizi büyük olasılıkla değil.

- **Uyarılar.** Bu iletiler, istediğiniz sonuçları olmanızı engelleyebilir durumları gösterir.

Tüm hata iletilerini aşağıdaki biçiminde:

> *Yardımcı program*: *Filename* (*satırı*): {*Error_type*} (*kod*): *Message_text*

burada:

*yardımcı programı*<br/>
Hata iletisi gönderilen program.

*Dosya adı*<br/>
Hata oluşturmadan koşulu içeren dosya.

*Satır*<br/>
Hata koşulu bulunduğu yaklaşık satır.

*Error_type*<br/>
Önemli hata, hata veya uyarı.

*Kod*<br/>
Benzersiz 5 veya 6 basamaklı hata kodu.

*Message_text*<br/>
Hata koşulu kısa ve genel açıklaması.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Macro Assembler Başvurusu](../../assembler/masm/microsoft-macro-assembler-reference.md)
