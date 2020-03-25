---
title: NMAKE Önemli Hatası U1051
ms.date: 11/04/2016
f1_keywords:
- U1051
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
ms.openlocfilehash: 9c6b939c97f993e42049677292374377d825d474
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193686"
---
# <a name="nmake-fatal-error-u1051"></a>NMAKE Önemli Hatası U1051

yetersiz bellek

Derleme görevleri dosyası çok büyük veya karmaşık olduğundan, sanal bellek dahil olmak üzere NMAKE belleği tükendi.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltilmesi için

1. Diskte boş alan boşaltın.

1. Windows NT disk belleği dosyasının veya Windows takas dosyasının boyutunu artırın.

1. Derleme görevleri dosyasının yalnızca bir kısmı kullanılıyorsa, derleme görevleri dosyasını ayrı dosyalara bölün veya kullanın **! Eğer** , NMAKE 'in işlemesi gereken miktarı sınırlamak için ön işleme yönergeleri. **! Yönergeler IÇERIYORSA** **! Eğer**, `!IFDEF`, **! IFNDEF**, **! AKSI TAKDIRDE**, **! ELSE** `IFDEF`ve **! ELSE** `IFNDEF`.
