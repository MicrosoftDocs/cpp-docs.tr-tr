---
title: __readdr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __readdr
dev_langs:
- C++
helpviewer_keywords:
- __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1d5cabbd1d779de4c6c081b57b8f241d9fa92f62
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709069"
---
# <a name="readdr"></a>__readdr
Belirtilen hata ayıklama kaydı değerini okur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned         __readdr(unsigned int DebugRegister);  
unsigned __int64 __readdr(unsigned int DebugRegister);  
```  
  
#### <a name="parameters"></a>Parametreler  
*DebugRegister*<br/>
[in] Hata ayıklama tanımlayan 0 ile 7 arasında bir sabit kaydedin.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Belirtilen hata ayıklama kayıt değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu iç öğeler yalnızca çekirdek modunda kullanılabilir ve yordamlar yalnızca iç öğe olarak kullanılabilir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__readdr`|x86, x64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__readeflags](../intrinsics/readeflags.md)