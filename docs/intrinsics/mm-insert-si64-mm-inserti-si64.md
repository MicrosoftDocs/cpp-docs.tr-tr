---
title: _mm_insert_si64, _mm_inserti_si64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_inserti_si64
- _mm_insert_si64
dev_langs:
- C++
helpviewer_keywords:
- insertq instruction
- _mm_insert_si64 intrinsic
- _mm_inserti_si64 intrinsic
ms.assetid: 897a4b36-8b08-4b00-a18f-7850f5732d7d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f859b461a2072afabbe48126eba94e0a3ed470a3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403872"
---
# <a name="mminsertsi64-mminsertisi64"></a>_mm_insert_si64, _mm_inserti_si64

**Microsoft'a özgü**

Oluşturur `insertq` BITS ikinci işleneniyle ilk işleneni eklemek için yönerge.

## <a name="syntax"></a>Sözdizimi

```
__m128i _mm_insert_si64(
   __m128i Source1,
   __m128i Source2
);
__m128i _mm_inserti_si64(
   __m128i Source1,
   __m128i Source2
   int Length,
   int Index
);
```

#### <a name="parameters"></a>Parametreler

*Kaynak1*<br/>
[in] 128-bit alanı, daha düşük bir alan eklenecek olan 64bitový giriş verileri.

*Kaynak2*<br/>
[in] 128-bit alanı ile düşük bit'leri eklenecek veri.  İçin `_mm_insert_si64`, ayrıca bir alan tanımlayıcısı, yüksek bit içerir.

*Uzunluğu*<br/>
[in] Eklemek için alan uzunluğunu belirten bir tamsayı sabiti.

*Index*<br/>
[in] Alanın veri eklenecek olan en az önemli bite dizinini belirten bir tamsayı sabiti.

## <a name="return-value"></a>Dönüş Değeri

Daha düşük olan 64 bit içeren özgün düşük 64 bit bir 128-bit alanı `Source1` düşük bitleri tarafından belirtilen bit alanı ile değiştirilen `Source2`. Üst 64 bit geri dönüş değeri tanımsızdır.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`_mm_insert_si64`|SSE4a|
|`_mm_inserti_si64`|SSE4a|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu iç oluşturur `insertq` bitten eklemek için talimat `Source2` içine `Source1`. İç bu iki sürümü vardır: `_mm_inserti_si64`, hemen sürümü ve `_mm_insert_si64` hemen olmayan bir sertifikadır.  Her sürüm kaynak2 belirtilen uzunlukta bir bit alanı ayıklar ve kaynak1 ekler.  Ayıklanan kaynak2 en az önemli bitlerini bittir.  Bu bit eklenecek olan alan kaynak1, en az önemli bit dizinini ve uzunluğu ile tanımlanır.  Değerlerin dizinini ve uzunluğu 64 mod alınır, böylece hem -1 ile 127 63 yorumlanır. (Daraltılmış) bit dizini ve (daraltılmış) alan uzunluğu 64 ' büyükse, sonuçlar tanımsızdır. Alan uzunluğu sıfır değerini 64 yorumlanır.  Alan uzunluğu ve bit dizini iki sıfır, BITS 63:0 varsa `Source2` eklendiği `Source1`.  Alan uzunluğu sıfır ancak bit dizin sıfır olmayan, sonuçlar tanımsızdır.

Alan uzunluğu _mm_insert_si64 çağrısı içinde BITS 77:72 kaynak2 ve BITS 69:64 dizininde yer alır.

Eğer `_mm_inserti_si64` derleyici tamsayı sabitleri olmasını belirlenemiyor bağımsız değişkenleri ile derleyici bu değerleri bir XMM yazmacına paketi ve çağırmak için kod oluşturur. `_mm_insert_si64`.

İçin donanım desteği belirlemek için `insertq` yönerge çağrı `__cpuid` ile iç `InfoType=0x80000001` ve 6 bit `CPUInfo[2] (ECX)`. Bu bit aksi yönerge destekleniyorsa 1 ve 0 olacaktır. Kullanan kodu bu iç desteği olmayan donanım üzerinde çalıştırdığınız varsa `insertq` yönergesi, sonuçların tahmin edilemeyeceğine.

## <a name="example"></a>Örnek

```
// Compile this sample with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

union {
    __m128i m;
    unsigned __int64 ui64[2];
} source1, source2, source3, result1, result2, result3;

int
main()
{

    __int64 mask;

    source1.ui64[0] = 0xffffffffffffffffll;
    source2.ui64[0] = 0xfedcba9876543210ll;
    source2.ui64[1] = 0xc10;
    source3.ui64[0] = source2.ui64[0];

    result1.m = _mm_insert_si64 (source1.m, source2.m);
    result2.m = _mm_inserti_si64(source1.m, source3.m, 16, 12);
    mask = 0xffff << 12;
    mask = ~mask;
    result3.ui64[0] = (source1.ui64[0] & mask) |
                      ((source2.ui64[0] & 0xffff) << 12);

    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;
    cout << "result2 = 0x" << result2.ui64[0] << endl;
    cout << "result3 = 0x" << result3.ui64[0] << endl;

}
```

```Output
result1 = 0xfffffffff3210fff
result2 = 0xfffffffff3210fff
result3 = 0xfffffffff3210fff
```

**END Microsoft özgü**

Telif Hakkı 2007 Gelişmiş Micro cihazlar, Inc. Tüm hakları saklıdır. Gelişmiş Micro cihazlar, Inc. izniyle üretilemez

## <a name="see-also"></a>Ayrıca Bkz.

[_mm_extract_si64, _mm_extracti_si64](../intrinsics/mm-extract-si64-mm-extracti-si64.md)<br/>
[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)