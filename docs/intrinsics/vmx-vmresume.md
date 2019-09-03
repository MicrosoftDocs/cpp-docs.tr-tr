---
title: __vmx_vmresume
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmresume
helpviewer_keywords:
- __vmx_vmresume intrinsic
- VMRESUME instruction
ms.assetid: 233fe1b6-c727-493a-a484-1b2363732281
ms.openlocfilehash: 34d0e6814dd00da07076e644513400bd5be36bd3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219447"
---
# <a name="__vmx_vmresume"></a>__vmx_vmresume

**Microsoft 'a özgü**

Geçerli sanal makine denetim yapısını (VMCS) kullanarak VMX kök olmayan işlemi sürdürür.

## <a name="syntax"></a>Sözdizimi

```C
unsigned char __vmx_vmresume(
   void);
```

## <a name="return-value"></a>Dönüş değeri

|Değer|Açıklama|
|-----------|-------------|
|0|İşlem başarılı oldu.|
|1\.|İşlem, geçerli VNET `VM-instruction error field` 'lerin içinde kullanılabilir olan genişletilmiş durumla başarısız oldu.|
|2|İşlem durum kullanılabilir olmadan başarısız oldu.|

## <a name="remarks"></a>Açıklamalar

Bir uygulama, [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) veya `__vmx_vmresume` işlevini kullanarak VM-ENTER işlemi gerçekleştirebilir. İşlevi yalnızca başlatma `Clear`durumu olan bir VMCS ile kullanılabilir ve `__vmx_vmresume` işlev yalnızca başlatma durumu olan bir VMCS `Launched`ile kullanılabilir. `__vmx_vmlaunch` Sonuç olarak, bir VMCS 'nin başlatma durumunu olarak `Clear`ayarlamak için [__vmx_vmctemizle](../intrinsics/vmx-vmclear.md) işlevini kullanın `__vmx_vmlaunch` ve ardından `__vmx_vmresume` ilk VM-ENTER işleminizi ve sonraki VM-ENTER işlemleri için işlevini kullanın.

İşlev, `VMRESUME` makine yönergesine eşdeğerdir. `__vmx_vmresume` Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) SITESINDE "ıa-32 Intel mimarisi Için Intel Sanallaştırma teknik belirtimi" belge numarası C97063-002 olan PDF belgesini arayın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__vmx_vmresume`|X64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)\
[__vmx_vmclear](../intrinsics/vmx-vmclear.md)
