---
title: __inbytestring | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __inbytestring
- __inbytestring_cpp
dev_langs: C++
helpviewer_keywords:
- rep insb instruction
- __inbytestring intrinsic
ms.assetid: fe549556-e7a3-4af3-8ebf-8a7dc3cb233b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4b6a70614a747ad5e313e96713f64ad756de9211
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="inbytestring"></a>__inbytestring
**Microsoft özel**  
  
 Belirtilen bağlantı noktası kullanımından veri okuyan `rep insb` yönergesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __inbytestring(  
   unsigned short Port,  
   unsigned char* Buffer,  
   unsigned long Count  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`Port`  
 Okunacak bağlantı noktası.  
  
 [out]`Buffer`  
 Bağlantı noktasından okunan veriler burada yazılır.  
  
 [in]`Count`  
 Okunacak veri bayt sayısı.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__inbytestring`|x86,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yordam yalnızca bir iç kullanılabilir.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)