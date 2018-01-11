---
title: __popcnt16, __popcnt, __popcnt64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __popcnt64
- __popcnt
- __popcnt16
dev_langs: C++
helpviewer_keywords:
- popcnt instruction
- __popcnt16
- __popcnt64
- __popcnt
ms.assetid: e525b236-adc8-42df-9b9b-8b7d8c245d3b
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 45e60a412dc24f685fd375ebc19c109b2bee0e2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="popcnt16-popcnt-popcnt64"></a>__popcnt16, __popcnt, __popcnt64
**Microsoft özel**  
  
 Bir sayar 16-, 32 veya 64 baytlık bir işaretsiz tamsayı BITS (popülasyon sayısı).  
  
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
 [in]`value`  
 16, 32 veya 64 bit işaretsiz tamsayıyı popülasyon sayısı istiyoruz.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir bit sayısı `value` parametresi.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__popcnt16`|Gelişmiş Bit düzenleme|  
|`__popcnt`|Gelişmiş Bit düzenleme|  
|`__popcnt64`|Gelişmiş Bit düzenlemesi 64-bit modunda.|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı her oluşturur `popcnt` yönergesi.  Değeri, `popcnt` yönergesi verir bağımsız değişkeni boyutu ile aynı.  32-bit modunda Hayır 64-bit hiçbir 64-bit genel amaçlı kayıtları, bu nedenle vardır `popcnt`.  
  
 Donanım desteğini belirlemek için `popcnt` yönerge, çağrı `__cpuid` ile iç `InfoType=0x00000001` ve biti 23 denetleyin `CPUInfo[2] (ECX)`. Bu yönerge destekleniyorsa 1 ve 0 aksi bitidir. Kullanan kodu bu iç desteklemediği donanımda çalıştırırsanız `popcnt` yönerge, sonuçlar tahmin edilemez.  
  
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
__oopcnt(0xffff) = 16  
__popcnt(0xffffffff) = 32  
```  
  
**SON Microsoft özel**  
 Gelişmiş Mikro Aygıtlar, Inc. Telif Hakkı 2007 Tüm hakları saklıdır. Gelişmiş Mikro Aygıtlar, Inc. izinle çoğaltılamaz  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)