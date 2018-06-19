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
ms.openlocfilehash: 72597007922e78ab9b83687cb5b80bd6ecef7d01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33338201"
---
# <a name="mminsertsi64-mminsertisi64"></a>_mm_insert_si64, _mm_inserti_si64
**Microsoft özel**  
  
 Oluşturur `insertq` BITS, ikinci işlenen kendi ilk işlenen eklemek için yönerge.  
  
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
 [in] `Source1`  
 Kendi alt 64 alana eklenecek olan BITS giriş verilerini 128-bit alanıyla.  
  
 [in]  `Source2`  
 Düşük bit'leri eklenecek veri 128-bit alanıyla.  İçin `_mm_insert_si64`, ayrıca bir alan tanımlayıcısı yüksek bit cinsinden içerir.  
  
 [in]  `Length`  
 Eklenecek alanın uzunluğu belirten tamsayı sabiti.  
  
 [in]  `Index`  
 En az önemli bit veri eklenecek olan alanın dizinini belirten bir tamsayı sabiti.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Daha düşük olan 64 bit içeren özgün düşük 64 bit düzeyi 128-bit alan `Source1` belirtilen bit alanıyla yerini tarafından düşük bit `Source2`. Dönüş değeri üst 64 bit tanımlanmamış.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_mm_insert_si64`|SSE4a|  
|`_mm_inserti_si64`|SSE4a|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Bu iç oluşturur `insertq` bitten eklemek için yönerge `Source2` içine `Source1`. İç bu iki sürümü vardır: `_mm_inserti_si64`, hemen sürümü ve `_mm_insert_si64` hemen olmayan adrestir.  Her sürümün belirtilen uzunlukta bir bit alanı kaynak2 ayıklar ve kaynak1 ekler.  Ayıklanan kaynak2 en az önemli bitleri bittir.  Bu BITS eklenecek olan alan kaynak1 uzunluğu ve en az önemli bit dizini tarafından tanımlanır.  Dizin ve uzunluk değerler mod 64 alınır, böylece -1 ile 127 63 yorumlanır. (Sınırlı) bit dizin ve (sınırlı) alan uzunluğu toplamı 64'den büyükse, sonuçları tanımlanmamış. Alan uzunluğu için sıfır değeri 64 yorumlanır.  Alan uzunluğu ve bit dizini hem sıfır, BITS 63:0 varsa `Source2` eklenir `Source1`.  Alan uzunluğu sıfır ancak bit dizin sıfır değilse, sonuçları tanımlanmamış.  
  
 _Mm_insert_si64 için bir çağrı alan uzunluğu BITS 77:72 kaynak2 ve BITS 69:64 dizininde bulunur.  
  
 Çağırırsanız `_mm_inserti_si64` derleyici tamsayı sabitleri olmasını belirleyemiyor bağımsız değişkenlerle derleyici bu değerleri XMM yazmaç paketlemek için ve çağırmak için kodu oluşturur. `_mm_insert_si64`.  
  
 Donanım desteğini belirlemek için `insertq` yönerge çağrısı `__cpuid` ile iç `InfoType=0x80000001` ve bit 6 denetleyin `CPUInfo[2] (ECX)`. Bu bit aksi yönerge destekleniyorsa 1 ve 0 olacaktır. Kullanan kodu bu iç desteklemediği donanımda çalıştırırsanız `insertq` yönerge, sonuçlar tahmin edilemez.  
  
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
  
**SON Microsoft özel**  
 Gelişmiş Mikro Aygıtlar, Inc. Telif Hakkı 2007 Tüm hakları saklıdır. Gelişmiş Mikro Aygıtlar, Inc. izinle çoğaltılamaz  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_mm_extract_si64, _mm_extracti_si64](../intrinsics/mm-extract-si64-mm-extracti-si64.md)   
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)