---
title: __readdr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __readdr
dev_langs: C++
helpviewer_keywords: __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ba898d71895b74c43ad5de737355606a1d2b69ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="readdr"></a>__readdr
Belirtilen hata ayıklama kaydı değerini okur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned         __readdr(unsigned int DebugRegister);  
unsigned __int64 __readdr(unsigned int DebugRegister);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`DebugRegister`  
 Hata ayıklama tanımlayan 0 ile 7 arasında bir sabit kaydedin.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Belirtilen hata ayıklama kaydı değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yapı yalnızca çekirdek modunda kullanılabilir ve yordamlar yalnızca iç bilgileri kullanılabilir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__readdr`|x86,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__readeflags](../intrinsics/readeflags.md)