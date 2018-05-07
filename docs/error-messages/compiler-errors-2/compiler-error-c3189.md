---
title: Derleyici Hatası C3189 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3189
dev_langs:
- C++
helpviewer_keywords:
- C3189
ms.assetid: b254de79-931e-4a59-a9f4-1c690d90ca5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acf0e49ecf9c8003d8dcfe035b14c8f5c5067dbc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3189"></a>Derleyici Hatası C3189
' TypeID\<soyut bildirimcisi yazın >': Bu söz dizimini artık desteklenmeyen, kullanın:: TypeID yerine  
  
 Artık kullanılmayan bir biçiminde [TypeID](../../windows/typeid-cpp-component-extensions.md) edildi kullanıldığında, yeni formu kullanın.  
  
 Aşağıdaki örnek C3189 oluşturur:  
  
```  
// C3189.cpp  
// compile with: /clr  
int main() {  
   System::Type^ t  = typeid<System::Object>;   // C3189  
   System::Type^ t2  = System::Object::typeid;   // OK  
}  
```