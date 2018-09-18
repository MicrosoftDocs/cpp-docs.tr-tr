---
title: Derleyici Hatası C2955 | Microsoft Docs
ms.custom: ''
ms.date: 03/28/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2955
dev_langs:
- C++
helpviewer_keywords:
- C2955
ms.assetid: 77709fb6-d69b-46fd-a62f-e8564563d01b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c9d9817a2b78638868242c5c5642a89fb41d93c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051951"
---
# <a name="compiler-error-c2955"></a>Derleyici Hatası C2955

'identifier': sınıf şablonu kullanın veya diğer genel şablon veya genel bağımsız değişken listesi gerektiriyor

Bir sınıf şablonu ya da genel bir sınıf, şablon veya genel bağımsız değişken listesi olmayan bir tanımlayıcı olarak kullanamazsınız.

Daha fazla bilgi için [sınıf şablonlarının](../../cpp/class-templates.md).

Aşağıdaki örnek, C2955 oluşturur ve bu sorunun nasıl gösterir:

```
// C2955.cpp
// compile with: /c
template<class T>
class X {};

X x1;   // C2955
X<int> x2;   // OK - this is how to fix it.
```

C2955 da bir sınıf şablonu olarak bildirilen bir işlev için bir satır dışı tanımı çalışırken meydana gelebilir:

```
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

C2955, genel türler kullanırken da meydana gelebilir:

```
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

**Visual Studio 2017 ve üzeri:** şablonu (örneğin parçası varsayılan şablon bağımsız değişkeni veya bir tür olmayan şablon parametresi) bir şablon parametre listesinde göründüğünde derleyici doğru eksik şablon bağımsız değişken listeleri tanılar. Aşağıdaki kod, Visual Studio 2015'te derler ancak Visual Studio 2017'de bir hata oluşturur.

```
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```
