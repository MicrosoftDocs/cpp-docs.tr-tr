---
title: __vmx_vmptrld | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmptrld
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmptrld intrinsic
- VMPTRLD instruction
ms.assetid: 95c9ec5b-1a81-41ba-983e-327bd6a65fcb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd04350df17b6d2dfed65526d0f7681c314f07f8
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43682626"
---
# <a name="vmxvmptrld"></a>__vmx_vmptrld
**Microsoft'a özgü**  
  
 İmleci belirtilen adres geçerli sanal makine denetim yapısı (Windows VMCS) yükler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int __vmx_vmptrld(   
   unsigned __int64 *VmcsPhysicalAddress   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] *`VmcsPhysicalAddress`  
 Windows VMCS işaretçinin depolandığı adresi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 0  
 İşlem başarılı oldu.  
  
 1.  
 İşlem başarısız oldu bulunan genişletilmiş durumundaki `VM-instruction error field` , geçerli Windows VMCS.  
  
 2  
 İşlem durumu olmadan başarısız oldu.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir 64 bit fiziksel adresi Windows VMCS işaretçisidir.  
  
 `__vmx_vmptrld` İşlev, eşdeğer `VMPTRLD` makine yönergesi. Bu işlev, bir konuk işletim sistemi ve uygulamaları ile bir konağın sanal makine İzleyici etkileşimi destekler. Daha fazla bilgi için "Intel Sanallaştırma teknik belirtimi IA-32 Intel mimari," Belge ara adresindeki sayı C97063 002 belge [Intel Corporation'da](https://software.intel.com/en-us/articles/intel-sdm) site.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__vmx_vmptrld`|X64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmptrst](../intrinsics/vmx-vmptrst.md)