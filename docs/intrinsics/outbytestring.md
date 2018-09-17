---
title: __outbytestring | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __outbytestring
dev_langs:
- C++
helpviewer_keywords:
- rep outsb instruction
- __outbytestring intrinsic
- outsb instruction
ms.assetid: c9150661-9c18-427f-bae8-710bba6ed78c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54a816bd4df165b3df9de723560192ac9072b29c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718841"
---
# <a name="outbytestring"></a>__outbytestring
**Microsoft'a özgü**  
  
 Oluşturur `rep outsb` gönderen ilk yönerge `Count` verileri baytlık tarafından işaret edilen `Buffer` tarafından belirtilen bağlantı noktasına `Port`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __outbytestring(   
   unsigned short Port,   
   unsigned char* Buffer,   
   unsigned long Count   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
*Bağlantı noktası*<br/>
[in] Veri göndermek için bağlantı noktası.  
  
*Arabellek*<br/>
[in] Belirtilen bağlantı noktasına gönderilecek veri.  
  
*Sayısı*<br/>
[in] Veri gönderilecek bayt sayısı.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__outbytestring`|x86, x64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yordam yalnızca bir iç öğe olarak kullanılabilir.  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)