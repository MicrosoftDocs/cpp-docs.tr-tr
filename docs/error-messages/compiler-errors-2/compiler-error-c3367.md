---
title: "Derleyici Hatası C3367 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3367
dev_langs: C++
helpviewer_keywords: C3367
ms.assetid: e675d42b-f5b0-4d43-aab1-1f5024233102
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d1d144399ca42ba321d8f3d11425bf2ff8e65891
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3367"></a>Derleyici Hatası C3367
'static_member_function': statik işlevi ilişkisiz bir temsilci oluşturmak için kullanamazsınız  
  
İlişkisiz bir temsilciyi çağırdığınızda, bir nesnenin örneğine geçirmeniz gerekir. Statik üye işlevi sınıf adı olarak adlandırılan bu yana, yalnızca bir örneği üye işlevi ile ilişkisiz bir temsilci örneğini oluşturabilirsiniz.  
  
İlişkisiz temsilciler hakkında daha fazla bilgi için bkz: [nasıl yapılır: tanımlama ve kullanma temsilciler (C + +/ CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md).  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C3367 oluşturur.  
  
```cpp  
// C3367.cpp  
// compile with: /clr  
ref struct R {  
   void b() {}  
   static void f() {}  
};  
  
delegate void Del(R^);  
  
int main() {  
   Del ^ a = gcnew Del(&R::b);   // OK  
   Del ^ b = gcnew Del(&R::f);   // C3367  
}  
```