---
title: "İşlev türleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 7e33d5f4-dabb-406d-afb3-13777b995028
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 54f2b910062038901578389a9c0a7ab8a2647f3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="function-types"></a>İşlev Türleri
Temel işlevler iki tür vardır. Yığın çerçevesi gerektiren bir işlev çerçeve işlevi çağrılır. Yığın çerçevesi gerektirmeyen bir işlev yaprak işlevi çağrılır.  
  
 Çerçeve işlevi yığın alan ayırır, diğer işlevleri çağıran, kalıcı Yazmaçları kaydeden veya özel durum işleme kullanan bir işlevdir. Ayrıca, bir işlev tablo girişi gerektirir. Çerçeve işlevi bir giriş ve bitiş gerektirir. Çerçeve işlevi yığın alanı dinamik olarak ayırabilir ve bir çerçeve işaretçisi tercih edebilirsiniz. Çerçeve işlevi, alt elden standart çağırma özelliklerinin tamamı bu sahiptir.  
  
 Çerçeve işlevi başka bir işlev çağırmaz sonra yığını hizalamak için gerekli olmayan ('bölümünde [yığın ayırma](../build/stack-allocation.md)).  
  
 Bir yaprak işlevi tablo girişi gerektirmeyen bir işlevdir. Bu, tüm işlevler çağıramaz ya yığın alanı ayırdığınızdan emin anlamına gelir RSP dahil olmak üzere tüm kalıcı Yazmaçları değişiklik yapamazsınız. Yürütürken yığın hizalanmamış bırakın izin verilmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yığın Kullanımı](../build/stack-usage.md)
