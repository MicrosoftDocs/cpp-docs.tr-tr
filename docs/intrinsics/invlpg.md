---
title: __invlpg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __invlpg
- __invlpg_cpp
dev_langs:
- C++
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ada416217be672da8f93c777b0b2a6e12684711
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703033"
---
# <a name="invlpg"></a>__invlpg
**Microsoft'a özgü**  
  
 X86 oluşturur `invlpg` işaret ettiği bellek ile ilişkili sayfası için çeviri arabelleğinde arabelleği (TLB) geçersiz kılmaz yönerge `Address`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __invlpg(  
   void* Address  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
*Adresi*<br/>
[in] Bir 64-bit adresi.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__invlpg`|x86, x64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 İç `__invlpg` ayrıcalıklı yönerge yayar ve yalnızca 0 ayrıcalık düzeyi (CPL) ile çekirdek modunda kullanılabilir.  
  
 Bu yordam yalnızca bir iç öğe olarak kullanılabilir.  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)