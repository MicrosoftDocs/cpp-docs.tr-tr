---
title: Derleyici Hatası C3068
ms.date: 11/04/2016
f1_keywords:
- C3068
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
ms.openlocfilehash: 4790c9caafd28722f3631104cfe5cfc762cf6426
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575480"
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