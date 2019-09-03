---
title: __vmx_vmptrld
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmptrld
helpviewer_keywords:
- __vmx_vmptrld intrinsic
- VMPTRLD instruction
ms.assetid: 95c9ec5b-1a81-41ba-983e-327bd6a65fcb
ms.openlocfilehash: 79b5a8b34b652ae1f011e89c793a7157c9e435ee
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219500"
---
# <a name="__vmx_vmptrld"></a>__vmx_vmptrld

**Microsoft 'a özgü**

İşaretçiyi belirtilen adresten geçerli sanal makine denetim yapısına (VMCS) yükler.

## <a name="syntax"></a>Sözdizimi

```C
int __vmx_vmptrld(
   unsigned __int64 *VmcsPhysicalAddress
);
```

### <a name="parameters"></a>Parametreler

*VmcsPhysicalAddress*\
'ndaki VMCS işaretçisinin depolandığı adres.

## <a name="return-value"></a>Dönüş değeri

0
İşlem başarılı oldu.

1
İşlem, geçerli VNET `VM-instruction error field` 'lerin içinde kullanılabilir olan genişletilmiş durumla başarısız oldu.

iki
İşlem durum kullanılabilir olmadan başarısız oldu.

## <a name="remarks"></a>Açıklamalar

VMCS işaretçisi 64 bitlik bir fiziksel adrestir.

İşlev, `VMPTRLD` makine yönergesine eşdeğerdir. `__vmx_vmptrld` Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) SITESINDE "ıa-32 Intel mimarisi Için Intel Sanallaştırma teknik belirtimi" belge numarası C97063-002 olan belgeyi arayın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__vmx_vmptrld`|X64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmptrst](../intrinsics/vmx-vmptrst.md)
