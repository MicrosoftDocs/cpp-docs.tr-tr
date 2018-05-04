---
title: İşlev türleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 7e33d5f4-dabb-406d-afb3-13777b995028
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 322bd45abbfe217671fd39f0617987fde21445db
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="function-types"></a>İşlev Türleri
Temel işlevler iki tür vardır. Yığın çerçevesi gerektiren bir işlev çerçeve işlevi çağrılır. Yığın çerçevesi gerektirmeyen bir işlev yaprak işlevi çağrılır.  
  
 Çerçeve işlevi yığın alan ayırır, diğer işlevleri çağıran, kalıcı Yazmaçları kaydeden veya özel durum işleme kullanan bir işlevdir. Ayrıca, bir işlev tablo girişi gerektirir. Çerçeve işlevi bir giriş ve bitiş gerektirir. Çerçeve işlevi yığın alanı dinamik olarak ayırabilir ve bir çerçeve işaretçisi tercih edebilirsiniz. Çerçeve işlevi, alt elden standart çağırma özelliklerinin tamamı bu sahiptir.  
  
 Çerçeve işlevi başka bir işlev çağırmaz sonra yığını hizalamak için gerekli olmayan ('bölümünde [yığın ayırma](../build/stack-allocation.md)).  
  
 Bir yaprak işlevi tablo girişi gerektirmeyen bir işlevdir. Bu, tüm işlevler çağıramaz ya yığın alanı ayırdığınızdan emin anlamına gelir RSP dahil olmak üzere tüm kalıcı Yazmaçları değişiklik yapamazsınız. Yürütürken yığın hizalanmamış bırakın izin verilmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yığın Kullanımı](../build/stack-usage.md)
