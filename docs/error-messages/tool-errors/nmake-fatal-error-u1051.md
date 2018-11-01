---
title: NMAKE Önemli Hatası U1051
ms.date: 11/04/2016
f1_keywords:
- U1051
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
ms.openlocfilehash: ddf1d262fb8dfc6e63b0bf5cc098b7b140539310
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641512"
---
# <a name="nmake-fatal-error-u1051"></a>NMAKE Önemli Hatası U1051

Bellek yetersiz

NMAKE derleme görevleri dosyası çok büyük veya karmaşık olduğundan, sanal bellek dahil olmak üzere, bellek yetersiz kaldı.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltmek için

1. Disk üzerinde biraz alan boşaltın.

1. Windows NT disk belleği dosyası ya da Windows takas dosyası boyutunu artırın.

1. Yalnızca derleme görevleri dosyası parçası kullanılan derleme görevleri dosyası ayrı dosyalara bölün veya kullanın **! Eğer** ön işleme NMAKE işlemelisiniz tutarını sınırlamak için yönergeleri. **! Eğer** yönergelerinde **! Eğer**, `!IFDEF`, **! IFNDEF**, **! ELSE IF**, **! BAŞKA** `IFDEF`, ve **! BAŞKA** `IFNDEF`.