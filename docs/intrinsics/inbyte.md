---
title: __inbyte | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __inbyte
- __inbyte_cpp
dev_langs: C++
helpviewer_keywords:
- in instruction
- __inbyte intrinsic
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 20781d2e8f925cec9bacb8ca125f68c3e9f7c201
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="inbyte"></a>__inbyte
**Microsoft özel**  
  
 Oluşturur `in` yönerge tarafından belirtilen bağlantı noktası okuma bayt döndürme `Port`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned char __inbyte(  
   unsigned short Port  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`Port`  
 Okunacak bağlantı noktası.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Belirtilen bağlantı noktasından baytı okur.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__inbyte`|x86,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
**SON Microsoft özel**  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yordam yalnızca bir iç kullanılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)