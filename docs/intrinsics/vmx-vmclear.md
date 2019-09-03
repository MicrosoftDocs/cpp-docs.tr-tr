---
title: __vmx_vmclear
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmclear
helpviewer_keywords:
- VMCLEAR instruction
- __vmx_vmclear intrinsic
ms.assetid: e3eb98e4-50fc-4c93-9bac-340fd1f0a466
ms.openlocfilehash: 3b5807402cf0a9d8a9ef1ded1d112d22a801633e
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219533"
---
# <a name="__vmx_vmclear"></a>__vmx_vmclear

**Microsoft 'a özgü**

Belirtilen sanal makine denetim yapısını (VMCS) başlatır ve başlatma durumunu olarak `Clear`ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
unsigned char __vmx_vmclear(
   unsigned __int64 *VmcsPhysicalAddress
);
```

### <a name="parameters"></a>Parametreler

*VmcsPhysicalAddress*\
'ndaki Temizlenecek VMCS 'lerin fiziksel adresini içeren 64 bitlik bir bellek konumu işaretçisi.

## <a name="return-value"></a>Dönüş değeri

|Değer|Açıklama|
|-----------|-------------|
|0|İşlem başarılı oldu.|
|1\.|İşlem, geçerli VNET `VM-instruction error field` 'lerin içinde kullanılabilir olan genişletilmiş durumla başarısız oldu.|
|2|İşlem durum kullanılabilir olmadan başarısız oldu.|

## <a name="remarks"></a>Açıklamalar

Bir uygulama, [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) ya da [__vmx_vmözgeçmişi](../intrinsics/vmx-vmresume.md) işlevini kullanarak bir VM-ENTER işlemi gerçekleştirebilir. [__Vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) işlevi yalnızca başlatma durumu `Clear`olan bir VMCS ile kullanılabilir ve [__vmx_vmözgeçmişi](../intrinsics/vmx-vmresume.md) işlevi yalnızca başlatma durumu olan bir `Launched`VMCS ile kullanılabilir. Sonuç olarak, bir VMCS 'nin başlatma durumunu olarak `Clear`ayarlamak için [__vmx_vmctemizle](../intrinsics/vmx-vmclear.md) işlevini kullanın. İlk VM-ENTER işlemi için [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) işlevini ve sonraki VM-ENTER işlemleri için [__vmx_vmözgeçmişi](../intrinsics/vmx-vmresume.md) işlevini kullanın.

İşlev, `VMCLEAR` makine yönergesine eşdeğerdir. `__vmx_vmclear` Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) SITESINDE "ıa-32 Intel mimarisi Için Intel Sanallaştırma teknik belirtimi" belge numarası C97063-002 olan belgeyi arayın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__vmx_vmclear`|X64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)\
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)
