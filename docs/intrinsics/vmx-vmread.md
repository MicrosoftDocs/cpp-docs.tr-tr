---
title: __vmx_vmread
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmread
helpviewer_keywords:
- VMREAD instruction
- __vmx_vmread intrinsic
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
ms.openlocfilehash: 409835ac29d6f2e839de62291cc5b142166a465c
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219438"
---
# <a name="__vmx_vmread"></a>__vmx_vmread

**Microsoft 'a özgü**

Geçerli sanal makine denetim yapısından (VMCS) belirtilen bir alanı okur ve belirtilen konuma koyar.

## <a name="syntax"></a>Sözdizimi

```C
unsigned char __vmx_vmread(
   size_t Field,
   size_t *FieldValue
);
```

### <a name="parameters"></a>Parametreler

*Alanla*\
'ndaki Okunacak VMCS alanı.

*Alandeğeri*\
'ndaki `Field` Parametresi tarafından belirtilen VMCS alanından okunan değerin depolandığı konuma yönelik bir işaretçi.

## <a name="return-value"></a>Dönüş değeri

|Değer|Açıklama|
|-----------|-------------|
|0|İşlem başarılı oldu.|
|1\.|İşlem, geçerli VNET `VM-instruction error field` 'lerin içinde kullanılabilir olan genişletilmiş durumla başarısız oldu.|
|2|İşlem durum kullanılabilir olmadan başarısız oldu.|

## <a name="remarks"></a>Açıklamalar

İşlev, `VMREAD` makine yönergesine eşdeğerdir. `__vmx_vmread` `Field` Parametresinin değeri, Intel belgelerinde açıklanan, kodlanmış bir alan dizinidir. Daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) SITESINDE "ıa-32 Intel mimarisi Için Intel Sanallaştırma teknik belirtimi" başlıklı Ek C 'yi arayın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__vmx_vmread`|X64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)
