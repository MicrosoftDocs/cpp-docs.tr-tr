---
description: 'Hakkında daha fazla bilgi edinin: __vmx_vmclear'
title: __vmx_vmclear
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmclear
helpviewer_keywords:
- VMCLEAR instruction
- __vmx_vmclear intrinsic
ms.assetid: e3eb98e4-50fc-4c93-9bac-340fd1f0a466
ms.openlocfilehash: 2eec5c1189c6a798246a6dabfc731fb0166bc14a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333559"
---
# <a name="__vmx_vmclear"></a>__vmx_vmclear

**Microsoft'a Özgü**

Belirtilen sanal makine denetim yapısını (VMCS) başlatır ve başlatma durumunu olarak ayarlar `Clear` .

## <a name="syntax"></a>Sözdizimi

```C
unsigned char __vmx_vmclear(
   unsigned __int64 *VmcsPhysicalAddress
);
```

### <a name="parameters"></a>Parametreler

*VmcsPhysicalAddress*\
'ndaki Temizlenecek VMCS 'lerin fiziksel adresini içeren 64 bitlik bir bellek konumu işaretçisi.

## <a name="return-value"></a>Döndürülen değer

|Değer|Anlamı|
|-----------|-------------|
|0|İşlem başarılı oldu.|
|1|İşlem, geçerli VNET 'lerin içinde kullanılabilir olan genişletilmiş durumla başarısız oldu `VM-instruction error field` .|
|2|İşlem durum kullanılabilir olmadan başarısız oldu.|

## <a name="remarks"></a>Açıklamalar

Bir uygulama, [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) ya da [__vmx_vmresume](../intrinsics/vmx-vmresume.md) işlevini kullanarak bir VM-ENTER işlemi gerçekleştirebilir. [__Vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) işlevi yalnızca başlatma durumu olan BIR VMCS ile kullanılabilir `Clear` ve [__vmx_vmresume](../intrinsics/vmx-vmresume.md) işlevi yalnızca başlatma durumu olan bir VMCS ile kullanılabilir `Launched` . Sonuç olarak, bir VMCS 'nin başlatma durumunu olarak ayarlamak için [__vmx_vmclear](../intrinsics/vmx-vmclear.md) işlevini kullanın `Clear` . İlk VM-ENTER işlemi için [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) işlevini ve sonraki VM-ENTER işlemleri için [__vmx_vmresume](../intrinsics/vmx-vmresume.md) işlevini kullanın.

`__vmx_vmclear`İşlev, `VMCLEAR` makine yönergesine eşdeğerdir. Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) SITESINDE "ıa-32 Intel mimarisi Için Intel Sanallaştırma teknik belirtimi" belge numarası C97063-002 olan belgeyi arayın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__vmx_vmclear`|x64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)\
[__vmx_vmresume](../intrinsics/vmx-vmresume.md)
