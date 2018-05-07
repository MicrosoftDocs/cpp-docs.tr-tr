---
title: Derleyici Hatası C2802 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2802
dev_langs:
- C++
helpviewer_keywords:
- C2802
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fe069b93c8dc6bb098927925e93f10cec2dbc4c3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2802"></a>Derleyici Hatası C2802
statik üye 'işleci işleci' biçimsel parametresi yok  
  
 Bir işleç tarafından bildirilen bir `static` üye işlevi, en az bir parametresi olmalıdır.  
  
 Aşağıdaki örnek C2802 oluşturur:  
  
```  
// C2802.cpp  
// compile with: /clr /c  
ref class A {  
   static operator+ ();   // C2802  
   static operator+ (A^, A^);   // OK  
};  
```