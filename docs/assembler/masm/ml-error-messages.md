---
title: ML hata iletileri | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- vc.errors.ml
dev_langs:
- C++
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 836daf438fa5a7f4c797b5b15ffab89720a7af98
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43675971"
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