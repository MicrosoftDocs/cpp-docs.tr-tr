---
title: "Derleyici Hatası C2570 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2570
dev_langs: C++
helpviewer_keywords: C2570
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 873d71415e610ee1a7295cd425b9960360f8631f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2570"></a>Derleyici Hatası C2570
'tanımlayıcısı': UNION temel sınıflar sahip olamaz  
  
 UNION, sınıf, yapı veya birleşim türer. Bu duruma izin verilmez. Türetilmiş bir tür bir sınıf veya yapı bunun yerine bildirin.  
  
 Aşağıdaki örnek C2570 oluşturur:  
  
```  
// C2570.cpp  
// compile with: /c  
class base {};  
union hasPubBase : public base {};   // C2570  
union hasNoBase {};   // OK  
```