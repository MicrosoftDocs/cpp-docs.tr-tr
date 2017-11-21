---
title: "Bağlayıcı araçları hatası LNK1201 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1201
dev_langs: C++
helpviewer_keywords: LNK1201
ms.assetid: 64c3f496-a428-4b54-981e-faa82ef9c8a1
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 344f56eb3097bad447d9a0b12a0c5aac6f68b119
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1201"></a>Bağlayıcı Araçları Hatası LNK1201
Program veritabanı için 'filename'; yazılırken hata oluştu yetersiz disk alanı, geçersiz bir yol veya yetersiz ayrıcalık olup olmadığını denetleyin  
  
 BAĞLANTI, çıktı dosyası için program veritabanı (PDB) dosyasına yazılamadı.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Dosya bozuk olabilir. Yeniden bağlama ve PDB dosya silin.  
  
2.  Dosyayı yazmak için yeterli disk alanı yok.  
  
3.  Sürücü büyük olasılıkla bir ağ sorunu nedeniyle kullanılabilir değil.  
  
4.  Hata ayıklayıcı bağlantı oluşturmaya çalıştığınız programın etkin değil.  
  
5.  Yığın alanı kalmadı.  Bkz: [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) daha fazla bilgi için.