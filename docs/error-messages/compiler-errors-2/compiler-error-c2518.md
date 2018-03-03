---
title: "Derleyici Hatası C2518 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2518
dev_langs:
- C++
helpviewer_keywords:
- C2518
ms.assetid: a7895b47-da90-4851-ac97-18e81479595a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f711fb8c1ebf5f3bdc6352595164ec5d6ccb0fdf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2518"></a>Derleyici Hatası C2518
anahtar sözcüğü 'anahtar sözcüğü' taban sınıf listesinde; geçersiz göz ardı  
  
 Anahtar sözcükler `class` ve `struct` bir temel sınıf listesinde görünmemesi gerekir.  
  
 Aşağıdaki örnek C2518 oluşturur:  
  
```  
// C2518.cpp  
// compile with: /c  
class B {};  
class C : public class B {};   // C2518  
class D: public B {};   // OK  
```