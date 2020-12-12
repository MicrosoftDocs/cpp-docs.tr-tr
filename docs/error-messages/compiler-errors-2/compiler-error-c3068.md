---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3068'
title: Derleyici hatası C3068
ms.date: 11/04/2016
f1_keywords:
- C3068
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
ms.openlocfilehash: a73c525f017a3d571600e31d4c9ea875d0b25662
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281684"
---
# <a name="compiler-error-c3068"></a>Derleyici hatası C3068

' function ': bir ' Naked ' işlevi bir C++ özel durumu oluştuğunda geriye doğru izleme gerektirecek nesneler içeremez

Derleyici, işlevde geçici bir nesne oluşturulduğu ve C++ özel durum işleme ([/EHsc](../../build/reference/eh-exception-handling-model.md)) belirtildiği için bir özel durum oluşturan, [çıplak](../../cpp/naked-cpp.md) bir işlevde yığın geri sarma işlemi yapamadı.

Bu hatayı çözmek için aşağıdakilerden en az birini yapın:

- /EHsc. ile derleme kullanmayın.

- İşlevi olarak işaretlemeyin `naked` .

- İşlevde geçici bir nesne oluşturmayın.

Bir işlev yığında geçici bir nesne oluşturursa, işlev bir özel durum oluşturursa ve C++ özel durum işleme etkinse, bir özel durum oluşturulursa derleyici yığını temizler.

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
