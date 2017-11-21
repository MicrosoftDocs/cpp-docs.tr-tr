---
title: "Derleyici Hatası C2248 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2248
dev_langs: C++
helpviewer_keywords: C2248
ms.assetid: 7a3ba0e8-d3b9-4bb9-95db-81ef17e31d23
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a6023532a7644753f1aaff957232fde70d01426f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2248"></a>Derleyici Hatası C2248
'*üye*': erişemiyor '*access_level*'üye bildirilen sınıfında'*sınıfı*'  
  
Türetilmiş bir sınıf üyeleri erişemiyor `private` bir taban sınıfı üyeleri. Öğesine erişemiyor `private` veya `protected` sınıf örneklerini üyeleri.  
  
## <a name="example"></a>Örnek  
  
Bir sınıfın korumalı üyeleri sınıfın dışından erişilen veya C2248 özel olduğunda aşağıdaki örneği oluşturur. Bu sorunu gidermek için bu üyeleri sınıfın dışından doğrudan erişmez. Ortak üye verileri ve üye işlevleri sınıfı ile etkileşim kurmak için kullanın.  
  
```cpp  
// C2248_access.cpp 
// compile with: cl /EHsc /W4 C2248_access.cpp 
#include <stdio.h>  

class X {  
public:  
    int  m_publicMember;  
    void setPrivateMember( int i ) {  
        m_privateMember = i;  
        printf_s("\n%d", m_privateMember);  
    }  
protected:  
    int  m_protectedMember;  
  
private:  
    int  m_privateMember;  
} x;  
  
int main() {  
    x.m_publicMember = 4;  
    printf_s("\n%d", x.m_publicMember);  
    x.m_protectedMember = 2; // C2248 m_protectedMember is protected  
    x.m_privateMember = 3;   // C2248  m_privMemb is private  
    x.setPrivateMember(0);   // OK uses public access function  
}  
```  
  
C2248 gösteren başka bir uyumluluk sorunu şablon arkadaşları ve uzmanlık kullanımıdır. Bu sorunu gidermek için bir boş şablon parametre listesi <> veya belirli bir şablon parametreleri kullanarak şablon işlevleri arkadaş bildirin.  
  
```cpp  
// C2248_template.cpp 
// compile with: cl /EHsc /W4 C2248_template.cpp 
template<class T>  
void f(T t) {  
    t.i;   // C2248  
}  
  
struct S {  
private:  
    int i;  
  
public:  
    S() {}  
    friend void f(S);   // refer to the non-template function void f(S)  
    // To fix, comment out the previous line and
    // uncomment the following line.  
    // friend void f<S>(S);  
};  
  
int main() {  
    S s;  
    f<S>(s);  
}  
```  
  
Bir sınıf ve sınıf arkadaş bildirimine sınıfının kapsamında görünür olmadığında bir arkadaş bildirme girişiminde bulunduğunuzda C2248 gösteren başka bir uyum sorunudur. Bu sorunu gidermek için kapsayan sınıfına Arkadaşlık verin.  
  
```cpp  
// C2248_enclose.cpp  
// compile with: cl /W4 /c C2248_enclose.cpp  
class T {  
    class S {  
        class E {};  
    };  
    friend class S::E;   // C2248  
};  
  
class A {  
    class S {  
        class E {};  
        friend class A;  // grant friendship to enclosing class  
    };  
    friend class S::E;   // OK  
};  
```