---
title: restrict (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- cpu_CPP
- amp_CPP
helpviewer_keywords:
- restrict clause (C++ AMP)
ms.assetid: 07d3291f-7edf-456b-8828-283ac8673661
ms.openlocfilehash: 3609e3f0541cfd8a8af8559d8d49e6a77c00d91c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403392"
---
# <a name="restrict-c-amp"></a>restrict (C++ AMP)

Kısıtlama tanımlayıcısı işlev ve lambda bildirimlerine uygulanabilir. C++ Accelerated Massive Parallelism (C++ AMP) çalışma zamanı kullanan uygulamalarda işlevdeki kod ve işlevin davranışı için kısıtlamalar uygular.

> [!NOTE]
>  Hakkında bilgi için **kısıtlama** parçası olan anahtar sözcüğü **__declspec** depolama sınıfı öznitelikleri [kısıtlama](../cpp/restrict.md).

**Kısıtlama** yan tümcesi aşağıdaki biçimleri alır:

|Yan Tümce|Açıklama|
|------------|-----------------|
|`restrict(cpu)`|İşlev tam C++ dilini kullanabilir. İşlevi yalnızca restrict(cpu) işlevleri kullanılarak bildirilen diğer işlevler çağırabilir.|
|`restrict(amp)`|İşlev, yalnızca C++ AMP'nin hızlandırabileceği C++ dilinin alt kümesini kullanabilir.|
|Bir `restrict(cpu)` ve `restrict(amp)` dizisi.|İşlev hem `restrict(cpu)` hem de `restrict(amp)` kısıtlamalarına uymalıdır. İşlev, `restrict(cpu)`,  `restrict(amp)`, `restrict(cpu, amp)` veya `restrict(amp, cpu)` kullanılarak bildirilen işlevler tarafından çağrılabilir.<br /><br /> `restrict(A) restrict(B)` biçimi `restrict(A,B)` olarak yazılabilir.|

## <a name="remarks"></a>Açıklamalar

**Kısıtlama** anahtar sözcüğü bağlamsal bir sözcüktür. Kısıtlama tanımlayıcıları `cpu` ve `amp`, ayrılmış sözcükler değildir. Tanımlayıcıların listesi genişletilemez. Sahip olmayan bir işlev bir **kısıtlama** yan tümcesi olan bir işlev ile aynı ise `restrict(cpu)` yan tümcesi.

`restrict(amp)` yan tümcesine sahip bir işlev aşağıdaki kısıtlamalara sahiptir:

- İşlev yalnızca `restrict(amp)` yan tümcesine sahip işlevleri çağırabilir.

- İşlev satır içine alınabilir olmalıdır.

- İşlevi yalnızca bildirebilirsiniz **int**, **işaretsiz int**, **float**, ve **çift** değişkenleri, sınıf ve yalnızca içeren yapıları Bu tür. **bool** da izin verilir, ancak bir bileşen türünde kullanıyorsanız 4 bayt hizalı olmalıdır.

- Lambda işlevleri, başvuruya göre yakalama gerçekleştiremez ve işaretçileri yakalayamaz.

- Başvurular ve tek yöneltmeli işaretçiler, yalnızca yerel değişkenler, işlev bağımsız değişkenleri ve dönüş türleri olarak desteklenir.

- Aşağıdakilere izin verilmez:

   - Yineleme.

   - Değişkenleri [geçici](../cpp/volatile-cpp.md) anahtar sözcüğü.

   - Sanal işlevler.

   - İşlev işaretçileri.

   - Üye işlevlerinin işaretçileri.

   - Yapılar içerisindeki işaretçiler.

   - İşaretçilerin işaretçileri.

   - **goto** deyimleri.

   - Etiketli deyimler.

   - **deneyin**, **catch**, veya **throw** deyimleri.

   - Genel değişkenler.

   - Statik değişkenler. Kullanım [tile_static anahtar sözcüğü](../cpp/tile-static-keyword.md) yerine.

   - **dynamic_cast** yayınlar.

   - **TypeID** işleci.

   - asm bildirimleri.

   - Varargs.

İşlev kısıtlamaları için bkz [(amp) kısıtlamaları kısıtlama](https://blogs.msdn.microsoft.com/nativeconcurrency/2011/12/19/restrictamp-restrictions-part-0-of-n-introduction/).

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `restrict(amp)`yan tümcesi.

```cpp
void functionAmp() restrict(amp) {}
void functionNonAmp() {}

void callFunctions() restrict(amp)
{
    // int is allowed.
    int x;
    // long long int is not allowed in an amp-restricted function. This generates a compiler error.
    // long long int y;

    // Calling an amp-restricted function is allowed.
    functionAmp();

    // Calling a non-amp-restricted function is not allowed.
    // functionNonAmp();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)