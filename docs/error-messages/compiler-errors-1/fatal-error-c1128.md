---
title: "Önemli hata C1128 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1128
dev_langs: C++
helpviewer_keywords: C1128
ms.assetid: 6f9580fd-ecef-48be-9780-dcf666704279
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 83ec855a3280b1169ce3537ecf85944939449316
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1128"></a>Önemli hata C1128
bölüm sayısı nesne dosya biçimi sınırı aşıldı: / bigobj ile derleme  
  
 .Obj dosya izin verilen bölüm, bir COFF nesne dosya biçimi sınırlama sayısı aşıldı.  
  
 Bu bölümde sınırlama ulaşmasını kullanmanın sonucu olabilir [/Gy](../../build/reference/gy-enable-function-level-linking.md) ve hata ayıklama derlemesi; **/Gy** kendi comdat'ı bölümlere gitmek işlevleri neden olur. Bir hata ayıklama derlemesi her COMDAT işlevi için bir hata ayıklama bilgisi bölümü yoktur.  
  
 Çok fazla satır içi işlevler olduğunda C1128 da neden olabilir.  
  
 Bu hatayı düzeltmek için birden çok kaynak kodu dosyasına kaynak dosyanızı bölmek, olmadan derleme **/Gy**, veya ile derleme [bigobj (sayı, içinde. Obj dosyası)](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md).  İle derleme değil yaparsanız **/Gy**, en iyi duruma getirme ayrı ayrı belirtmeniz gerekecektir bu yana **O2** ve **/O1** her ikisi de kapsıyor **/Gy**.  
  
 Mümkünse, hata ayıklama bilgisi olmadan derleyin.  
  
 Ayrı bir kaynak kod dosyalarında şablonlarının belirli örneklemesi sahip gerekebilir yerine derleyici sahip, yayma bunları.  
  
 Kod bağlantı noktası oluşturma, C1128 büyük olasılıkla ilk x64 kullanılırken görünür derleyici ve daha sonra çok x86 ile derleyici. x64 derlenmiş her işlev ile ilişkili en az 4 bölüme sahip olacak **/Gy** veya satır içi şablonları veya satır içi sınıfı: kod, pdata ve bilgileri ve büyük olasılıkla xdata hata ayıklama.  X86 pdata olmayacaktır.