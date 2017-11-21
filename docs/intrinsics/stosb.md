---
title: __stosb | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __stosb
dev_langs: C++
helpviewer_keywords:
- rep stosb instruction
- __stosb intrinsic
- stosb instruction
ms.assetid: 634589ed-2da3-439b-a381-a214d89bf10c
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e53a001a63eb73ef124841596c7b8da42409f8c7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="stosb"></a>__stosb
**Microsoft özel**  
  
 Bir depolama dize yönergesi oluşturur (`rep stosb`).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __stosb(   
   unsigned char* Dest,   
   unsigned char Data,   
   size_t Count   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out]`Dest`  
 İşlemin hedefi.  
  
 [in]`Data`  
 Depolamak için veriler.  
  
 [in]`Count`  
 Yazılacak bayt Blok uzunluğu.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__stosb`|x86,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Sonuç karakter olan `Data` bloğunun yazılan `Count` bayt cinsinden `Dest` dize.  
  
 Bu yordam yalnızca bir iç kullanılabilir.  
  
## <a name="example"></a>Örnek  
  
```  
// stosb.c  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__stosb)  
  
int main()  
{  
    unsigned char c = 0x40; /* '@' character */  
    unsigned char s[] = "*********************************";  
  
    printf_s("%s\n", s);  
    __stosb((unsigned char*)s+1, c, 6);  
    printf_s("%s\n", s);  
  
}  
```  
  
```Output  
*********************************  
*@@@@@@**************************  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)