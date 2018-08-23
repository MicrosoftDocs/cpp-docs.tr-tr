---
title: __vmx_vmwrite | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmwrite
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec022fe2d317ec38bc1d9b06f459b9efc7818c92
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42465174"
---
# <a name="vmxvmwrite"></a>__vmx_vmwrite
**Microsoft'a özgü**  
  
 Belirtilen değer geçerli bir sanal makine denetim yapısı (Windows VMCS) belirtilen alan yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned char __vmx_vmwrite(   
   size_t Field,  
   size_t FieldValue  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `Field`|Yazmak için Windows VMCS alan.|  
|[in] `FieldValue`|Windows VMCS alanına yazılacak değer.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 0  
 İşlem başarılı oldu.  
  
 1.  
 İşlem başarısız oldu bulunan genişletilmiş durumundaki `VM-instruction error field` , geçerli Windows VMCS.  
  
 2  
 İşlem durumu olmadan başarısız oldu.  
  
## <a name="remarks"></a>Açıklamalar  
 `__vmx_vmwrite` İşlev, eşdeğer `VMWRITE` makine yönergesi. Değerini `Field` Intel belgelerinde açıklanan bir kodlanmış alan dizini parametredir. Daha fazla bilgi için "Intel Sanallaştırma teknik belirtimi IA-32 Intel mimari," Belge ara adresindeki sayı C97063 002 belge [Intel Corporation'da](http://go.microsoft.com/fwlink/p/?linkid=127) site ve ardından, söz konusu ek C başvurun Belge.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__vmx_vmwrite`|X64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmread](../intrinsics/vmx-vmread.md)