---
title: __vmx_vmread
ms.date: 11/04/2016
f1_keywords:
- __vmx_vmread
helpviewer_keywords:
- VMREAD instruction
- __vmx_vmread intrinsic
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
ms.openlocfilehash: 5c7b72ba3bf1bd60324704b774bcedaf5612240f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028392"
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
|*Alan*|[in] Okunacak Windows VMCS alan.|
|*FieldValue*|[in] Bir işaretçi değeri depolamak için konum için okuma tarafından belirtilen Windows VMCS alanından `Field` parametresi.|

## <a name="return-value"></a>Dönüş Değeri

|Değer|Açıklama|
|-----------|-------------|
|0|İşlem başarılı oldu.|
|1.|İşlem başarısız oldu bulunan genişletilmiş durumundaki `VM-instruction error field` , geçerli Windows VMCS.|
|2|İşlem durumu olmadan başarısız oldu.|

## <a name="remarks"></a>Açıklamalar

`__vmx_vmread` İşlev, eşdeğer `VMREAD` makine yönergesi. Değerini `Field` Intel belgelerinde açıklanan bir kodlanmış alan dizini parametredir. Daha fazla bilgi için "Intel Sanallaştırma teknik belirtimi IA-32 Intel mimari," Belge ara adresindeki sayı C97063 002 belge [Intel Corporation'da](https://software.intel.com/articles/intel-sdm) site ve ardından bu belgenin ek C başvurun .

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__vmx_vmread`|X64|

**Üst bilgi dosyası** \<intrin.h >

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)