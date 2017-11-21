---
title: _umul128 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __umul128
dev_langs: C++
helpviewer_keywords: __umul128 intrinsic
ms.assetid: 13684df3-3ac7-467c-b258-a0e93bc490b5
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 81a408540d2606cb81d92a3e93cbcff888d4a3e7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="umul128"></a>_umul128
**Microsoft özel**  
  
 İlk iki bağımsız değişken olarak geçirilen iki 64-bit işaretsiz tamsayı çarpar ve ürünün yüksek 64 bit gösterdiği 64 bit işaretsiz tamsayıyı koyan `HighProduct` ve ürünün düşük 64 bit döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned __int64 _umul128(   
   unsigned __int64 Multiplier,   
   unsigned __int64 Multiplicand,   
   unsigned __int64 *HighProduct   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`Multiplier`  
 Çarpılacağı ilk 64-bit tam sayı.  
  
 [in]`Multiplicand`  
 Çarpılacağı ikinci 64-bit tam sayı.  
  
 [out]`HighProduct`  
 Ürünün yüksek 64 bit.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Ürünün düşük 64 bit.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|Üstbilgi|  
|---------------|------------------|------------|  
|`_umul128`|ARM,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h >|  
  
## <a name="example"></a>Örnek  
  
```  
// umul128.c  
// processor: IPF, x64  
  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_umul128)  
  
int main()  
{  
    unsigned __int64 a = 0x0fffffffffffffffI64;  
    unsigned __int64 b = 0xf0000000I64;  
    unsigned __int64 c, d;  
  
    d = _umul128(a, b, &c);  
  
    printf_s("%#I64x * %#I64x = %#I64x%I64x\n", a, b, c, d);  
}  
```  
  
```Output  
0xfffffffffffffff * 0xf0000000 = 0xeffffffffffffff10000000  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)