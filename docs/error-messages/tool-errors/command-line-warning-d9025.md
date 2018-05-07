---
title: Komut satırı uyarısı D9025 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9025
dev_langs:
- C++
helpviewer_keywords:
- D9025
ms.assetid: 6edff72c-1508-46c2-99f4-0e4b3c5e60c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3875a2cbd065fd5ad887267bcc80748fa9845d0d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="command-line-warning-d9025"></a>Komut Satırı Uyarısı D9025
'seçenek ' 1 'Seçenek2' ile geçersiz kılma  
  
 *Seçenek 1* seçeneği belirtildi, ancak ardından tarafından geçersiz kılınmış *Seçenek2*. *Seçenek2* seçeneği kullanıldı.  
  
 İki seçenek çelişkili ya da uyumsuz yönergeleri belirtirseniz, komut satırında sağa sağdan seçeneğinde zımni ya da belirtilen yönergesi kullanılır.  
  
 Bu uyarı geliştirme ortamından derlerken almak ve burada çakışan Seçenekler'ten gelen emin değilseniz, aşağıdakileri göz önünde bulundurun:  
  
-   Bir seçenek kodu veya bir projenin proje ayarları belirtilebilir. Derleyicinin bakarsanız [komut satırı özellik sayfaları](../../ide/command-line-property-pages.md) ve çakışan seçeneklerinde görürseniz **tüm seçenekleri** seçenekleri ayarlama seçenekleri projenin özellik sayfalarında, aksi takdirde, sonra alanı Kaynak kodu olarak ayarlanır.  
  
     Projenin özellik sayfalarında seçenekleri ayarlarsanız derleyicinin önişlemci özellik sayfasında (Çözüm Gezgini'nde Seçili proje düğümüne) arayın.  Var. ayarlayın, emin olmak için her kaynak kodu dosyasının (Çözüm Gezgini'nde) önişlemci özellik sayfası ayarlarını denetlemek seçeneği görmüyorsanız var. eklenmez.  
  
     Kodda seçenekleri ayarlarsanız kodu veya bir windows üstbilgileri ayarlayabilirsiniz.  Önceden işlenmiş bir dosya oluşturulurken deneyebilirsiniz ([/P](../../build/reference/p-preprocess-to-a-file.md)) ve simge için arama yapın.