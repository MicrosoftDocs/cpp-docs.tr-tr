---
title: _rotr8, _rotr16 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _rotr16
- _rotr8
dev_langs:
- C++
helpviewer_keywords:
- _rotr8 intrinsic
- _rotr16 intrinsic
ms.assetid: dfbd2c82-82b4-427a-ad52-51609027ebff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 936113d2b59bf089179c6f0c016c8a91c5edc74d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715825"
---
# <a name="rotr8-rotr16"></a>_rotr8, _rotr16
**Microsoft'a özgü**  
  
 Giriş değerleri tarafından belirtilen bit konumları sayısı en az önemli bite (LSB'si) Sağa Döndür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned char _rotr8(   
   unsigned char value,   
   unsigned char shift   
);  
unsigned short _rotr16(   
   unsigned short value,   
   unsigned char shift   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
*value*<br/>
[in] Döndürülecek değer.  
  
*Kaydırma*<br/>
[in] Döndürmek için bit sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürülen değer.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_rotr8`|x86, ARM, x64|  
|`_rotr16`|x86, ARM, x64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Sağa kaydırma işleminin aksine, doğru döndürme yürütülürken, kalan en düşük alt sıra bitleri üst sıra bit konumlarına taşınır.  
  
## <a name="example"></a>Örnek  
  
```  
// rotr.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_rotr8, _rotr16)  
  
int main()  
{  
    unsigned char c = 'A', c1, c2;  
  
    for (int i = 0; i < 8; i++)  
    {  
       printf_s("Rotating 0x%x right by %d bits gives 0x%x\n", c,  
                i, _rotr8(c, i));  
    }  
  
    unsigned short s = 0x12;  
    int nBit = 10;  
  
    printf_s("Rotating unsigned short 0x%x right by %d bits "  
             "gives 0x%x\n",  
            s, nBit, _rotr16(s, nBit));  
}  
```  
  
```Output  
Rotating 0x41 right by 0 bits gives 0x41  
Rotating 0x41 right by 1 bits gives 0xa0  
Rotating 0x41 right by 2 bits gives 0x50  
Rotating 0x41 right by 3 bits gives 0x28  
Rotating 0x41 right by 4 bits gives 0x14  
Rotating 0x41 right by 5 bits gives 0xa  
Rotating 0x41 right by 6 bits gives 0x5  
Rotating 0x41 right by 7 bits gives 0x82  
Rotating unsigned short 0x12 right by 10 bits gives 0x480  
```  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_rotl8, _rotl16](../intrinsics/rotl8-rotl16.md)   
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)