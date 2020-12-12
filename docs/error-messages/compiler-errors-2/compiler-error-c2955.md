---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2955'
title: Derleyici hatası C2955
ms.date: 03/28/2017
f1_keywords:
- C2955
helpviewer_keywords:
- C2955
ms.assetid: 77709fb6-d69b-46fd-a62f-e8564563d01b
ms.openlocfilehash: 0d81410aaf9b111b8c601a28ef50d5c4d377d5f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210627"
---
# <a name="compiler-error-c2955"></a>Derleyici hatası C2955

' tanımlayıcı ': sınıf şablonu veya diğer ad genel kullanım için şablon veya genel bağımsız değişken listesi gerekir

Şablon veya genel bağımsız değişken listesi olmayan bir sınıf şablonu veya sınıf genel bir tanımlayıcı olarak kullanamazsınız.

Daha fazla bilgi için bkz. [sınıf şablonları](../../cpp/class-templates.md).

Aşağıdaki örnek C2955 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2955.cpp
// compile with: /c
template<class T>
class X {};

X x1;   // C2955
X<int> x2;   // OK - this is how to fix it.
```

Ayrıca, bir sınıf şablonunda bildirildiği bir işlev için satır dışı bir tanım denenirken C2955 de oluşabilir:

```cpp
// C2955_b.cpp
// compile with: /c
template <class T>
class CT {
public:
   void CTFunc();
   void CTFunc2();
};

void CT::CTFunc() {}   // C2955

// OK - this is how to fix it
template <class T>
void CT<T>::CTFunc2() {}
```

C2955, genel türler kullanılırken de oluşabilir:

```cpp
// C2955_c.cpp
// compile with: /clr
generic <class T>
ref struct GC {
   T t;
};

int main() {
   GC^ g;   // C2955
   GC <int>^ g;
}
```

## <a name="example"></a>Örnek

**Visual Studio 2017 ve üzeri:** Şablon bir şablon parametre listesinde (örneğin, varsayılan bir şablon bağımsız değişkeninin veya tür olmayan bir şablon parametresi) göründüğünde derleyici, eksik şablon bağımsız değişken listelerini doğru bir şekilde tanılar. Aşağıdaki kod Visual Studio 2015 ' de derlenir ancak Visual Studio 2017 ' de bir hata oluşturur.

```
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```
