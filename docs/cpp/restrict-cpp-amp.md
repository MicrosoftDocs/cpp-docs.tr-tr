---
title: restrict (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- cpu_CPP
- amp_CPP
helpviewer_keywords:
- restrict clause (C++ AMP)
ms.assetid: 07d3291f-7edf-456b-8828-283ac8673661
ms.openlocfilehash: 31db9e8c6f18879e65596593c10a8b3413c5cea9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213274"
---
# <a name="restrict-c-amp"></a>restrict (C++ AMP)

Kısıtlama tanımlayıcısı işlev ve lambda bildirimlerine uygulanabilir. C++ Accelerated Massive Parallelism (C++ AMP) çalışma zamanı kullanan uygulamalarda işlevdeki kod ve işlevin davranışı için kısıtlamalar uygular.

> [!NOTE]
> **`restrict`** Depolama sınıfı özniteliklerinin bir parçası olan anahtar sözcük hakkında daha fazla bilgi için **`__declspec`** bkz. [Restrict](../cpp/restrict.md).

**`restrict`** Yan tümcesi aşağıdaki formları alır:

|Yan Tümce|Açıklama|
|------------|-----------------|
|`restrict(cpu)`|İşlev tam C++ dilini kullanabilir. İşlevi yalnızca restrict(cpu) işlevleri kullanılarak bildirilen diğer işlevler çağırabilir.|
|`restrict(amp)`|İşlev, yalnızca C++ AMP'nin hızlandırabileceği C++ dilinin alt kümesini kullanabilir.|
|Bir `restrict(cpu)` ve `restrict(amp)` dizisi.|İşlev hem `restrict(cpu)` hem de `restrict(amp)` kısıtlamalarına uymalıdır. İşlev, `restrict(cpu)`,  `restrict(amp)`, `restrict(cpu, amp)` veya `restrict(amp, cpu)` kullanılarak bildirilen işlevler tarafından çağrılabilir.<br /><br /> `restrict(A) restrict(B)` biçimi `restrict(A,B)` olarak yazılabilir.|

## <a name="remarks"></a>Açıklamalar

**`restrict`** Anahtar sözcüğü bağlamsal bir anahtar sözcüktür. Kısıtlama tanımlayıcıları `cpu` ve `amp`, ayrılmış sözcükler değildir. Tanımlayıcıların listesi genişletilemez. Yan tümcesine sahip olmayan bir işlev, **`restrict`** yan tümcesine sahip bir işlevle aynıdır `restrict(cpu)` .

`restrict(amp)` yan tümcesine sahip bir işlev aşağıdaki kısıtlamalara sahiptir:

- İşlev yalnızca `restrict(amp)` yan tümcesine sahip işlevleri çağırabilir.

- İşlev satır içine alınabilir olmalıdır.

- İşlev yalnızca,,, **`int`** **`unsigned int`** **`float`** ve **`double`** değişkenlerini ve yalnızca bu türleri içeren sınıfları ve yapıları bildirebilir. **`bool`** Ayrıca buna izin verilir, ancak bileşik bir tür içinde kullanıyorsanız 4 baytlık hizalı olmalıdır.

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

  - **`goto`** deyimler.

  - Etiketli deyimler.

  - **`try`**, **`catch`** , veya **`throw`** deyimleri.

  - Genel değişkenler.

  - Statik değişkenler. Bunun yerine [Tile_static anahtar sözcüğünü](../cpp/tile-static-keyword.md) kullanın.

  - **`dynamic_cast`** Podcast.

  - **`typeid`** İşleci.

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
