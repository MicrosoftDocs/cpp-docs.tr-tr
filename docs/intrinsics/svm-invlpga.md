---
title: __svm_invlpga | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_invlpga
dev_langs:
- C++
helpviewer_keywords:
- __svm_invlpga intrinsic
- INVLPGA instruction
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c2f962ec4a348cca7ffdf43852cb01d673f3fb18
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706608"
---
# <a name="svminvlpga"></a>__svm_invlpga
**Microsoft'a özgü**  
  
 Bilgisayarın çeviri görünüm edilgen arabellek adresi eşleme girişi geçersiz kılar. Adres alanı tanımlayıcısı geçersiz kılmak için sayfanın ve sanal adres parametreleri belirtin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __svm_invlpga(  
     void *Va,  
     int ASID);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|*Va*|[in] Geçersiz kılmak için sayfanın sanal adres.|  
|*ASID*|[in] Geçersiz kılmak için sayfanın adres alanı tanımlayıcısı (ASID).|  
  
## <a name="remarks"></a>Açıklamalar  
 `__svm_invlpga` İşlev, eşdeğer `INVLPGA` makine yönergesi. Bu işlev, bir konuk işletim sistemi ve uygulamaları ile bir konağın sanal makine İzleyici etkileşimi destekler. Belge için daha fazla bilgi için arama "AMD64 mimarisi Programcı el ile birim 2: Sistem programlama" konumundaki belge numarasını 24593, düzeltme 3.11, [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) site.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__svm_invlpga`|x86, x64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)