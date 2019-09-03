---
title: __vmx_vmlaunch
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmlaunch
helpviewer_keywords:
- VMLAUNCH instruction
- __vmx_vmlaunch intrinsic
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
ms.openlocfilehash: 8d78e5181fdd43e10431e12d0cf540c8c9c2e719
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219554"
---
# <a name="__vmx_vmlaunch"></a>__vmx_vmlaunch

**Microsoft 'a özgü**

Geçerli sanal makine denetim yapısını (VMCS) kullanarak, çağıran uygulamayı VMX 'in kök olmayan işlem durumuna (VM girin) koyar.

## <a name="syntax"></a>Sözdizimi

```C
unsigned char __vmx_vmlaunch(void);
```

## <a name="return-value"></a>Dönüş değeri

|Değer|Açıklama|
|-----------|-------------|
|0|İşlem başarılı oldu.|
|1\.|İşlem, geçerli VNET `VM-instruction error field` 'lerin içinde kullanılabilir olan genişletilmiş durumla başarısız oldu.|
|2|İşlem durum kullanılabilir olmadan başarısız oldu.|

## <a name="remarks"></a>Açıklamalar

Bir uygulama, [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) ya da [__vmx_vmözgeçmişi](../intrinsics/vmx-vmresume.md) işlevini kullanarak bir VM-ENTER işlemi gerçekleştirebilir. [__Vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) işlevi yalnızca başlatma durumu `Clear`olan bir VMCS ile kullanılabilir ve [__vmx_vmözgeçmişi](../intrinsics/vmx-vmresume.md) işlevi yalnızca başlatma durumu olan bir `Launched`VMCS ile kullanılabilir. Sonuç olarak, `Clear`bir VMCS 'nin başlatma durumunu olarak ayarlamak için [__vmx_vmctemizle](../intrinsics/vmx-vmclear.md) işlevini kullanın ve ardından ilk VM-ENTER işlemi için [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) işlevini ve sonraki VM-ENTER için [__vmx_vmözgeçmişi](../intrinsics/vmx-vmresume.md) işlevini kullanın operasyonları.

İşlev, `VMLAUNCH` makine yönergesine eşdeğerdir. `__vmx_vmlaunch` Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) SITESINDE "ıa-32 Intel mimarisi Için Intel Sanallaştırma teknik belirtimi" belge numarası C97063-002 olan belgeyi arayın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__vmx_vmlaunch`|X64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)\
[__vmx_vmclear](../intrinsics/vmx-vmclear.md)
