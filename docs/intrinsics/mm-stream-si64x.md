---
title: _mm_stream_si64x | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _mm_stream_si64x
dev_langs: C++
helpviewer_keywords:
- movnti instruction
- _mm_stream_si64x intrinsic
ms.assetid: 114c2cd0-085f-41aa-846e-87bdd56c9ee7
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 00d3420fc070eaaecfd368ef27a33915f3dbfa2c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mmstreamsi64x"></a>_mm_stream_si64x  
  
**Microsoft özel**  
  
 MOVNTI yönergesi oluşturur. Verileri Yazar `Source` tarafından belirtilen bir bellek konumuna `Dest`, önbellekleri kirletmesini olmadan.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _mm_stream_si64x(   
   __int64 * Dest,   
   __int64 Source   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
 [out]`Dest`  
 Kaynak veri yazmak için konumu için bir işaretçi.  
  
 [in]`Source`  
 Yazılacak veriler.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_mm_stream_si64x`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
  
 Bu yordam yalnızca bir iç kullanılabilir.  
  
## <a name="example"></a>Örnek  
  
```C  
// _mm_stream_si64x.c  
// processor: x64  
  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_mm_stream_si64x)  
  
int main()  
{  
    __int64 val = 0xFFFFFFFFFFFFI64;  
    __int64 a[10];  
  
    memset(a, 0, sizeof(a));  
    _mm_stream_si64x(a+1, val);  
    printf_s( "%I64x %I64x %I64x %I64x", a[0], a[1], a[2], a[3]);   
}  
```  
  
```Output  
0 ffffffffffff 0 0  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)