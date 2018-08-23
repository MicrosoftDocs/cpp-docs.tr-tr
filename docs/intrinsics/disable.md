---
title: _disable | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _disable_cpp
- _disable
dev_langs:
- C++
helpviewer_keywords:
- _disable intrinsic
- rsm instruction
- disable intrinsic
ms.assetid: 52da3df9-815c-4524-9839-6d1742cff5c6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2748d0412c9ee0f7e7684d35a38f3c2b5d133754
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42465460"
---
# <a name="disable"></a>_disable
**Microsoft'a özgü**  
  
 Kesmeleri devre dışı bırakır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _disable(void);  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_disable`|x86, ARM, x64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 `_disable` İşlemci Kesme bayrağını temizleme bildirir. X86 sistemleri, bu işlev kesme bayrağını Temizle oluşturur (`cli`) yönerge.  
  
 Bu işlev, yalnızca çekirdek modunda kullanılabilir. Ayrıcalıklı yönerge özel durum, kullanıcı modunda kullandıysanız, çalışma zamanında durum oluşturulur.  
  
 ARM platformlarında, bu yordam yalnızca bir iç öğe olarak kullanılabilir.  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)