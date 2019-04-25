---
title: ML Hata İletileri
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- vc.errors.ml
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
ms.openlocfilehash: aa0440afae980e218c32ab3296bd7c6fb2b444d9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62202217"
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

[Microsoft Macro Assembler Başvurusu](../../assembler/masm/microsoft-macro-assembler-reference.md)<br/>