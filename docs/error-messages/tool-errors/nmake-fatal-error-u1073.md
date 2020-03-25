---
title: NMAKE Önemli Hatası U1073
ms.date: 11/04/2016
f1_keywords:
- U1073
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
ms.openlocfilehash: 97d44594540d18bf008757506a9e36e6d16d2cd7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182701"
---
# <a name="nmake-fatal-error-u1073"></a>NMAKE Önemli Hatası U1073

' TargetName ' yapmayı bilmiyorum

Belirtilen hedef yok ve uygulanacak bir komut veya çıkarım kuralı yok.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltilmesi için

1. Hedef adının yazımını denetleyin.

1. *TargetName* bir sözde hedef ise, bunu başka bir açıklama bloğunda hedef olarak belirtin.

1. *TargetName* bir makro çağrımı ise, null bir dizeye genişlemediğinden emin olun.
