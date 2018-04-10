---
title: Derleyici Hatası C3085 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- C3085
dev_langs:
- C++
helpviewer_keywords:
- C3085
ms.assetid: 1ac40bf2-f63e-439e-8921-47e6dadc8354
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a7b193a0d059598a3b73bc2e743ace5724b9cf4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3085"></a>Derleyici Hatası C3085
'Oluşturucusu': bir Oluşturucu 'anahtar sözcüğü' olamaz  
  
 Bir oluşturucu yanlış bildirildi. Bkz: [geçersiz kılma tanımlayıcıları](../../windows/override-specifiers-cpp-component-extensions.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3085 oluşturur.  
  
```  
// C3085.cpp  
// compile with: /c /clr  
ref struct S {  
   S() abstract;   // C3085  
   S(S%) abstract;   // C3085  
};  
  
ref struct T {  
   T() sealed {}   // C3085  
   T(T%) sealed {}   // C3085  
};  
```