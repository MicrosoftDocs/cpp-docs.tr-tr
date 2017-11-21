---
title: "Derleyici Uyarısı (düzey 4) C4459 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4459
dev_langs: C++
helpviewer_keywords: C4459
ms.assetid: ee9f6287-9c70-4b10-82a0-add82a13997f
caps.latest.revision: "0"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 11a4122bf58ac5645c4430f8c6a41de7ed19f430
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4459"></a>Derleyici Uyarısı (düzey 4) C4459
  
> bildirimi '*tanımlayıcısı*' genel bildirim gizler
  
Bildirimi *tanımlayıcısı* yerel kapsamda aynı adlı bildirimi gizler *tanımlayıcısı* genel kapsamda. Bu uyarı, başvuran için bilmenizi sağlar *tanımlayıcısı* bu kapsamda olabilir veya maksadınızı olmayabilir genel sürümünü değil, yerel olarak bildirilen sürüme çözümleyin. Genellikle, iyi bir mühendislik uygulama olarak genel değişkenler kullanımını en aza öneririz. Genel ad alanı kirliliği en aza indirmek için genel değişkenler adlandırılmış bir ad alanı kullanılmasını öneririz.  
  
Bu uyarı Visual c++ derleyici sürümü 18.00 Visual Studio 2015'te yeni. Derleyici veya kodunuzu geçiş sırasında daha sonra sürümdeki uyarıları gizlemek için kullanın [/Wv:18](../../build/reference/compiler-option-warning-level.md) derleyici seçeneği. 

## <a name="example"></a>Örnek
  
 Aşağıdaki örnek C4459 oluşturur:  
  
```cpp  
// C4459_hide.cpp
// compile with: cl /W4 /EHsc C4459_hide.cpp
int global_or_local = 1;

int main() { 
    int global_or_local; // warning C4459 
    global_or_local = 2;
} 
```  
  
Bu sorunu çözmenin bir yolu olan bir ad alanı, globals için oluşturmak ve kullanmak için bir `using` tüm başvuruları anlaşılır kullanmak için bu ad alanı kapsam içine getirmek için yönergesi nitelenmiş adlar:  
  
```cpp  
// C4459_namespace.cpp
// compile with: cl /W4 /EHsc C4459_namespace.cpp
namespace globals {
    int global_or_local = 1;
}

int main() { 
    int global_or_local; // OK 
    global_or_local = 2;
    globals::global_or_local = 3;
} 
```  
