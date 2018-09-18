---
title: Derleyici Hatası C3068 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3068
dev_langs:
- C++
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fdea26e204032c27f00639ee46a928c7bf084a4e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035632"
---
# <a name="compiler-error-c3068"></a>Derleyici Hatası C3068

'function': 'naked' işlev C++ özel durumu oluştuğunda geriye doğru izleme gerektirecek nesneler içeremez

Derleyicinin yığın üzerinde geriye doğru izleme gerçekleştiremedi bir [naked](../../cpp/naked-cpp.md) geçici bir nesne işlevi ve C++ özel durum işleme oluşturulduğundan, bir özel durum belirtti işlevi ([/ehsc](../../build/reference/eh-exception-handling-model.md)) belirtildi.

Bu hatayı gidermek için en az aşağıdakilerden birini yapın:

- / Ehsc ile derlenmiyor.

- İşlev olarak işaretlemeyin `naked`.

- Geçici bir nesne işlevinde oluşturmayın.

Geçici bir nesne yığını üzerinde işlev bir özel durum oluşturursa ve C++ özel durum işleme etkinse, bir işlev oluşturur, derleyici bir özel durum oluşturulursa yığını temizler.

Bir özel durum, derleyici oluşturulan kod, giriş adlı ve epilog ve, çıplak bir işlev mevcut olmayan bir işlev için yürütülür.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3068 oluşturur:

```
// C3068.cpp
// compile with: /EHsc
// processor: x86
class A {
public:
   A(){}
   ~A(){}
};

void b(A){}

__declspec(naked) void c() {
   b(A());   // C3068
};
```