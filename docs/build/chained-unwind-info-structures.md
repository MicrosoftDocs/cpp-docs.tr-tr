---
title: "Zincirleme Bırakma bilgi yapıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 176835bf-f118-45d9-9128-9db4b7571864
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8e608d3b6826eb8bfbcebdec7fdf9891d033b418
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="chained-unwind-info-structures"></a>Zincirleme Bırakma Bilgi Yapıları
UNW_FLAG_CHAININFO bayrağı ayarlarsanız, ardından bir bırakma bilgisi ikincil bir yapıdır ve paylaşılan özel durum işleyici/zincirleme-bilgisi adres alanı birincil bırakma bilgi içerir. Aşağıdaki kod alır birincil bırakma bilgi olduğunu varsayarak, `unwindInfo` kümesine sahip yapısı bayrağı ayarlanmış olduğu.  
  
```  
PRUNTIME_FUNCTION primaryUwindInfo = (PRUNTIME_FUNCTION)&(unwindInfo->UnwindCode[( unwindInfo->CountOfCodes + 1 ) & ~1]);  
```  
  
 Zincirleme bilgi iki durumlarda faydalıdır. İlk olarak, bitişik olmayan kod kesimleri için kullanılabilir. Zincirleme bilgi kullanarak birincil bırakma bilgisi bırakma kodları diziden çoğaltmak olmadığı için gerekli bırakma bilgi boyutunu azaltabilirsiniz.  
  
 Zincirleme bilgi, geçici kayıtları gruplamak için de kullanabilirsiniz. Derleyici dışında işlevi giriş giriş oluncaya kadar bazı geçici kayıtları geciktirebilir. Bu gruplandırılmış koddan önce işlevin kısmı için birincil bırakma bilgisi sağlayarak kaydedebilir ve burada zincirleme bilgileri bırakma kodlarının kalıcı Yazmaçları kaydeder yansıtacak giriş, sıfır olmayan boyutunu bilgiyle zincirleme sonra ayarlama. Bu durumda, bırakma kodlarının tüm UWOP_SAVE_NONVOL örnekleridir. PUSH kullanarak kalıcı Yazmaçları kaydeden veya bir ek sabit yığın ayırma kullanarak RSP kaydı değiştiren bir gruplandırma desteklenmez.  
  
 Ayarlama kümesine sahip bir UNWIND_INFO öğesi, UNWIND_INFO öğesi de (birden çok sabit) ayarlamak kümesine sahip bir RUNTIME_FUNCTION girdisini içerebilir. Sonuç olarak, zincirleme işaretçileri temizlenmiş kümesine sahip UNWIND_INFO öğeyi ulaşır bilgilerindeki; Bu, gerçek yordamı için giriş noktası işaret birincil UNWIND_INFO öğe değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri bırakma, özel durum işleme için hata ayıklayıcı desteği](../build/unwind-data-for-exception-handling-debugger-support.md)