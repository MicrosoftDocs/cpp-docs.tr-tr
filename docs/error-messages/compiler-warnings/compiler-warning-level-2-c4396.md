---
title: "Derleyici Uyarısı (Düzey 2) C4396 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4396
dev_langs: C++
helpviewer_keywords: C4396
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bd40c2b78c12cff4b3904348c86dff1c7c3da0b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4396"></a>Derleyici Uyarısı (Düzey 2) C4396
"name": arkadaş bildirimi işlevi şablonu özelleştirmesi için başvurduğunda satır içi belirticisi kullanılamaz  
  
 İşlev şablonu uzmanlaşması herhangi birini belirtmek [satır içi](../../cpp/inline-functions-cpp.md) tanımlayıcıları. Derleyici Uyarısı C4396 sorunları ve satır içi tanımlayıcısı yok sayar.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Kaldırma `inline`, `__inline`, veya `__forceinline` arkadaş işlev bildirimi gelen tanımlayıcısı.  
  
## <a name="example"></a>Örnek  
 Geçersiz bir arkadaş işlevi bildiriminde ile aşağıdaki kodu örnekte gösterildiği bir `inline` tanımlayıcısı.  
  
```  
// C4396.cpp  
// compile with: /W2 /c  
  
class X;   
template<class T> void Func(T t, int i);  
  
class X {  
    friend inline void Func<char>(char t, int i);  //C4396  
// try the following line instead  
//    friend void Func<char>(char t, int i);   
    int i;  
};  
```