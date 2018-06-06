---
title: Derleyici Hatası C2712 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2712
dev_langs:
- C++
helpviewer_keywords:
- C2712
ms.assetid: f7d4ffcc-7ed2-459b-8067-a728ce647071
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27db5f8ae3fd56078a3085c8d216e7dd34edb2fc
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704262"
---
# <a name="compiler-error-c2712"></a>Derleyici Hatası C2712

> Kullanım nesne geriye doğru izleme gerektiren işlevlerde __try olamaz

## <a name="remarks"></a>Açıklamalar

Hata C2712 kullanırsanız oluşabilir [/EHsc](../../build/reference/eh-exception-handling-model.md), ve unwinding (yok etme) gerektiren nesnelerini ayrıca yapılandırılmış özel durum işleme ile bir işleve sahiptir.

Olası çözümler:

- Başka bir işleve SEH gerektiren kod taşıma

- Yerel değişkenleri ve Yıkıcılar sahip parametreleri kullanımını önlemek için SEH kullanan işlevler yeniden yazın. SEH oluşturucular veya Yıkıcılar kullanmayın

- /EHsc derleme

Hata C2712 da gerçekleşebilir kullanarak bildirilen bir yöntem çağrısı [__event](../../cpp/event.md) anahtar sözcüğü. Olay birden çok iş parçacıklı bir ortamda kullanılabilir olduğundan derleyici, olay nesnesini işlenmesini önler ve ardından bir SEH oluşturulan kodu alır kodunu oluşturur [try-finally deyimi](../../cpp/try-finally-statement.md). Sonuç olarak, olay yöntemini çağırın ve değerine göre bir yıkıcı olan türüne sahip bağımsız değişken geçirin halinde hata C2712 ortaya çıkar. Bir çözümü bu durumda bağımsız değişkeni sabit bir başvuru olarak geçirmektir.

C2712 da gerçekleşebilir ile derleme **/CLR: pure** ve işaretçileri işlevlerinin içinde statik bir dizi bildirme bir `__try` bloğu. Statik bir üyenin derleyicinin altında dinamik başlatma kullanmasını gerektirir **/CLR: pure**, C++ özel durum işleme anlamına gelir. Ancak, C++ özel durum işleme izin verilmez bir `__try` bloğu.

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2712 oluşturur ve nasıl düzeltileceği gösterir.

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