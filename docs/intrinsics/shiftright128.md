---
title: __shiftright128 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __shiftright128
dev_langs: C++
helpviewer_keywords: __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5b7913802df6894697875e90b86286870d32fccc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="shiftright128"></a>__shiftright128
**Microsoft özel**  
  
 İki 64-bit miktarlar olarak temsil 128 bitlik bir miktar, kaydırır `LowPart` ve `HighPart`, sağ tarafından belirtilen bit sayısı tarafından `Shift` ve düşük 64 bit sonucunun döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned __int64 __shiftright128(   
   unsigned __int64 LowPart,   
   unsigned __int64 HighPart,   
   unsigned char Shift   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`LowPart`  
 Düşük 64 bit kaydırmak için 128-bit miktarı.  
  
 [in]`HighPart`  
 Yüksek 64 bit kaydırmak için 128-bit miktarı.  
  
 [in]`Shift`  
 Kaydırılacak bit sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sonucun düşük 64 bit.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__shiftright128`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 `Shift` Değerdir her zaman 64 modulo bu nedenle, örneğin, çağırırsanız `__shiftright128(0, 1, 64)`, işlevi üst kısım kayar `0` BITS sağ ve düşük bir parçası dönmek `0` ve `1` aksi beklenen şekilde.  
  
## <a name="example"></a>Örnek  
 Bir örnek için bkz: [__shiftleft128](../intrinsics/shiftleft128.md).  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__shiftleft128](../intrinsics/shiftleft128.md)   
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)