---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2248'
title: Derleyici hatası C2248
ms.date: 11/04/2016
f1_keywords:
- C2248
helpviewer_keywords:
- C2248
ms.assetid: 7a3ba0e8-d3b9-4bb9-95db-81ef17e31d23
ms.openlocfilehash: f2d840195fd6cdeb4cc8e1e90a06a502378ac634
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337602"
---
# <a name="compiler-error-c2248"></a>Derleyici hatası C2248

'*üye*': '*Class*' sınıfında belirtilen '*access_level*' üyesine erişilemiyor

Türetilmiş bir sınıfın üyeleri **`private`** bir temel sınıfın üyelerine erişemez. **`private`** Sınıf örneklerine erişemez veya **`protected`** üye ekleyemezsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir sınıfın özel veya korumalı üyelerine sınıfının dışından erişildiğinde C2248 oluşturur. Bu sorunu düzeltemedi, bu üyelere doğrudan sınıf dışından erişmeyin. Sınıfla etkileşim kurmak için ortak üye verilerini ve üye işlevlerini kullanın.

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

C2248 sunan başka bir uyumluluk sorunu, şablon arkadaşları ve özelleştirmesi 'nın kullanımı. Bu sorunu onarmak için, bir boş şablon parametre listesi <> veya belirli şablon parametrelerini kullanarak arkadaş şablon işlevleri bildirin.

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

Bir sınıfın arkadaşını bildirmeye çalıştığınızda ve sınıf, sınıf kapsamındaki arkadaş bildirimine görünür olmadığında, C2248 sunan başka bir uyumluluk sorunu. Bu sorunu düzeltemedi, kapsayan sınıfa arkadaşlık verin.

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
