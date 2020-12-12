---
description: 'Hakkında daha fazla bilgi edinin: NMAKE önemli hatası U1051'
title: NMAKE Önemli Hatası U1051
ms.date: 11/04/2016
f1_keywords:
- U1051
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
ms.openlocfilehash: c7d465eaf34adb69e41f523006fb0740eea722ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272116"
---
# <a name="nmake-fatal-error-u1051"></a>NMAKE Önemli Hatası U1051

yetersiz bellek

Derleme görevleri dosyası çok büyük veya karmaşık olduğundan, sanal bellek dahil olmak üzere NMAKE belleği tükendi.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltilmesi için

1. Diskte boş alan boşaltın.

1. Windows NT disk belleği dosyasının veya Windows takas dosyasının boyutunu artırın.

1. Derleme görevleri dosyasının yalnızca bir kısmı kullanılıyorsa, derleme görevleri dosyasını ayrı dosyalara bölün veya kullanın **! Eğer** , NMAKE 'in işlemesi gereken miktarı sınırlamak için ön işleme yönergeleri. **! Yönergeler IÇERIYORSA** **! Eğer**, `!IFDEF` , **! IFNDEF**, **! AKSI TAKDIRDE**, **! ELSE** `IFDEF` ve **! ELSE** `IFNDEF` .
