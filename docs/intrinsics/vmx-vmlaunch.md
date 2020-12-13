---
description: 'Hakkında daha fazla bilgi edinin: __vmx_vmlaunch'
title: __vmx_vmlaunch
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmlaunch
helpviewer_keywords:
- VMLAUNCH instruction
- __vmx_vmlaunch intrinsic
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
ms.openlocfilehash: 3f6596e0644250710491ed90036a651c0725a5f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333544"
---
# <a name="__vmx_vmlaunch"></a>__vmx_vmlaunch

**Microsoft'a Özgü**

Geçerli sanal makine denetim yapısını (VMCS) kullanarak, çağıran uygulamayı VMX 'in kök olmayan işlem durumuna (VM girin) koyar.

## <a name="syntax"></a>Sözdizimi

```C
unsigned char __vmx_vmlaunch(void);
```

## <a name="return-value"></a>Döndürülen değer

|Değer|Anlamı|
|-----------|-------------|
|0|İşlem başarılı oldu.|
|1|İşlem, geçerli VNET 'lerin içinde kullanılabilir olan genişletilmiş durumla başarısız oldu `VM-instruction error field` .|
|2|İşlem durum kullanılabilir olmadan başarısız oldu.|

## <a name="remarks"></a>Açıklamalar

Bir uygulama, [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) ya da [__vmx_vmresume](../intrinsics/vmx-vmresume.md) işlevini kullanarak bir VM-ENTER işlemi gerçekleştirebilir. [__Vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) işlevi yalnızca başlatma durumu olan BIR VMCS ile kullanılabilir `Clear` ve [__vmx_vmresume](../intrinsics/vmx-vmresume.md) işlevi yalnızca başlatma durumu olan bir VMCS ile kullanılabilir `Launched` . Sonuç olarak, bir VMCS 'nin başlatma durumunu olarak ayarlamak için [__vmx_vmclear](../intrinsics/vmx-vmclear.md) işlevini kullanın `Clear` ve ardından ilk VM-enter işlemi için [__VMX_VMLAUNCH](../intrinsics/vmx-vmlaunch.md) işlevini ve sonraki vm-ENTER işlemleri için [__vmx_vmresume](../intrinsics/vmx-vmresume.md) işlevini kullanın.

`__vmx_vmlaunch`İşlev, `VMLAUNCH` makine yönergesine eşdeğerdir. Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) SITESINDE "ıa-32 Intel mimarisi Için Intel Sanallaştırma teknik belirtimi" belge numarası C97063-002 olan belgeyi arayın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__vmx_vmlaunch`|x64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)\
[__vmx_vmclear](../intrinsics/vmx-vmclear.md)
