---
title: Bağlayıcı araçları hatası LNK1106 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1106
dev_langs:
- C++
helpviewer_keywords:
- LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3dedaa2bd500b11f06f9cfa98802fdd6ca84534
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298097"
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