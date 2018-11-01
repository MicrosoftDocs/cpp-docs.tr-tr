---
title: NMAKE Önemli Hatası U1073
ms.date: 11/04/2016
f1_keywords:
- U1073
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
ms.openlocfilehash: 2aa02fd86906bd545373a313fa5e6e409ffb3cf9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582279"
---
# <a name="nmake-fatal-error-u1073"></a>NMAKE Önemli Hatası U1073

'targetname' olun nasıl yapılandıracağımı bilmiyorum

Belirtilen hedef yok ve yürütmek için komut veya uygulamak için çıkarım kuralı yok.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltmek için

1. Hedef adı yazımını denetleyin.

1. Varsa *targetname* bir pseudotarget olan başka bir açıklama bloğundaki hedefi olarak belirtin.

1. Varsa *targetname* bir makro çağrısı olduğundan bu genişletmeyen boş bir dize emin olun.