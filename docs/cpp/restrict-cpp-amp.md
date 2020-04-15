---
title: restrict (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- cpu_CPP
- amp_CPP
helpviewer_keywords:
- restrict clause (C++ AMP)
ms.assetid: 07d3291f-7edf-456b-8828-283ac8673661
ms.openlocfilehash: 5a0011d11e4a59c9ca3a5e18f44d4cf831b21582
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366652"
---
# <a name="restrict-c-amp"></a>restrict (C++ AMP)

Kısıtlama tanımlayıcısı işlev ve lambda bildirimlerine uygulanabilir. C++ Accelerated Massive Parallelism (C++ AMP) çalışma zamanı kullanan uygulamalarda işlevdeki kod ve işlevin davranışı için kısıtlamalar uygular.

> [!NOTE]
> **__declspec** depolama sınıfı özniteliklerinin bir parçası olan **kısıtlama** anahtar sözcüğü hakkında bilgi [için](../cpp/restrict.md)bkz.

**Kısıtlama** maddesi aşağıdaki formları alır:

|Yan Tümce|Açıklama|
|------------|-----------------|
|`restrict(cpu)`|İşlev tam C++ dilini kullanabilir. İşlevi yalnızca restrict(cpu) işlevleri kullanılarak bildirilen diğer işlevler çağırabilir.|
|`restrict(amp)`|İşlev, yalnızca C++ AMP'nin hızlandırabileceği C++ dilinin alt kümesini kullanabilir.|
|Bir `restrict(cpu)` ve `restrict(amp)` dizisi.|İşlev hem `restrict(cpu)` hem de `restrict(amp)` kısıtlamalarına uymalıdır. İşlev, `restrict(cpu)`,  `restrict(amp)`, `restrict(cpu, amp)` veya `restrict(amp, cpu)` kullanılarak bildirilen işlevler tarafından çağrılabilir.<br /><br /> `restrict(A) restrict(B)` biçimi `restrict(A,B)` olarak yazılabilir.|

## <a name="remarks"></a>Açıklamalar

**Kısıtlama** anahtar kelimesi bağlamsal bir anahtar kelimedir. Kısıtlama tanımlayıcıları `cpu` ve `amp`, ayrılmış sözcükler değildir. Tanımlayıcıların listesi genişletilemez. **Kısıtlama** yan tümcesi olmayan bir işlev, `restrict(cpu)` yan tümcesi olan bir işlevle aynıdır.

`restrict(amp)` yan tümcesine sahip bir işlev aşağıdaki kısıtlamalara sahiptir:

- İşlev yalnızca `restrict(amp)` yan tümcesine sahip işlevleri çağırabilir.

- İşlev satır içine alınabilir olmalıdır.

- İşlev yalnızca **int,** **imzasız int,** **float**ve **çift** değişkenleri ve yalnızca bu türleri içeren sınıfları ve yapıları bildirebilir. **bool** de izin verilir, ancak bileşik bir tür de kullanırsanız 4-bayt hizalanmış olmalıdır.

- Lambda işlevleri, başvuruya göre yakalama gerçekleştiremez ve işaretçileri yakalayamaz.

- Başvurular ve tek yöneltmeli işaretçiler, yalnızca yerel değişkenler, işlev bağımsız değişkenleri ve dönüş türleri olarak desteklenir.

- Aşağıdakilere izin verilmez:

  - Yineleme.

  - [Değişken](../cpp/volatile-cpp.md) anahtar kelime ile bildirilen değişkenler.

  - Sanal işlevler.

  - İşlev işaretçileri.

  - Üye işlevlerinin işaretçileri.

  - Yapılar içerisindeki işaretçiler.

  - İşaretçilerin işaretçileri.

  - **goto** ifadeler.

  - Etiketli deyimler.

  - **deneyin,** **yakalayın**veya ifadeleri **atın.**

  - Genel değişkenler.

  - Statik değişkenler. Bunun yerine [tile_static Anahtar Kelime](../cpp/tile-static-keyword.md) kullanın.

  - **dynamic_cast** alçı.

  - **Typeid** işleci.

  - asm bildirimleri.

  - Varargs.

İşlev sınırlamalarının tartışılması için, [kısıtlama (amp) Kısıtlamaları'na](https://blogs.msdn.microsoft.com/nativeconcurrency/2011/12/19/restrictamp-restrictions-part-0-of-n-introduction/)bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, yan tümcenin nasıl kullanılacağını `restrict(amp)`gösterir.

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
