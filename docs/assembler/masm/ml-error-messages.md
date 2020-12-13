---
description: 'Daha fazla bilgi edinin: ML hata Iletileri'
title: ML Hata İletileri
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- vc.errors.ml
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
ms.openlocfilehash: 08f9a3ccd1bfe79195bf3ba9acf5b5347cc35a1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129707"
---
# <a name="ml-error-messages"></a>ML Hata İletileri

Mase bileşenleri tarafından oluşturulan hata iletileri üç kategoride yer ayrılır:

- **Önemli hatalar.** Bu, yardımcı programın normal sürecini tamamlamasını engelleyen ciddi bir sorun olduğunu gösterir.

- **Önemli olmayan hatalar.** Yardımcı programı işlemini tamamlayabilir. Varsa, bunun sonucu istediğiniz bir durum değildir.

- **Uyarılarına.** Bu iletiler istediğiniz sonuçları almanızı engelleyebilen koşulları gösterir.

Tüm hata iletileri aşağıdaki formu alır:

> *Yardımcı program*: *filename* (*satır*): {*Error_type*} (*kod*): *Message_text*

burada:

*Utility*\
Hata iletisini gönderen program.

*Kısaltın*\
Hata oluşturma koşulunu içeren dosya.

*Satırı*\
Hata koşulunun varolduğu yaklaşık satır.

*Error_type*\
Önemli hata, hata veya uyarı.

*Kodudur*\
Benzersiz 5 veya 6 basamaklı hata kodu.

*Message_text*\
Hata koşulunun kısa ve genel bir açıklaması.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Macro Assembler başvurusu](microsoft-macro-assembler-reference.md)
