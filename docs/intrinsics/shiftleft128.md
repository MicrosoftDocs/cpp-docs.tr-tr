---
title: __shiftleft128 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __shiftleft128
dev_langs:
- C++
helpviewer_keywords:
- __shiftleft128 intrinsic
ms.assetid: 557b846a-8fb0-469d-91ac-1b1fad80dc2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57846bab53e50f1644dcdc3ec817472e47793840
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725211"
---
# <a name="shiftleft128"></a>__shiftleft128
**Microsoft'a özgü**  
  
 İki 64-bit miktarlar olarak temsil edilen bir 128-bit miktarı kaydırır `LowPart` ve `HighPart`, sol tarafından belirtilen bit sayısı `Shift` ve yüksek 64 bit sonuç döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned __int64 __shiftleft128(   
   unsigned __int64 LowPart,   
   unsigned __int64 HighPart,   
   unsigned char Shift   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
*Alt kısım*<br/>
[in] Kaydırmak için 128 bit miktarı düşük 64 bit.  
  
*HighPart*<br/>
[in] Yüksek 64 bit kaydırmak için 128 bit miktarı.  
  
*Kaydırma*<br/>
[in] Kaydırılacak bit sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sonuç yüksek 64 bit.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__shiftleft128`|X64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 `Shift` Değerdir her zaman 64 bu nedenle, örneğin, çağırırsanız `__shiftleft128(1, 0, 64)`, işlev düşük bölümü kayar `0` BITS yüksek bir parçası olarak döndürmek ve sola `0` ve `1` aksi beklenebilir gibi.  
  
## <a name="example"></a>Örnek  
  
```  
// shiftleft128.c  
// processor: IPF, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic (__shiftleft128, __shiftright128)  
  
int main()  
{  
    unsigned __int64 i = 0x1I64;  
    unsigned __int64 j = 0x10I64;  
    unsigned __int64 ResultLowPart;  
    unsigned __int64 ResultHighPart;  
  
    ResultLowPart = i << 1;  
    ResultHighPart = __shiftleft128(i, j, 1);  
  
    // concatenate the low and high parts padded with 0's  
    // to display correct hexadecimal 128 bit values  
    printf_s("0x%02I64x%016I64x << 1 = 0x%02I64x%016I64x\n",  
             j, i, ResultHighPart, ResultLowPart);  
  
    ResultHighPart = j >> 1;  
    ResultLowPart = __shiftright128(i, j, 1);  
  
    printf_s("0x%02I64x%016I64x >> 1 = 0x%02I64x%016I64x\n",  
             j, i, ResultHighPart, ResultLowPart);    
}  
```  
  
```Output  
0x100000000000000001 << 1 = 0x200000000000000002  
0x100000000000000001 >> 1 = 0x080000000000000000  
```  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__shiftright128](../intrinsics/shiftright128.md)   
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)