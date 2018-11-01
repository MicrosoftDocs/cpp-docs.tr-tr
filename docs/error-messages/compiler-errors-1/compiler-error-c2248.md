---
title: Derleyici Hatası C2248
ms.date: 11/04/2016
f1_keywords:
- C2248
helpviewer_keywords:
- C2248
ms.assetid: 7a3ba0e8-d3b9-4bb9-95db-81ef17e31d23
ms.openlocfilehash: d9b9a6c04e7e9a5d88df516125280b6b23894a01
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558203"
---
# <a name="compiler-error-c2248"></a>Derleyici Hatası C2248

'*üye*': erişemiyor '*access_level*'üyesi, sınıfta bildirilen'*sınıfı*'

Türetilmiş bir sınıf üyelerine erişemez `private` bir taban sınıfı üyeleri. Erişemiyorsanız `private` veya `protected` üyeleri sınıf örneği.

## <a name="example"></a>Örnek

Aşağıdaki örnek, özel durumlarda C2248 oluşturur veya bir sınıfın korumalı üyeleri sınıf erişilen. Bu sorunu gidermek için bu üyeleri sınıf dışındaki doğrudan erişemez. Sınıf ile etkileşim kurmak için ortak üye verileri ve üye işlevleri kullanın.

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

Şablon arkadaşları ve uzmanlık C2248 sunan başka bir uyumluluk sorunu tabidir. Bu sorunu gidermek için bir boş şablon parametre listesi <> veya belirli bir şablon parametreleri kullanarak arkadaş şablon işlevleri bildirin.

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

C2248 sunan başka bir uyumluluk sorunu ve sınıfın sınıf kapsamı içinde friend bildirimi için görünür değil, bir sınıfın arkadaş bildirme girişimi andır. Bu sorunu gidermek için Arkadaşlık kapsayan sınıfa verin.

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