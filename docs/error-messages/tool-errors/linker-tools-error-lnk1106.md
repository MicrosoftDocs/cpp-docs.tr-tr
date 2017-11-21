---
title: "Bağlayıcı araçları hatası LNK1106 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1106
dev_langs: C++
helpviewer_keywords: LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b97196ebed51c21e40fa74ab1b80d23f3c49eec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1106"></a>Bağlayıcı Araçları Hatası LNK1106
Geçersiz dosya veya disk dolu: konuma arama yapılamaz  
  
 Aracı değil okuma veya yazma `location` bellekle eşlenen dosyasında.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Disk dolu.  
  
     Biraz alan boşaltın ve yeniden bağlayın.  
  
2.  Bir ağ üzerinden bağlamak çalışıyor.  
  
     Bazı ağlar bağlayıcı tarafından kullanılan bellek eşlemeli dosyalar tam olarak desteklemez. Yerel diskinize bağlamayı deneyin.  
  
3.  Disk üzerindeki bozuk blok.  
  
     Disk donanım ve işletim sistemi gibi bir hata algılandı karşın, bir disk denetleme programı çalıştırmak isteyebilirsiniz.  
  
4.  Yığın alanı kalmadı.  
  
     Bkz: [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) daha fazla bilgi için.