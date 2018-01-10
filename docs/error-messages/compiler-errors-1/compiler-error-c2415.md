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
ms.workload: cplusplus
ms.openlocfilehash: 4ff0f423ec83b9951e806a2483417f3ab79f817a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2415"></a>Derleyici Hatası C2415
hatalı işlenen türü  
  
 Opcode bu türündeki işlenenler kullanmaz.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Opcode kullanılan işlenenler sayısını desteklemiyor. İşlenen doğru sayısını belirlemek için bir derleme dili başvurusu el ile denetleyin.  
  
2.  Daha yeni bir işlemci ek türleriyle yönerge destekler. Ayarlama [/arch (en düşük CPU Mimarisi)](../../build/reference/arch-minimum-cpu-architecture.md) sonraki işlemci kullanacak şekilde seçeneği.