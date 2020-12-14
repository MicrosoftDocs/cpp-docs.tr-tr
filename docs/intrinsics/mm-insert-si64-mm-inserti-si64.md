---
description: 'Hakkında daha fazla bilgi edinin: _mm_insert_si64 _mm_inserti_si64'
title: _mm_insert_si64, _mm_inserti_si64
ms.date: 09/02/2019
f1_keywords:
- _mm_inserti_si64
- _mm_insert_si64
helpviewer_keywords:
- insertq instruction
- _mm_insert_si64 intrinsic
- _mm_inserti_si64 intrinsic
ms.assetid: 897a4b36-8b08-4b00-a18f-7850f5732d7d
ms.openlocfilehash: 96ddf9a8836dcb927a09a51e0b2818b2a040c9d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345270"
---
# <a name="_mm_insert_si64-_mm_inserti_si64"></a>_mm_insert_si64, _mm_inserti_si64

**Microsoft'a Özgü**

`insertq`İkinci işleneninden bitleri ilk işlenene ekleme yönergesini üretir.

## <a name="syntax"></a>Sözdizimi

```C
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

### <a name="parameters"></a>Parametreler

*Source1*\
'ndaki Bir alanın ekleneceği, daha düşük 64 bitine girdi verileri olan 128 bitlik bir alan.

*Source2*\
'ndaki Düşük bitlerinde eklenecek verilere sahip 128 bitlik bir alan.  İçin `_mm_insert_si64` , yüksek bitleriyle bir alan tanımlayıcısı da içerir.

*Uzunluklu*\
'ndaki Eklenecek alanın uzunluğunu belirten bir tamsayı sabiti.

*İndeks*\
'ndaki Verilerin ekleneceği alanın en az önemli bitinin dizinini belirten bir tamsayı sabiti.

## <a name="return-value"></a>Döndürülen değer

Düşük 64 bit, *source1*' nin orijinal düşük 64 bitlerini içeren 128 bitlik bir alan, belirtilen bit alanıyla aynı *SOURCE2* düşük bitleriyle değiştirilmiştir. Dönüş değerinin üst 64 bitleri tanımsız.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_mm_insert_si64`|SSE4a|
|`_mm_inserti_si64`|SSE4a|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu iç bilgiler, `insertq` *SOURCE2* 'den *source1*'e bit ekleme yönergesini oluşturur. İki sürüm vardır: `_mm_inserti_si64` , en yakın sürümdür ve `_mm_insert_si64` tek bir sürümdür. Her sürüm, SOURCE2 adresinden verilen uzunluktaki bir bit alanını ayıklar ve source1 'e ekler.  Ayıklanan bitler, SOURCE2 'in en az önemli bitleridir.  Bu bitlerin ekleneceği alan source1, en az önemli bitin uzunluğu ve dizini tarafından tanımlanır.  Uzunluk ve Dizin değerleri mod 64 ' a alınır, bu nedenle hem-1 hem de 127, 63 olarak yorumlanır. (Azaltılmış) bit dizini ve (azaltılmış) alanı uzunluğunun toplamı 64 ' den büyükse, sonuçlar tanımsızdır. Alan uzunluğu için sıfır değeri 64 olarak yorumlanır. Alan uzunluğu ve bit dizini her ikisi de sıfırsa, *SOURCE2* bit 63:0 ' ye *source1* eklenir. Alan uzunluğu sıfırsa, ancak bit dizini sıfır değilse, sonuçlar tanımsızdır.

_Mm_insert_si64 çağrısında, alan uzunluğu SOURCE2 bit 77:72 ' de ve bit 69:64 ' deki dizinde bulunur.

`_mm_inserti_si64`Derleyicinin tamsayı sabitleri belirleyemediğini tespit eden bağımsız değişkenlerle birlikte çağırırsanız, derleyici bu değerleri BIR XMM kaydına paketetmek ve çağırmak için kod üretir `_mm_insert_si64` .

Yönergeyle ilgili donanım desteğini öğrenmek için, `insertq` `__cpuid` ile iç öğesini çağırın `InfoType=0x80000001` ve bit 6 ' yı denetleyin `CPUInfo[2] (ECX)` . Yönerge destekleniyorsa bu bit 1, değilse 0 ' dır. Yönergeyi desteklemeyen bir donanım kullanan kodu çalıştırırsanız `insertq` , sonuçlar tahmin edilemez olur.

## <a name="example"></a>Örnek

```cpp
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

**SON Microsoft 'a özgü**

Bölüm Telif hakkı 2007 Advanced Micro Devices, Inc. Tüm hakları saklıdır. Gelişmiş mikro cihazlar, Inc. izniyle yeniden üretilme.

## <a name="see-also"></a>Ayrıca bkz.

[_mm_extract_si64, _mm_extracti_si64](../intrinsics/mm-extract-si64-mm-extracti-si64.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
