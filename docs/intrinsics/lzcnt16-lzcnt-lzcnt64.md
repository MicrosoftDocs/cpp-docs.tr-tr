---
title: __lzcnt16, __lzcnt, __lzcnt64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __lzcnt64
- __lzcnt16
- __lzcnt
dev_langs:
- C++
helpviewer_keywords:
- __lzcnt intrinsic
- lzcnt instruction
- lzcnt16 intrinsic
- lzcnt intrinsic
- __lzcnt16 intrinsic
- lzcnt64 intrinsic
- __lzcnt64 intrinsic
ms.assetid: 412113e7-052e-46e5-8bfa-d5ad72abc10e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86e04182cf673674e1f1ba8c073b624760bc4809
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="lzcnt16-lzcnt-lzcnt64"></a>__lzcnt16, __lzcnt, __lzcnt64
**Microsoft özel**  
  
 Sayıları başında sayısı 16-, 32 veya 64 bit tamsayı sıfırlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned short __lzcnt16(  
   unsigned short value  
);  
unsigned int __lzcnt(  
   unsigned int value  
);  
unsigned __int64 __lzcnt64(  
   unsigned __int64 value  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `value`  
 16, 32 veya 64 bit işaretsiz tamsayıyı baştaki sıfırlarla taramak için.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sıfır bit cinsinden baştaki sayısı `value` parametresi. Varsa `value` sıfırsa, dönüş değeri giriş işleneni (16, 32 veya 64) boyutudur. Varsa, en önemli biti `value` biri, dönüş değeri sıfırdır.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__lzcnt16`|AMD: Gelişmiş Bit işleme (ABM)<br /><br /> Intel: Haswell|  
|`__lzcnt`|AMD: Gelişmiş Bit işleme (ABM)<br /><br /> Intel: Haswell|  
|`__lzcnt64`|AMD: Bit işleme (ABM) 64 bit modunda Gelişmiş.<br /><br /> Intel: Haswell|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı her oluşturur `lzcnt` yönergesi.  Değeri, `lzcnt` yönergesi verir bağımsız değişkeni boyutu ile aynı.  32-bit modunda Hayır 64-bit hiçbir 64-bit genel amaçlı kayıtları, bu nedenle vardır `lzcnt`.  
  
 Donanım desteğini belirlemek için `lzcnt` yönerge çağrısı `__cpuid` ile iç `InfoType=0x80000001` ve bit 5 denetleyin `CPUInfo[2] (ECX)`. Bu bit aksi yönerge destekleniyorsa 1 ve 0 olacaktır. Kullanan kodu bu iç desteklemediği donanımda çalıştırırsanız `lzcnt` yönerge, sonuçlar tahmin edilemez.  
  
 Desteklemeyen Intel işlemcileri üzerinde `lzcnt` yönerge olarak yürütüldüğünde yönerge bayt kodlaması `bsr` (bit tarama tersine). Kod taşınabilirlik önemliyse kullanımını göz önünde bulundurun `_BitScanReverse` iç yerine. Daha fazla bilgi için bkz: [_BitScanReverse, _BitScanReverse64](../intrinsics/bitscanreverse-bitscanreverse64.md).  
  
## <a name="example"></a>Örnek  
  
```  
// Compile this test with: /EHsc  
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
    usr = __lzcnt16(us[i]);  
    cout << "__lzcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;  
  }  
  
  for (int i=0; i<4; i++) {  
    uir = __lzcnt(ui[i]);  
    cout << "__lzcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;  
  }  
}  
  
```  
  
```Output  
__lzcnt16(0x0) = 16  
__lzcnt16(0xff) = 8  
__lzcnt16(0xffff) = 0  
__lzcnt(0x0) = 32  
__lzcnt(0xff) = 24  
__lzcnt(0xffff) = 16  
__lzcnt(0xffffffff) = 0  
```  
  
**SON Microsoft özel**  
 Bu içerik bölümlerini Gelişmiş Mikro Aygıtlar, Inc. Telif Hakkı 2007 olan Tüm hakları saklıdır. Gelişmiş Mikro Aygıtlar, Inc. izinle çoğaltılamaz  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)
