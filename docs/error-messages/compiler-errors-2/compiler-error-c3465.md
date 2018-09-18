---
title: Derleyici Hatası C3465 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3465
dev_langs:
- C++
helpviewer_keywords:
- C3465
ms.assetid: aeb815e5-b3fc-4525-afe2-d738e9321df1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6aa388d95904aecc8e1ba558b374249bb280e02
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048987"
---
# <a name="compiler-error-c3465"></a>Derleyici Hatası C3465

türü 'type' kullanmak için ' % s'derleme 'derlemesi' başvurusu

İstemci yeniden derleyin kadar tür iletme istemci uygulaması için çalışır. Yeniden derleme yaptığınızda, istemci uygulamanızda kullanılan bir tür tanımını içeren her derleme için başvuru gerekir.

Daha fazla bilgi için [tür iletme (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md).

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