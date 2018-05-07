---
title: Derleyici Hatası C2071 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2071
dev_langs:
- C++
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: faee56023d14e9b010d1c691af654ffcbc31dc78
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2071"></a>Derleyici Hatası C2071
'tanımlayıcısı': Geçersiz depolama sınıfı  
  
 `identifier` Geçersiz bir bildirildi [depolama sınıfı](../../c-language/c-storage-classes.md). Birden fazla depolama sınıfı tanımlayıcısı belirtildiğinde veya tanımı depolama sınıf bildirimi ile uyumsuz olduğunda bu hata oluşabilir.  
  
 Bu sorunu gidermek için hedeflenen depolama sınıfı tanımlayıcısı anlamanız — Örneğin, `static` veya `extern`— ve bildirimi eşleşecek şekilde düzeltin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2071 oluşturur.  
  
```  
// C2071.cpp  
// compile with: /c  
struct C {  
   extern int i;   // C2071  
};  
struct D {  
   int i;   // OK, no extern on an automatic  
};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2071 oluşturur.  
  
```  
// C2071_b.cpp  
// compile with: /c  
typedef int x(int i) { return i; }   // C2071  
typedef int (x)(int);   // OK, no local definition in typedef  
```