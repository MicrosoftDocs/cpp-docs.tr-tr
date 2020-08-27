---
title: Derleyici hatası C2712
description: Microsoft C/C++ derleyicisi hata C2712 açıklar.
ms.date: 08/25/2020
f1_keywords:
- C2712
helpviewer_keywords:
- C2712
ms.assetid: f7d4ffcc-7ed2-459b-8067-a728ce647071
ms.openlocfilehash: 2f0b883607241473a429919e06de9e975fa2e3c1
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898691"
---
# <a name="compiler-error-c2712"></a>Derleyici hatası C2712

> `__try`nesne geriye doğru izleme gerektiren işlevlerde kullanılamaz

## <a name="remarks"></a>Açıklamalar

Kullanırsanız hata C2712 oluşabilir [`/EHsc`](../../build/reference/eh-exception-handling-model.md) ve yapılandırılmış özel durum işleme içeren bir işlev aynı zamanda geriye doğru izleme (yok etme) gerektiren nesneler de vardır.

Olası çözümler:

- SEH gerektiren kodu başka bir işleve taşıma

- Yerel değişkenlerin ve yıkıcıları olan parametrelerin kullanımını önlemek için SEH kullanan işlevleri yeniden yazın. Oluşturucuları veya yıkıcılarda SEH kullanmayın

- /EHsc olmadan derle

Anahtar sözcüğü kullanılarak belirtilen bir yöntemi çağırırsanız hata C2712 da oluşabilir [`__event`](../../cpp/event.md) . Etkinlik çok iş parçacıklı bir ortamda kullanılabilir olabileceğinden, derleyici temel olay nesnesinin düzenlenmesini engelleyen bir kod oluşturur ve sonra oluşturulan kodu bir SEH [ `try-finally` ifadesinde](../../cpp/try-finally-statement.md)barındırır. Sonuç olarak, Event metodunu çağırdığınızda ve değer olarak, türü yok edici olan bir bağımsız değişken ile geçirirseniz hata C2712 oluşur. Bu durumda bir çözüm, bağımsız değişkeni sabit bir başvuru olarak iletmektir.

C2712, ile derleme yaptığınızda **`/clr:pure`** ve bir blok içindeki işaretçilerden işlevlere statik bir dizi bildirdiğinizde da oluşabilir **`__try`** . Statik bir üye, derleyicinin altında dinamik başlatma kullanmasını gerektirir **`/clr:pure`** , bu da C++ özel durum işleme anlamına gelir. Ancak, bir blokta C++ özel durum işlemeye izin verilmez **`__try`** .

**`/clr:pure`** Ve **`/clr:safe`** derleyici seçenekleri visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2712 oluşturur ve nasıl düzeltileceğini gösterir.

```cpp
// C2712.cpp
// compile with: /clr:pure /c
struct S1 {
   static int smf();
   void fnc();
};

void S1::fnc() {
   __try {
      static int (*array_1[])() = {smf,};   // C2712

      // OK
      static int (*array_2[2])();
      array_2[0] = smf;
    }
    __except(0) {}
}
```
