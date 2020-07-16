---
title: restrict (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- cpu_CPP
- amp_CPP
helpviewer_keywords:
- restrict clause (C++ AMP)
ms.assetid: 07d3291f-7edf-456b-8828-283ac8673661
ms.openlocfilehash: b3464b758c6b66cdbd5015ee4b7c9d11eb2209dd
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404944"
---
# <a name="restrict-c-amp"></a>restrict (C++ AMP)

Kısıtlama tanımlayıcısı işlev ve lambda bildirimlerine uygulanabilir. C++ Accelerated Massive Parallelism (C++ AMP) çalışma zamanı kullanan uygulamalarda işlevdeki kod ve işlevin davranışı için kısıtlamalar uygular.

> [!NOTE]
> **__Declspec** Storage sınıfı özniteliklerinin parçası olan **Restrict** anahtar sözcüğü hakkında bilgi için bkz. [Restrict](../cpp/restrict.md).

**Restrict** yan tümcesi aşağıdaki formları alır:

|Yan Tümce|Açıklama|
|------------|-----------------|
|`restrict(cpu)`|İşlev tam C++ dilini kullanabilir. İşlevi yalnızca restrict(cpu) işlevleri kullanılarak bildirilen diğer işlevler çağırabilir.|
|`restrict(amp)`|İşlev, yalnızca C++ AMP'nin hızlandırabileceği C++ dilinin alt kümesini kullanabilir.|
|Bir `restrict(cpu)` ve `restrict(amp)` dizisi.|İşlev hem `restrict(cpu)` hem de `restrict(amp)` kısıtlamalarına uymalıdır. İşlev, `restrict(cpu)`,  `restrict(amp)`, `restrict(cpu, amp)` veya `restrict(amp, cpu)` kullanılarak bildirilen işlevler tarafından çağrılabilir.<br /><br /> `restrict(A) restrict(B)` biçimi `restrict(A,B)` olarak yazılabilir.|

## <a name="remarks"></a>Açıklamalar

**Restrict** anahtar sözcüğü bağlamsal bir anahtar sözcüktür. Kısıtlama tanımlayıcıları `cpu` ve `amp`, ayrılmış sözcükler değildir. Tanımlayıcıların listesi genişletilemez. **Restrict** yan tümcesine sahip olmayan bir işlev, yan tümcesine sahip bir işlevle aynıdır `restrict(cpu)` .

`restrict(amp)` yan tümcesine sahip bir işlev aşağıdaki kısıtlamalara sahiptir:

- İşlev yalnızca `restrict(amp)` yan tümcesine sahip işlevleri çağırabilir.

- İşlev satır içine alınabilir olmalıdır.

- İşlev yalnızca **int**, **işaretsiz int**, **float**ve **Double** değişkenlerini ve yalnızca bu türleri içeren sınıfları ve yapıları bildirebilir. **bool** öğesine de izin verilir, ancak bunu bir bileşik türde kullanıyorsanız 4 baytlık hizalı olmalıdır.

- Lambda işlevleri, başvuruya göre yakalama gerçekleştiremez ve işaretçileri yakalayamaz.

- Başvurular ve tek yöneltmeli işaretçiler, yalnızca yerel değişkenler, işlev bağımsız değişkenleri ve dönüş türleri olarak desteklenir.

- Aşağıdakilere izin verilmez:

  - Yineleme.

  - [Volatile](../cpp/volatile-cpp.md) anahtar sözcüğüyle belirtilen değişkenler.

  - Sanal işlevler.

  - İşlev işaretçileri.

  - Üye işlevlerinin işaretçileri.

  - Yapılar içerisindeki işaretçiler.

  - İşaretçilerin işaretçileri.

  - **goto** deyimleri.

  - Etiketli deyimler.

  - **TRY**, **catch**veya **throw** deyimleri.

  - Genel değişkenler.

  - Statik değişkenler. Bunun yerine [Tile_static anahtar sözcüğünü](../cpp/tile-static-keyword.md) kullanın.

  - **dynamic_cast** yayınları.

  - **TypeId** işleci.

  - asm bildirimleri.

  - Varargs.

İşlev sınırlamalarıyla ilgili bir tartışma için bkz. [restrict (amp) kısıtlamaları](/archive/blogs/nativeconcurrency/restrictamp-restrictions-part-0-of-n-introduction).

## <a name="example"></a>Örnek

Aşağıdaki örnek, yan tümcesinin nasıl kullanılacağını göstermektedir `restrict(amp)` .

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
