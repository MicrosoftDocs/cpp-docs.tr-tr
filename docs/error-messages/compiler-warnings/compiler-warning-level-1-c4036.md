---
title: "Derleyici Uyarısı (düzey 1) C4036 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4036
dev_langs: C++
helpviewer_keywords: C4036
ms.assetid: f0b15359-4d62-48ec-8cb1-a7b36587a47f
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6392ba12c14ca3ef89f992e358bf019d1d92e5db
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4036"></a>Derleyici Uyarısı (düzey 1) C4036
Gerçek parametre olarak adlandırılmamış 'type'  
  
 Yapısı, UNION, numaralandırma veya gerçek bir parametresi olarak kullanılan sınıf için hiçbir tür adı verilir. Kullanıyorsanız [/Zg](../../build/reference/zg-generate-function-prototypes.md) işlev prototipleri üret, derleyici bu uyarı ve açıklamalar oluşturulan prototip resmi parametresinde çıkışı verir.  
  
 Bu uyarıyı çözümlemek için bir tür adı belirtin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4036 oluşturur.  
  
```  
// C4036.c  
// compile with: /Zg /W1  
// D9035 expected  
typedef struct { int i; } T;  
void f(T* t) {}   // C4036  
  
// OK  
typedef struct MyStruct { int i; } T2;  
void f2(T2 * t) {}  
```