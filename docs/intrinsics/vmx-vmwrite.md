---
title: __vmx_vmwrite
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmwrite
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
ms.openlocfilehash: cdc5590858f160db24bf75ef11c8f20b204a3152
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219397"
---
# <a name="__vmx_vmwrite"></a>__vmx_vmwrite

**Microsoft 'a özgü**

Belirtilen değeri geçerli sanal makine denetim yapısında (VMCS) belirtilen alana yazar.

## <a name="syntax"></a>Sözdizimi

```C
unsigned char __vmx_vmwrite(
   size_t Field,
   size_t FieldValue
);
```

### <a name="parameters"></a>Parametreler

*Alanla*\
'ndaki Yazılacak VMCS alanı.

*Alandeğeri*\
'ndaki VMCS alanına yazılacak değer.

## <a name="return-value"></a>Dönüş değeri

0
İşlem başarılı oldu.

1
İşlem, geçerli VNET `VM-instruction error field` 'lerin içinde kullanılabilir olan genişletilmiş durumla başarısız oldu.

iki
İşlem durum kullanılabilir olmadan başarısız oldu.

## <a name="remarks"></a>Açıklamalar

İşlev, `VMWRITE` makine yönergesine eşdeğerdir. `__vmx_vmwrite` `Field` Parametresinin değeri, Intel belgelerinde açıklanan, kodlanmış bir alan dizinidir. Daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) SITESINDE "ıa-32 Intel mimarisi Için Intel Sanallaştırma teknik belirtimi" başlıklı Ek C 'yi arayın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__vmx_vmwrite`|X64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmread](../intrinsics/vmx-vmread.md)
