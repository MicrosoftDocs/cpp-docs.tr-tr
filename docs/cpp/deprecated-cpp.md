---
title: "(C++) kullanım dışı | Microsoft Docs"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: deprecated_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], deprecated
- deprecated __declspec keyword
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d3ec06d469f6fc71b23c9bdc6a67e5ed741d9f5f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="deprecated-c"></a>deprecated (C++)
Bu konu hakkında Microsoft'a özgü olan declspec bildirimi kullanım dışı. C ++ 14 hakkında bilgi için `[[deprecated]]` özniteliği ve ne zaman bu öznitelik Microsoft'a özgü declspec veya pragma, karşılaştırması kullanılacağı Kılavuzu bkz [C++ Standart öznitelikleri](attributes2.md).

 Aşağıda, belirtilen özel durumlarla birlikte **kullanım dışı** bildirimi ile aynı işlevselliği sunar [kullanım dışı](../preprocessor/deprecated-c-cpp.md) pragma:  
  
-   **Kullanım dışı** bildirimi belirtmenize olanak sağlar işlev aşırı yüklemelerinin belirli biçimlerinin olarak kullanım dışı pragma formun tüm aşırı yüklenmiş bir işlev adı formlara uygulanır ancak.  
  
-   **Kullanım dışı** bildirimi derleme zamanında görüntülenecek bir ileti belirtmenize olanak sağlar. İleti metni makrosu olabilir.  
  
-   Makroları yalnızca ile kullanım dışı bırakıldı olarak işaretlenmelidir **kullanım dışı** pragması.  
  
 Derleyici kullanım dışı bırakılan bir tanımlayıcısı veya standart kullanılmasını karşılaştığı varsa [ `[[deprecated]]` ](attributes2.md) öznitelik, bir [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) uyarı oluşturulur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, kullanım dışı işlev kullanıldığında derleme zamanında görüntülenen bir ileti belirtme ve İşlevler kullanım dışı olarak işaretlemek nasıl gösterir.  
  
```  
// deprecated.cpp  
// compile with: /W3  
#define MY_TEXT "function is deprecated"  
void func1(void) {}  
__declspec(deprecated) void func1(int) {}  
__declspec(deprecated("** this is a deprecated function **")) void func2(int) {}  
__declspec(deprecated(MY_TEXT)) void func3(int) {}  
  
int main() {  
   func1();  
   func1(1);   // C4996  
   func2(1);   // C4996  
   func3(1);   // C4996  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, kullanım dışı sınıfı kullanıldığında derleme zamanında görüntülenen bir ileti belirtme ve sınıfları kullanım dışı olarak işaretlemek nasıl gösterir.  
  
```  
// deprecate_class.cpp  
// compile with: /W3  
struct __declspec(deprecated) X {  
   void f(){}  
};  
  
struct __declspec(deprecated("** X2 is deprecated **")) X2 {  
   void f(){}  
};  
  
int main() {  
   X x;   // C4996  
   X2 x2;   // C4996  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)