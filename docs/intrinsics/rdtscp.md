---
title: __rdtscp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __rdtscp
dev_langs:
- C++
helpviewer_keywords:
- rdtscp intrinsic
- __rdtscp intrinsic
- rdtscp instruction
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d890afe9e19782f19442e8d95709b91a8680278
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33329809"
---
# <a name="rdtscp"></a>__rdtscp
**Microsoft özel**  
  
 Oluşturur `rdtscp` yönerge Yazar `TSC_AUX[31:0`] bellek ve 64-bit zaman damgası sayacı döndürür (`TSC)` sonucu.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned __int64 __rdtscp(  
   unsigned int * Aux  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out] `Aux`  
 İşaretçi makineye özgü kayıt içeriğini içeren bir konuma `TSC_AUX[31:0]`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir 64-bit işaretsiz tamsayı değer sayısı.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__rdtscp`|AMD NPT ailesi ten 0Fh veya sonraki sürümler|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Bu iç oluşturur `rdtscp` yönergesi. Bu yönerge donanım desteğini belirlemek için arama `__cpuid` ile iç `InfoType=0x80000001` ve biti 27 denetleyin `CPUInfo[3] (EDX)`. Bu yönerge destekleniyorsa 1 ve 0 aksi bitidir.  Kullanan kodu bu iç desteklemediği donanımda çalıştırırsanız `rdtscp` yönerge, sonuçlar tahmin edilemez.  
  
> [!CAUTION]
>  Farklı `rdtsc`, `rdtscp` biçimlendiricisi yönerge; olması yine de, bu geçici kod derleyici taşıyabilirsiniz iç.  
  
 ' In önceki sürümlerinde TSC değeri yorumu donanım bu oluşturmada farklı [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)].  Donanım kılavuzlarına daha fazla bilgi için bkz.  
  
 Değer anlamını `TSC_AUX[31:0]` işletim sistemine bağlıdır.  
  
## <a name="example"></a>Örnek  
  
```  
#include <intrin.h>   
#include <stdio.h>  
int main()   
{  
 unsigned __int64 i;  
 unsigned int ui;  
 i = __rdtscp(&ui);  
 printf_s("%I64d ticks\n", i);  
 printf_s("TSC_AUX was %x\n", ui);  
}  
```  
  
```Output  
3363423610155519 ticks  
TSC_AUX was 0  
```  
  
**SON Microsoft özel**  
 Gelişmiş Mikro Aygıtlar, Inc. Telif Hakkı 2007 Tüm hakları saklıdır. Gelişmiş Mikro Aygıtlar, Inc. izinle çoğaltılamaz  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__rdtsc](../intrinsics/rdtsc.md)   
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)