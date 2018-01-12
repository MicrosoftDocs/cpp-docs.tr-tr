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
ms.workload: cplusplus
ms.openlocfilehash: e341266c37411d96a4cf313e6a101e48aeb2a85d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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