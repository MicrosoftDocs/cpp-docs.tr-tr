---
title: "Derleyici Hatası C3320 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3320
dev_langs:
- C++
helpviewer_keywords:
- C3320
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c729bf63fae7a7181496e1901dda1d8ac5bdfa50
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3320"></a>Derleyici Hatası C3320
'type': türü module 'name' özelliği aynı ada sahip olamaz  
  
Geçirilen parametre olarak yapısı, sınıf, numaralandırma veya birleşim olabilen, bir verilen kullanıcı tanımlı tür (UDT) aynı ada sahip olamaz [Modülü](../../windows/module-cpp.md) özniteliğin adı özelliği.  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C3320 oluşturur:  
  
```cpp  
// C3320.cpp  
#include "unknwn.h"  
[module(name="xx")];  
  
[export] struct xx {   // C3320  
// Try the following line instead  
// [export] struct yy {  
   int i;  
};  
```