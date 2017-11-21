---
title: "Derleyici Hatası C2821 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2821
dev_langs: C++
helpviewer_keywords: C2821
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f0218061b8d34eca00baa5834053d90711798bd0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2821"></a>Derleyici Hatası C2821
'yeni işleç' ilk biçimsel parametresi 'imzasız int' olmalıdır  
  
İlk biçimsel parametresi [new işleci](../../standard-library/new-operators.md#op_new) imzasız olmalıdır `int`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2821 oluşturur:  
  
```cpp  
// C2821.cpp  
// compile with: /c  
void * operator new( /* unsigned int,*/ void * );   // C2821  
void * operator new( unsigned int, void * );  
```