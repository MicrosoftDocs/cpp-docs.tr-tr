---
title: Derleyici hatası C2712
ms.date: 11/04/2016
f1_keywords:
- C2712
helpviewer_keywords:
- C2712
ms.assetid: f7d4ffcc-7ed2-459b-8067-a728ce647071
ms.openlocfilehash: a25c59fa5c9ba0102666f6c8922a61b063e7627a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202312"
---
# <a name="compiler-error-c2712"></a>Derleyici hatası C2712

> nesne geriye doğru izleme gerektiren işlevlerde __try kullanılamaz

## <a name="remarks"></a>Açıklamalar

[/EHsc](../../build/reference/eh-exception-handling-model.md)kullanırsanız hata C2712 oluşabilir ve yapılandırılmış özel durum işleme içeren bir işlev aynı zamanda geriye doğru izleme (yok etme) gerektiren nesneler de içerebilir.

Olası çözümler:

- SEH gerektiren kodu başka bir işleve taşıma

- Yerel değişkenlerin ve yıkıcıları olan parametrelerin kullanımını önlemek için SEH kullanan işlevleri yeniden yazın. Oluşturucuları veya yıkıcılarda SEH kullanmayın

- /EHsc olmadan derle

[__Event](../../cpp/event.md) anahtar sözcüğünü kullanarak belirtilen bir yöntemi çağırırsanız hata C2712 de oluşabilir. Etkinlik çok iş parçacıklı bir ortamda kullanılabilir olabileceğinden, derleyici temel olay nesnesinin düzenlenmesini engelleyen bir kod oluşturur ve sonra oluşturulan kodu bir SEH [try-finally ifadesinde](../../cpp/try-finally-statement.md)barındırır. Sonuç olarak, Event metodunu çağırdığınızda ve değer olarak, türü yok edici olan bir bağımsız değişken ile geçirirseniz hata C2712 oluşur. Bu durumda bir çözüm, bağımsız değişkeni sabit bir başvuru olarak iletmektir.

C2712, **/clr: Pure** ile derleme yaptığınızda ve bir `__try` bloğunda işlev işaretçilerinden statik bir dizi bildirdiğinizde da oluşabilir. Statik bir üye, derleyicinin **/clr: Pure**altında dinamik başlatma kullanmasını gerektirir, bu da özel C++ durum işleme anlamına gelir. Ancak, C++ `__try` bloğunda özel durum işlemeye izin verilmez.

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

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
