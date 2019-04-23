---
title: _mm_extract_si64, _mm_extracti_si64
ms.date: 11/04/2016
f1_keywords:
- _mm_extracti_si64
- _mm_extract_si64
helpviewer_keywords:
- extrq instruction
- _mm_extracti_si64 intrinsic
- _mm_extract_si64 intrinsic
ms.assetid: 459fdd72-cc54-4ee5-bbd5-d2c6067a88e7
ms.openlocfilehash: e77ca5589ed50a4199921603afec1d9888c6cca5
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59040218"
---
# <a name="mmextractsi64-mmextractisi64"></a>_mm_extract_si64, _mm_extracti_si64

**Microsoft'a özgü**

Oluşturur `extrq` ilk bağımsız değişkeninin düşük 64 bit görüntüyü belirtilen BITS ayıklanacak yönergesi.

## <a name="syntax"></a>Sözdizimi

```
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

#### <a name="parameters"></a>Parametreler

*Kaynak*<br/>
[in] 128-bit alanı alt, 64 bit giriş verileri.

*Tanımlayıcı*<br/>
[in] Ayıklanacak bit alanı açıklar 128-bit alanı.

*Uzunluğu*<br/>
[in] Ayıklanacak alan uzunluğunu belirten bir tamsayı.

*Index*<br/>
[in] Ayıklanacak alan dizinini belirten bir tamsayı

## <a name="return-value"></a>Dönüş Değeri

128-bit alanı, en az önemli bitlerin ayıklanan alanıyla.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`_mm_extract_si64`|SSE4a|
|`_mm_extracti_si64`|SSE4a|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu iç oluşturur `extrq` bitten ayıklamak için yönerge `Source`. İç bu iki sürümü vardır: `_mm_extracti_si64` hemen sürümü ve `_mm_extract_si64` hemen olmayan bir sertifikadır.  Her sürüm ayıklar `Source` , en az önemli bit dizinini ve uzunluğu ile tanımlanan bir bit alanı. Değerlerin dizinini ve uzunluğu 64 mod alınır, böylece hem -1 ile 127 63 yorumlanır. (Daraltılmış) dizin ve (daraltılmış) alan uzunluğu 64 ' büyükse sonuçlar tanımsızdır. Alan uzunluğu sıfır değerini 64 yorumlanır. Alan uzunluğu ve bit dizini iki sıfır, BITS 63:0 varsa `Source` ayıklanır. Alan uzunluğu sıfır ancak bit dizin sıfır olmayan, sonuçlar tanımsızdır.

_Mm_extract_si64, bir çağrıda `Descriptor` BITS 13:8 ve BITS 5:0 ayıklanacak veri alanı uzunluğu dizin içeren...

Eğer `_mm_extracti_si64` derleyici tamsayı sabitleri olmasını belirlenemiyor bağımsız değişkenlerle derleyici bu değerleri bir XMM kaydı paketlemek için kod oluşturur. (`Descriptor`) ve çağırmak için `_mm_extract_si64`.

İçin donanım desteği belirlemek için `extrq` yönerge, çağrı `__cpuid` ile iç `InfoType=0x80000001` ve 6 bit `CPUInfo[2] (ECX)`. Bu bit aksi yönerge destekleniyorsa 1 ve 0 olacaktır. Desteklemediği bu iç donanım kullanan kodu çalıştırırsanız `extrq` yönergesi, sonuçların tahmin edilemeyeceğine.

## <a name="example"></a>Örnek

```
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

**END Microsoft özgü**

Telif Hakkı 2007 Gelişmiş Micro cihazlar, Inc. Tüm hakları saklıdır. Gelişmiş Micro cihazlar, Inc. izniyle üretilemez

## <a name="see-also"></a>Ayrıca bkz.

[_mm_insert_si64, _mm_inserti_si64](../intrinsics/mm-insert-si64-mm-inserti-si64.md)<br/>
[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)