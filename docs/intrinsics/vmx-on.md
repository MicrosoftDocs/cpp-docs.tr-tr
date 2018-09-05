---
title: __vmx_on | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_on
dev_langs:
- C++
helpviewer_keywords:
- VMXON instruction
- __vmx_on intrinsic
ms.assetid: 16804991-6a75-4adf-8ec2-bc95acfa4801
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4321a082efa71ecc81963099317ad3600ce8b36f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676204"
---
# <a name="vmxon"></a>__vmx_on
**Microsoft'a özgü**  
  
 Sanal makine Uzantıları (VMX) işlemci işlemindeki etkinleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned char __vmx_on(  
   unsigned __int64 *VmsSupportPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `VmsSupportPhysicalAddress`  
 Bir sanal makine denetim yapısı (Windows VMCS) işaret eden bir 64 bit fiziksel adresi için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|Değer|Açıklama|  
|-----------|-------------|  
|0|İşlem başarılı oldu.|  
|1.|İşlem başarısız oldu bulunan genişletilmiş durumundaki `VM-instruction error field` , geçerli Windows VMCS.|  
|2|İşlem durumu olmadan başarısız oldu.|  
  
## <a name="remarks"></a>Açıklamalar  
 `__vmx_on` İşlevi karşılık gelen `VMXON` makine yönergesi. Bu işlev, bir konuk işletim sistemi ve uygulamaları ile bir konağın sanal makine İzleyici etkileşimi destekler. Daha fazla bilgi için "Intel Sanallaştırma teknik belirtimi IA-32 Intel mimari," Belge ara adresindeki sayı C97063 002 belge [Intel Corporation'da](https://software.intel.com/en-us/articles/intel-sdm) site.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__vmx_on`|X64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)