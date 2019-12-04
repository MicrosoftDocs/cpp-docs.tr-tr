---
title: Derleyici hatası C3068
ms.date: 11/04/2016
f1_keywords:
- C3068
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
ms.openlocfilehash: 9e20333a4fc18219f7f2514f3aefe73b81f284a6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759496"
---
# <a name="compiler-error-c3068"></a>Derleyici hatası C3068

' function ': ' Naked ' işlevi bir C++ özel durum oluştuysa geriye doğru izleme gerektirecek nesneler içeremez

Derleyici, işlevde geçici bir nesne oluşturulduğu ve C++ özel durum işleme ([/EHsc](../../build/reference/eh-exception-handling-model.md)) belirtildiği için bir özel durum oluşturan bir [çıplak](../../cpp/naked-cpp.md) işlevde yığın geri sarma işlemi yapamadı.

Bu hatayı çözmek için aşağıdakilerden en az birini yapın:

- /EHsc. ile derleme kullanmayın.

- İşlevi `naked`olarak işaretlemeyin.

- İşlevde geçici bir nesne oluşturmayın.

Bir işlev yığında geçici bir nesne oluşturursa, işlev bir özel durum oluşturursa ve C++ özel durum işleme etkinse, bir özel durum oluşturulursa, derleyici yığını temizler.

Bir özel durum oluştuğunda, giriş ve bitiş olarak adlandırılan ve çıplak işlevde bulunmayan derleyici tarafından oluşturulan kod, bir işlev için yürütülür.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3068 oluşturur:

```cpp
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
