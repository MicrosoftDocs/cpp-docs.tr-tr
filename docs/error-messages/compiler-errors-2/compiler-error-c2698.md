---
title: Derleyici Hatası C2698 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2698
dev_langs:
- C++
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c466e39702f1e408ad96d79c16c4a5953fa373f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2698"></a>Derleyici Hatası C2698
using bildirimi için ' bildirimi 1' Varolan using bildirimi için ile birlikte bulunamayacak ' bildirimi 2'  
  
 Bulduktan sonra bir [bildirimi kullanarak](../../cpp/using-declaration.md) kullanarak herhangi bir veri üyesi için aynı adı kullanan aynı kapsamı bildiriminde izin verilmez, yalnızca işlevleri aşırı gibi.  
  
 Aşağıdaki örnek C2698 oluşturur:  
  
```  
// C2698.cpp  
struct A {  
   int x;  
};  
  
struct B {  
   int x;  
};  
  
struct C : A, B {  
   using A::x;  
   using B::x;   // C2698  
}  
```