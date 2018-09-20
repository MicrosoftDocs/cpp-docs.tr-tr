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
ms.openlocfilehash: 1a3a503528f5e12fbfafab8cb8e71711ba0650c6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396850"
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
|*Alan*|[in] Yazmak için Windows VMCS alan.|
|*FieldValue*|[in] Windows VMCS alanına yazılacak değer.|

## <a name="return-value"></a>Dönüş Değeri

İşlem başarılı 0.

1 işlem başarısız oldu bulunan genişletilmiş durumundaki `VM-instruction error field` , geçerli Windows VMCS.

2 işlem durumu olmadan başarısız oldu.

## <a name="remarks"></a>Açıklamalar

`__vmx_vmwrite` İşlev, eşdeğer `VMWRITE` makine yönergesi. Değerini `Field` Intel belgelerinde açıklanan bir kodlanmış alan dizini parametredir. Daha fazla bilgi için "Intel Sanallaştırma teknik belirtimi IA-32 Intel mimari," Belge ara adresindeki sayı C97063 002 belge [Intel Corporation'da](https://software.intel.com/en-us/articles/intel-sdm) site ve ardından, söz konusu ek C başvurun Belge.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__vmx_vmwrite`|X64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmread](../intrinsics/vmx-vmread.md)