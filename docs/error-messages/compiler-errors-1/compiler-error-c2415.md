---
title: "Derleyici Hatası C2415 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2415
dev_langs: C++
helpviewer_keywords: C2415
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 68666ba203897b43fb1658525e1f342bcb923c09
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2415"></a>Derleyici Hatası C2415
hatalı işlenen türü  
  
 Opcode bu türündeki işlenenler kullanmaz.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Opcode kullanılan işlenenler sayısını desteklemiyor. İşlenen doğru sayısını belirlemek için bir derleme dili başvurusu el ile denetleyin.  
  
2.  Daha yeni bir işlemci ek türleriyle yönerge destekler. Ayarlama [/arch (en düşük CPU Mimarisi)](../../build/reference/arch-minimum-cpu-architecture.md) sonraki işlemci kullanacak şekilde seçeneği.