---
title: Derleyici Hatası C3896 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C3896
dev_langs:
- C++
helpviewer_keywords:
- C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4aa98283d3c83f64ba461bf818a88599f97434e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3896"></a>Derleyici Hatası C3896
'member': hatalı Başlatıcı: Bu değişmez değer veri üyesi 'ile nullptr' yalnızca ilk değer atanabilir  
  
 A [değişmez değer](../../windows/literal-cpp-component-extensions.md) veri üyesi başlatılmış yanlış.  Bkz: [nullptr](../../windows/nullptr-cpp-component-extensions.md) daha fazla bilgi için.  
  
 Aşağıdaki örnek C3896 oluşturur:  
  
```  
// C3896.cpp  
// compile with: /clr /c  
ref class R{};  
  
value class V {  
   literal R ^ r = "test";   // C3896  
   literal R ^ r2 = nullptr;   // OK  
};  
```