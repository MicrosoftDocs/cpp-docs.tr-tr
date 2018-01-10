---
title: "Derleyici Hatası C3418 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3418
dev_langs: C++
helpviewer_keywords: C3418
ms.assetid: 54042c04-3c45-41c1-bad7-90f9ee05a21b
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e36fa3a27a122db715f84405b0484508fb13e8a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3418"></a>Derleyici Hatası C3418
erişim tanımlayıcısı 'tanımlayıcısı' desteklenmiyor  
  
Bir CLR erişim belirteci yanlış belirtildi.  Daha fazla bilgi için bkz: tür görünürlüğü ve üye görünürlüğü [nasıl yapılır: tanımlayın ve tüketmek sınıflar ve yapılar (C + +/ CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md).  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C3418 oluşturur.  
  
```cpp  
// C3418.cpp  
// compile with: /clr /c  
ref struct m {  
internal public:   // C3418  
   void test(){}  
};  
  
ref struct n {  
internal:   // OK  
   void test(){}  
};  
```