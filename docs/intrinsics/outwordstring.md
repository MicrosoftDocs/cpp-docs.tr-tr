---
title: __outwordstring | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __outwordstring
dev_langs:
- C++
helpviewer_keywords:
- rep outsw instruction
- __outwordstring intrinsic
- outsw instruction
ms.assetid: b470c7a0-1de9-4370-886a-b2c3a1f842f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c49f76175ced83fb9a9b7e72e1c1fc7dbb68e20
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720674"
---
# <a name="outwordstring"></a>__outwordstring
**Microsoft'a özgü**  
  
 Oluşturur `rep outsw` gönderen yönerge `Count` başlayan sözcükleri `Buffer` çıkış tarafından belirtilen g/ç bağlantı noktasına `Port`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __outwordstring(   
   unsigned short Port,   
   unsigned short* Buffer,   
   unsigned long Count   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
*Bağlantı noktası*<br/>
[in] Veri göndermek için bağlantı noktası.  
  
*Arabellek*<br/>
[in] Belirtilen bağlantı noktasına gönderilecek verileri için bir işaretçi.  
  
*Sayısı*<br/>
[in] Gönderilecek sözcük sayısı.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__outwordstring`|x86, x64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yordam yalnızca bir iç öğe olarak kullanılabilir.  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)