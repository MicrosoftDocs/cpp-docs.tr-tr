---
title: Derleyici Hatası C3737 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3737
dev_langs:
- C++
helpviewer_keywords:
- C3737
ms.assetid: ca2aeb23-2491-4ccb-8838-884abf7065c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29d31597e9581d03f97c2b07856ce81c5de50bd3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33264616"
---
# <a name="compiler-error-c3737"></a>Derleyici Hatası C3737
'temsilci': bir temsilci açık bir çağrı kuralı olmayabilir  
  
 Belirtemeyeceğiniz [çağırma](../../cpp/calling-conventions.md) için bir `delegate`.  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C3737 oluşturur:  
  
```  
// C3737a.cpp  
// compile with: /clr  
delegate void __stdcall MyFunc();   // C3737  
// Try the following line instead.  
// delegate void MyFunc();  
  
int main() {  
}  
```  
