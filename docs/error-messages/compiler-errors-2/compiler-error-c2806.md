---
title: Derleyici Hatası C2806 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2806
dev_langs:
- C++
helpviewer_keywords:
- C2806
ms.assetid: 7c9ff1f4-1590-4c47-991d-b1075a173b48
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c75a6aee78aef97f57acd29bf640917600dc05e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33237464"
---
# <a name="compiler-error-c2806"></a>Derleyici Hatası C2806
çok fazla biçimsel parametresi 'işleci işleci' olan  
  
 Aşırı yüklenmiş bir işleç çok fazla parametre yok.  
  
 Aşağıdaki örnek C2806 oluşturur:  
  
```  
// C2806.cpp  
// compile with: /c  
class X {  
public:  
   X operator++ ( int, int );   // C2806 more than 1 parameter  
   X operator++ ( int );   // OK  
} ;  
```