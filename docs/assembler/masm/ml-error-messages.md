---
title: ML hata iletileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: fbc2ae6388ad11a411850d03de421d2f6820fc03
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057103"
---
# <a name="ml-error-messages"></a>ML Hata İletileri
MASM bileşenleri tarafından oluşturulan hata iletileri üç kategoriye ayrılır:  
  
-   **Önemli hatalar.** Bu yardımcı program normal işleminin tamamlanmasını engelleyen ciddi bir sorunu işaret eder.  
  
-   **Önemli olmayan hataları.** Yardımcı program kendi işlemi tamamlanabilir. Aşması durumunda sonucu istediğinizi büyük olasılıkla değil.  
  
-   **Uyarılar.** Bu iletiler istediğiniz sonuçları alınırken engelleyebilir koşulları belirtin.  
  
 Tüm hata iletilerinin aşağıdaki biçimde alın:  
  
```  
  
Utility: Filename (Line) : [Error_type} (Code): Message_text  
```  
  
 burada:  
  
 `Utility`  
 Hata iletisi gönderilen program.  
  
 *Dosya adı*  
 Hata oluşturmadan koşulu içeren dosya.  
  
 *Satır*  
 Hata koşulu bulunduğu yaklaşık satır.  
  
 *Error_type*  
 Önemli hata, hata veya uyarı.  
  
 *Kod*  
 Benzersiz 5 veya 6 rakamlı hata kodu.  
  
 `Message_text`  
 Hata koşulu kısa ve genel açıklaması.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft Macro Assembler Başvurusu](../../assembler/masm/microsoft-macro-assembler-reference.md)