---
title: "Derleyici Hatası C3865 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3865
dev_langs: C++
helpviewer_keywords: C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: af0873d70fcb4f947e838afba130279edf705ced
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3865"></a>Derleyici Hatası C3865
'calling_convention': yalnızca yerel üye işlevlerini kullanılabilir  
  
 Çağırma kuralı genel bir işlevi olan bir işlevi veya yönetilen üye işlevi kullanıldı. Çağırma kuralı yalnızca yerel (yönetilmiyor) üye işlevi üzerinde kullanılabilir.  
  
 Daha fazla bilgi için bkz: [çağırma kuralları](../../cpp/calling-conventions.md).  
  
 Aşağıdaki örnek C3865 oluşturur:  
  
```  
// C3865.cpp  
// compile with: /clr  
// processor: x86  
void __thiscall Func(){}   // C3865  
  
// OK  
struct MyType {  
   void __thiscall Func(){}  
};  
```