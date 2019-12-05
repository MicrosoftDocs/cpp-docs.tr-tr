---
title: ML Hata İletileri
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- vc.errors.ml
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
ms.openlocfilehash: 2db928d22219d33f89396bb29530680d4b3c8dba
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856949"
---
# <a name="ml-error-messages"></a>ML Hata İletileri

Mase bileşenleri tarafından oluşturulan hata iletileri üç kategoride yer ayrılır:

- **Önemli hatalar.** Bu, yardımcı programın normal sürecini tamamlamasını engelleyen ciddi bir sorun olduğunu gösterir.

- **Önemli olmayan hatalar.** Yardımcı programı işlemini tamamlayabilir. Varsa, bunun sonucu istediğiniz bir durum değildir.

- **Uyarılarına.** Bu iletiler istediğiniz sonuçları almanızı engelleyebilen koşulları gösterir.

Tüm hata iletileri aşağıdaki formu alır:

> *Yardımcı program*: *filename* (*satır*): {*Error_type*} (*kod*): *Message_text*

burada:

*Yardımcı program*\
Hata iletisini gönderen program.

*Dosya adı*\
Hata oluşturma koşulunu içeren dosya.

*Satır*\
Hata koşulunun varolduğu yaklaşık satır.

*Error_type*\
Önemli hata, hata veya uyarı.

*Kod*\
Benzersiz 5 veya 6 basamaklı hata kodu.

*Message_text*\
Hata koşulunun kısa ve genel bir açıklaması.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Macro Assembler başvurusu](../../assembler/masm/microsoft-macro-assembler-reference.md)
