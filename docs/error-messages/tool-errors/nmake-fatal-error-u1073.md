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
ms.openlocfilehash: dde9ca2f4a15edf6599dcc31b39d9411645f2a6f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33316312"
---
# <a name="nmake-fatal-error-u1073"></a>NMAKE Önemli Hatası U1073
'targetname' nasıl bilmiyorsanız  
  
 Belirtilen hedef yok ve yürütülecek komut veya uygulamak için çıkarım kuralı yok.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümlere kullanarak düzeltmek için  
  
1.  Hedef adının yazımını denetleyin.  
  
2.  Varsa *targetname* bir pseudotarget olan başka bir açıklama bloğundaki hedefi olarak belirtin.  
  
3.  Varsa *targetname* makrosu çağırma olduğu değil genişletmek için boş bir dize emin olun.