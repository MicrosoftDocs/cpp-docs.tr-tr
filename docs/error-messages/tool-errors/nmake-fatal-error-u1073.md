---
title: NMAKE önemli hatası U1073 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1073
dev_langs:
- C++
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c309ed94cd1c984406e0d21f0139e35c6e41d7d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053952"
---
# <a name="nmake-fatal-error-u1073"></a>NMAKE Önemli Hatası U1073

'targetname' olun nasıl yapılandıracağımı bilmiyorum

Belirtilen hedef yok ve yürütmek için komut veya uygulamak için çıkarım kuralı yok.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltmek için

1. Hedef adı yazımını denetleyin.

1. Varsa *targetname* bir pseudotarget olan başka bir açıklama bloğundaki hedefi olarak belirtin.

1. Varsa *targetname* bir makro çağrısı olduğundan bu genişletmeyen boş bir dize emin olun.