---
description: 'Hakkında daha fazla bilgi edinin: __vmx_vmread'
title: __vmx_vmread
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmread
helpviewer_keywords:
- VMREAD instruction
- __vmx_vmread intrinsic
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
ms.openlocfilehash: 39ea9c0566d3f9c9d3fc6d980861fb3580293895
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333513"
---
# <a name="__vmx_vmread"></a>__vmx_vmread

**Microsoft'a Özgü**

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
'ndaki Parametresi tarafından belirtilen VMCS alanından okunan değerin depolandığı konuma yönelik bir işaretçi `Field` .

## <a name="return-value"></a>Döndürülen değer

|Değer|Anlamı|
|-----------|-------------|
|0|İşlem başarılı oldu.|
|1|İşlem, geçerli VNET 'lerin içinde kullanılabilir olan genişletilmiş durumla başarısız oldu `VM-instruction error field` .|
|2|İşlem durum kullanılabilir olmadan başarısız oldu.|

## <a name="remarks"></a>Açıklamalar

`__vmx_vmread`İşlev, `VMREAD` makine yönergesine eşdeğerdir. Parametresinin değeri, `Field` Intel belgelerinde açıklanan, kodlanmış bir alan dizinidir. Daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) SITESINDE "ıa-32 Intel mimarisi Için Intel Sanallaştırma teknik belirtimi" başlıklı Ek C 'yi arayın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__vmx_vmread`|x64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)
