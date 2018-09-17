---
title: __inbyte | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __inbyte
- __inbyte_cpp
dev_langs:
- C++
helpviewer_keywords:
- in instruction
- __inbyte intrinsic
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a503cb71ee1a7121a4770d5a401e33fe14fc649
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716550"
---
# <a name="inbyte"></a>__inbyte
**Microsoft'a özgü**  
  
 Oluşturur `in` yönerge tarafından belirtilen bağlantı noktası okuma bayt döndüren `Port`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned char __inbyte(  
   unsigned short Port  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
*Bağlantı noktası*<br/>
[in] Okunacak bağlantı noktası.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Belirtilen bağlantı noktasından bayt okuyun.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__inbyte`|x86, x64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
**END Microsoft özgü**  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yordam yalnızca bir iç öğe olarak kullanılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)