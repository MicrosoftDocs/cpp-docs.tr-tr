---
title: Derleyici Hatası C2712
ms.date: 11/04/2016
f1_keywords:
- C2712
helpviewer_keywords:
- C2712
ms.assetid: f7d4ffcc-7ed2-459b-8067-a728ce647071
ms.openlocfilehash: 19b9c5a54bf405114bd4d596c2a2cc4708aadcc9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386797"
---
# <a name="compiler-error-c2712"></a>Derleyici Hatası C2712

> Kullanım nesne geriye doğru izleme gerektiren işlevlerde __try kullanılamaz

## <a name="remarks"></a>Açıklamalar

Hatası C2712 kullanıyorsanız gerçekleşebilir [/ehsc](../../build/reference/eh-exception-handling-model.md), ve geriye doğru izleme (yok etme) gerektiren nesnelerini de yapılandırılmış özel durum işleme ile bir işleve sahiptir.

Olası çözümler:

- Başka bir işleve SEH gerektiren kodu Taşı

- Yerel değişkenleri ve yok ediciler olan parametreler kullanımını önlemek için SEH kullanan işlevler yeniden yazın. SEH oluşturucuları veya yıkıcıları kullanma

- / Ehsc derleme

Hatası C2712 kullanılarak bildirilen bir yöntem çağırırsanız da gerçekleşebilir [__event](../../cpp/event.md) anahtar sözcüğü. Derleyici, olay nesnesini işlenmesini önler ve ardından SEH oluşturulan kodu alır kod oluşturur, olay birden çok iş parçacıklı bir ortamda kullanılıyor olabilir çünkü [try-finally deyimi](../../cpp/try-finally-statement.md). Sonuç olarak, olay yöntemini çağırın ve türü bir yok Edicisi olan bağımsız değişken değere göre geçirin hatası C2712 oluşacaktır. Tek bir çözüm bağımsız değişkeni sabit bir başvuru geçirmek için bu durumda olur.

C2712 ile derleme yaparsanız da gerçekleşebilir **/CLR: pure** ve işaretçileri işlevleri statik bir diziyi bildirmek bir `__try` blok. Dinamik olarak başlatılması altında kullanılacak derleyici bir statik üye gerektirir **/CLR: pure**, C++ özel durum işleme anlamına gelir. Bununla birlikte, C++ özel durum işleme izin verilmiyor bir `__try` blok.

**/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2712 oluşturur ve bu sorunun nasıl gösterir.

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