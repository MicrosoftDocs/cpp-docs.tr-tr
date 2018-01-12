---
title: "NMAKE önemli hatası U1073 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1073
dev_langs: C++
helpviewer_keywords: U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: faae317df44560991a88d47ec7f123e6a8126429
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1073"></a>NMAKE Önemli Hatası U1073
'targetname' nasıl bilmiyorsanız  
  
 Belirtilen hedef yok ve yürütülecek komut veya uygulamak için çıkarım kuralı yok.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümlere kullanarak düzeltmek için  
  
1.  Hedef adının yazımını denetleyin.  
  
2.  Varsa *targetname* bir pseudotarget olan başka bir açıklama bloğundaki hedefi olarak belirtin.  
  
3.  Varsa *targetname* makrosu çağırma olduğu değil genişletmek için boş bir dize emin olun.