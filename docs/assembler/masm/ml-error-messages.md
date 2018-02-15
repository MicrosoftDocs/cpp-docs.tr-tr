---
title: ML hata iletileri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- vc.errors.ml
dev_langs:
- C++
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 09478bd3cff63e890014c6c14b11335feb8dfb3f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
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