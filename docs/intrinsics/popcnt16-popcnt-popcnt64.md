---
title: __popcnt16, __popcnt, __popcnt64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __popcnt64
- __popcnt
- __popcnt16
dev_langs:
- C++
helpviewer_keywords:
- popcnt instruction
- __popcnt16
- __popcnt64
- __popcnt
ms.assetid: e525b236-adc8-42df-9b9b-8b7d8c245d3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 34063223addb433a94c877ad56cf410f189e6681
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45724743"
---
# <a name="popcnt16-popcnt-popcnt64"></a>__popcnt16, __popcnt, __popcnt64

**Microsoft'a özgü**  
  
 Bir sayar BITS (nüfus sayımı) bir 16, 32 veya 64 bayt işaretsiz tamsayı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned short __popcnt16(  
   unsigned short value  
);  
unsigned int __popcnt(  
   unsigned int value  
);  
unsigned __int64 __popcnt64(  
   unsigned __int64 value  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
*value*<br/>
[in] 16, 32 veya 64-bit işaretsiz tamsayı nüfus sayımı istiyoruz.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir bit sayısı `value` parametresi.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__popcnt16`|Gelişmiş Bit işleme|  
|`__popcnt`|Gelişmiş Bit işleme|  
|`__popcnt64`|64 bit modunda Gelişmiş Bit işleme.|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Her biri bu iç oluşturur `popcnt` yönergesi.  Değer boyutu, `popcnt` yönerge boyutu bağımsız olarak aynı döndürür.  32 bit modunda 64 bit Hayır 64-bit genel amaçlı yazmaç yok, bu nedenle vardır `popcnt`.  
  
 İçin donanım desteği belirlemek için `popcnt` yönerge, çağrı `__cpuid` ile iç `InfoType=0x00000001` ve 23 bit `CPUInfo[2] (ECX)`. Bu bit Aksi takdirde yönerge destekleniyorsa 1 ve 0 olur. Kullanan kodu bu iç desteği olmayan donanım üzerinde çalıştırdığınız varsa `popcnt` yönergesi, sonuçların tahmin edilemeyeceğine.  
  
## <a name="example"></a>Örnek  
  
```  
#include <iostream>   
#include <intrin.h>   
using namespace std;   
  
int main()   
{  
  unsigned short us[3] = {0, 0xFF, 0xFFFF};  
  unsigned short usr;  
  unsigned int   ui[4] = {0, 0xFF, 0xFFFF, 0xFFFFFFFF};  
  unsigned int   uir;  
  
  for (int i=0; i<3; i++) {  
    usr = __popcnt16(us[i]);  
    cout << "__popcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;  
  }  
  
  for (int i=0; i<4; i++) {  
    uir = __popcnt(ui[i]);  
    cout << "__popcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;  
  }  
}  
  
```  
  
```Output  
__popcnt16(0x0) = 0  
__popcnt16(0xff) = 8  
__popcnt16(0xffff) = 16  
__popcnt(0x0) = 0  
__popcnt(0xff) = 8  
__popcnt(0xffff) = 16  
__popcnt(0xffffffff) = 32  
```  
  
**END Microsoft özgü**  

Telif Hakkı 2007 Gelişmiş Micro cihazlar, Inc. Tüm hakları saklıdır. Gelişmiş Micro cihazlar, Inc. izniyle üretilemez  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)
