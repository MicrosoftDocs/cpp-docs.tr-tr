---
title: __vmx_vmread | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmread
dev_langs:
- C++
helpviewer_keywords:
- VMREAD instruction
- __vmx_vmread intrinsic
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6f03ea1ea39b9202d4bb7b850bb81354a4a47f1
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43677386"
---
# <a name="vmxvmread"></a>__vmx_vmread
**Microsoft'a özgü**  
  
 Belirtilen alan geçerli sanal makine denetim yapısından (Windows VMCS) okur ve belirtilen konuma yerleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned char __vmx_vmread(  
   size_t Field,  
   size_t *FieldValue  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `Field`|Okunacak Windows VMCS alan.|  
|[in] `FieldValue`|Bir işaretçi değeri depolamak için konum için okuma tarafından belirtilen Windows VMCS alanından `Field` parametresi.|  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|Değer|Açıklama|  
|-----------|-------------|  
|0|İşlem başarılı oldu.|  
|1.|İşlem başarısız oldu bulunan genişletilmiş durumundaki `VM-instruction error field` , geçerli Windows VMCS.|  
|2|İşlem durumu olmadan başarısız oldu.|  
  
## <a name="remarks"></a>Açıklamalar  
 `__vmx_vmread` İşlev, eşdeğer `VMREAD` makine yönergesi. Değerini `Field` Intel belgelerinde açıklanan bir kodlanmış alan dizini parametredir. Daha fazla bilgi için "Intel Sanallaştırma teknik belirtimi IA-32 Intel mimari," Belge ara adresindeki sayı C97063 002 belge [Intel Corporation'da](https://software.intel.com/en-us/articles/intel-sdm) site ve ardından bu belgenin ek C başvurun .  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__vmx_vmread`|X64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)