---
title: Derleyici Uyarısı (Düzey 2) C4396 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4396
dev_langs:
- C++
helpviewer_keywords:
- C4396
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b937b6ecebedc6984279502a5f64b287f09bd2d9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33290676"
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