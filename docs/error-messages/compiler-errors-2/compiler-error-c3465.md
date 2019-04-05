---
title: Derleyici Hatası C3465
ms.date: 11/04/2016
f1_keywords:
- C3465
helpviewer_keywords:
- C3465
ms.assetid: aeb815e5-b3fc-4525-afe2-d738e9321df1
ms.openlocfilehash: 117c9b9918950fd2e95e206c5aea457dee183b0a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781581"
---
# <a name="compiler-error-c3465"></a>Derleyici Hatası C3465

türü 'type' kullanmak için ' % s'derleme 'derlemesi' başvurusu

İstemci yeniden derleyin kadar tür iletme istemci uygulaması için çalışır. Yeniden derleme yaptığınızda, istemci uygulamanızda kullanılan bir tür tanımını içeren her derleme için başvuru gerekir.

Daha fazla bilgi için [tür iletme (C + +/ CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir tür yeni konumunu içeren bir bütünleştirilmiş kod oluşturur.

```
// C3465.cpp
// compile with: /clr /LD
public ref class R {
public:
   ref class N {};
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, türü tanımı kapsamak için kullanılmış bir derleme oluşturur, ancak artık türü için iletme söz dizimi içeriyor.

```
// C3465_b.cpp
// compile with: /clr /LD
#using "C3465.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3465 oluşturur.

```
// C3465_c.cpp
// compile with: /clr
// C3465 expected
#using "C3465_b.dll"
// Uncomment the following line to resolve.
// #using "C3465.dll"

int main() {
   R^ r = gcnew R();
}
```