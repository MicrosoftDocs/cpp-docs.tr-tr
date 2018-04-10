---
title: Derleyici Hatası C2071 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C2071
dev_langs:
- C++
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1cb7d80f016250d289a70456f6fbfe2011c9410b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2071"></a>Derleyici Hatası C2071
'tanımlayıcısı': Geçersiz depolama sınıfı  
  
 `identifier`Geçersiz bir bildirildi [depolama sınıfı](../../c-language/c-storage-classes.md). Birden fazla depolama sınıfı tanımlayıcısı belirtildiğinde veya tanımı depolama sınıf bildirimi ile uyumsuz olduğunda bu hata oluşabilir.  
  
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