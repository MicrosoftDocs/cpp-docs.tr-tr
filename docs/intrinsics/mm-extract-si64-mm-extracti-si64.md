---
title: _mm_extract_si64, _mm_extracti_si64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _mm_extracti_si64
- _mm_extract_si64
dev_langs:
- C++
helpviewer_keywords:
- extrq instruction
- _mm_extracti_si64 intrinsic
- _mm_extract_si64 intrinsic
ms.assetid: 459fdd72-cc54-4ee5-bbd5-d2c6067a88e7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4bc65289ce52be9acb1cfe01d1149480a8381e3b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="mmextractsi64-mmextractisi64"></a>_mm_extract_si64, _mm_extracti_si64
**Microsoft Specific**  
  
 Oluşturur `extrq` belirtilen BITS düşük 64 bitten ilk bağımsız değişkenin değerini ayıklamak için yönerge.  
  
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
 [in] `Source`  
 Kendi alt 64 bit giriş verilerini 128-bit alanıyla.  
  
 [in] `Descriptor`  
 Ayıklanacak bit alan açıklar 128-bit alanı.  
  
 [in] `Length`  
 Ayıklanacak alanının uzunluğunu belirten bir tamsayı.  
  
 [in] `Index`  
 Ayıklanacak alanın dizinini belirten bir tamsayı  
  
## <a name="return-value"></a>Dönüş Değeri  
 En az önemli BITS ayıklanan alanında 128-bit alanıyla.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_mm_extract_si64`|SSE4a|  
|`_mm_extracti_si64`|SSE4a|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Bu iç oluşturur `extrq` bitten ayıklamak için yönerge `Source`. İç bu iki sürümü vardır: `_mm_extracti_si64` hemen sürümü ve `_mm_extract_si64` hemen olmayan adrestir.  Gelen her sürümü ayıklar `Source` uzunluğu ve en az önemli bit dizini tarafından tanımlanan bir bit alanı. Dizin ve uzunluk değerler mod 64 alınır, böylece -1 ile 127 63 yorumlanır. (Sınırlı) dizin ve (sınırlı) alan uzunluğu toplamı 64'den büyükse, sonuçları tanımlanmamış. Alan uzunluğu için sıfır değeri 64 yorumlanır. Alan uzunluğu ve bit dizini hem sıfır, BITS 63:0 varsa `Source` ayıklanır. Alan uzunluğu sıfır ancak bit dizin sıfır değilse, sonuçları tanımlanmamış.  
  
 _Mm_extract_si64, çağrıda `Descriptor` BITS 13:8 ve BITS 5:0 olarak ayıklanacak veri alanı uzunluğu dizinini içeren...  
  
 Çağırırsanız `_mm_extracti_si64` derleyici tamsayı sabitleri olmasını belirleyemiyor bağımsız değişkenlerle derleyici bu değerleri XMM kayıt paketi için kod oluşturur (`Descriptor`) ve çağırmak için `_mm_extract_si64`.  
  
 Donanım desteğini belirlemek için `extrq` yönerge, çağrı `__cpuid` ile iç `InfoType=0x80000001` ve bit 6 denetleyin `CPUInfo[2] (ECX)`. Bu bit aksi yönerge destekleniyorsa 1 ve 0 olacaktır. Desteklemediği iç bu donanım kullanan kodu çalıştırırsanız `extrq` yönerge, sonuçlar tahmin edilemez.  
  
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
  
**SON Microsoft özel**  
 Gelişmiş Mikro Aygıtlar, Inc. Telif Hakkı 2007 Tüm hakları saklıdır. Gelişmiş Mikro Aygıtlar, Inc. izinle çoğaltılamaz  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_mm_insert_si64, _mm_inserti_si64](../intrinsics/mm-insert-si64-mm-inserti-si64.md)   
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)