---
description: 'Hakkında daha fazla bilgi edinin: _mm_extract_si64 _mm_extracti_si64'
title: _mm_extract_si64, _mm_extracti_si64
ms.date: 09/02/2019
f1_keywords:
- _mm_extracti_si64
- _mm_extract_si64
helpviewer_keywords:
- extrq instruction
- _mm_extracti_si64 intrinsic
- _mm_extract_si64 intrinsic
ms.assetid: 459fdd72-cc54-4ee5-bbd5-d2c6067a88e7
ms.openlocfilehash: 39a07c7310727de8d752c060c3d38481469ff1a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322873"
---
# <a name="_mm_extract_si64-_mm_extracti_si64"></a>_mm_extract_si64, _mm_extracti_si64

**Microsoft'a Özgü**

`extrq`İlk bağımsız değişkeninin düşük 64 bitinden belirtilen bitleri ayıklama yönergesini üretir.

## <a name="syntax"></a>Sözdizimi

```C
__m128i _mm_extract_si64(
   __m128i Source,
   __m128i Descriptor
);
__m128i _mm_extracti_si64(
   __m128i Source,
   int Length,
   int Index
);
```

### <a name="parameters"></a>Parametreler

*Kaynaktaki*\
'ndaki Daha düşük 64 bitine girdi verileri olan 128 bitlik bir alan.

*CI*\
'ndaki Ayıklanacak bit alanını açıklayan 128 bitlik bir alan.

*Uzunluklu*\
'ndaki Ayıklanacak alanın uzunluğunu belirten bir tamsayı.

*İndeks*\
'ndaki Ayıklanacak alanın dizinini belirten bir tamsayı

## <a name="return-value"></a>Döndürülen değer

En az önemli bit içindeki ayıklanan alana sahip 128 bitlik bir alan.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_mm_extract_si64`|SSE4a|
|`_mm_extracti_si64`|SSE4a|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu iç bilgiler, `extrq` *kaynaktan* bitleri ayıklama yönergesini oluşturur. İki sürüm vardır: Bu, `_mm_extracti_si64` en yakın sürümdür ve `_mm_extract_si64` tek bir sürümlerdir. Her sürüm, kendi uzunluğuna ve en az önemli bit dizinine göre tanımlanan bir bit alanı *kaynağından* ayıklar. Uzunluk ve Dizin değerleri mod 64 ' a alınır, bu nedenle hem-1 hem de 127, 63 olarak yorumlanır. (Azaltılmış) dizin ve (azaltılmış) alanı uzunluğunun toplamı 64 ' den büyükse, sonuçlar tanımsızdır. Alan uzunluğu için sıfır değeri 64 olarak yorumlanır. Alan uzunluğu ve bit dizini her ikisi de sıfırsa, *kaynak* bitleri 63:0 çıkarılır. Alan uzunluğu sıfırsa ancak bit dizini sıfır değilse, sonuçlar tanımsızdır.

Bir çağrısında `_mm_extract_si64` , *tanımlayıcı* , BITS 13:8 ' deki dizini ve BITS 5:0 ' de Ayıklanacak verilerin alan uzunluğunu içerir.

`_mm_extracti_si64`Derleyicinin tamsayı sabitleri belirleyemediğini tespit eden bağımsız değişkenlerle birlikte çağırırsanız, derleyici bu değerleri BIR XMM kaydına (*tanımlayıcısına*) paketetmek ve çağırmak için kod üretir `_mm_extract_si64` .

Yönergeyle ilgili donanım desteğini öğrenmek için, `extrq` `__cpuid` ile iç öğesini çağırın `InfoType=0x80000001` ve bit 6 ' yı denetleyin `CPUInfo[2] (ECX)` . Yönerge destekleniyorsa bu bit 1 olur, aksi takdirde 0 olur. Yönergeyi desteklemeyen bu iç donanımı kullanan kodu çalıştırırsanız `extrq` , sonuçlar tahmin edilemez olur.

## <a name="example"></a>Örnek

```cpp
// Compile this sample with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

union {
    __m128i m;
    unsigned __int64 ui64[2];
} source, descriptor, result1, result2, result3;

int
main()
{
    source.ui64[0] =     0xfedcba9876543210ll;
    descriptor.ui64[0] = 0x0000000000000b1bll;

    result1.m = _mm_extract_si64 (source.m, descriptor.m);
    result2.m = _mm_extracti_si64(source.m, 27, 11);
    result3.ui64[0] = (source.ui64[0] >> 11) & 0x7ffffff;

    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;
    cout << "result2 = 0x" << result2.ui64[0] << endl;
    cout << "result3 = 0x" << result3.ui64[0] << endl;
}
```

```Output
result1 = 0x30eca86
result2 = 0x30eca86
result3 = 0x30eca86
```

**SON Microsoft 'a özgü**

Bölüm Telif hakkı 2007 Advanced Micro Devices, Inc. Tüm hakları saklıdır. Gelişmiş mikro cihazlar, Inc. izniyle yeniden üretilme.

## <a name="see-also"></a>Ayrıca bkz.

[_mm_insert_si64, _mm_inserti_si64](../intrinsics/mm-insert-si64-mm-inserti-si64.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
