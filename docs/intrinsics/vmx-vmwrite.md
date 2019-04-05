---
title: __vmx_vmwrite
ms.date: 11/04/2016
f1_keywords:
- __vmx_vmwrite
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
ms.openlocfilehash: e52b1f181f00ce013a111d1a5a62abeff544e20a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037516"
---
# <a name="vmxvmwrite"></a>__vmx_vmwrite

**Microsoft'a Özgü**

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

`__vmx_vmwrite` İşlev, eşdeğer `VMWRITE` makine yönergesi. Değerini `Field` Intel belgelerinde açıklanan bir kodlanmış alan dizini parametredir. Daha fazla bilgi için "Intel Sanallaştırma teknik belirtimi IA-32 Intel mimari," Belge ara adresindeki sayı C97063 002 belge [Intel Corporation'da](https://software.intel.com/articles/intel-sdm) site ve ardından, söz konusu ek C başvurun Belge.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__vmx_vmwrite`|X64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmread](../intrinsics/vmx-vmread.md)