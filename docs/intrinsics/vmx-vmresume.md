---
description: 'Hakkında daha fazla bilgi edinin: __vmx_vmresume'
title: __vmx_vmresume
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmresume
helpviewer_keywords:
- __vmx_vmresume intrinsic
- VMRESUME instruction
ms.assetid: 233fe1b6-c727-493a-a484-1b2363732281
ms.openlocfilehash: 35c1ca7eeca847b14d16c451752a186c63a59749
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343784"
---
# <a name="__vmx_vmresume"></a>__vmx_vmresume

**Microsoft'a Özgü**

Geçerli sanal makine denetim yapısını (VMCS) kullanarak VMX kök olmayan işlemi sürdürür.

## <a name="syntax"></a>Sözdizimi

```C
unsigned char __vmx_vmresume(
   void);
```

## <a name="return-value"></a>Döndürülen değer

|Değer|Anlamı|
|-----------|-------------|
|0|İşlem başarılı oldu.|
|1|İşlem, geçerli VNET 'lerin içinde kullanılabilir olan genişletilmiş durumla başarısız oldu `VM-instruction error field` .|
|2|İşlem durum kullanılabilir olmadan başarısız oldu.|

## <a name="remarks"></a>Açıklamalar

Bir uygulama, [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) veya IŞLEVINI kullanarak VM-ENTER işlemi gerçekleştirebilir `__vmx_vmresume` . `__vmx_vmlaunch`İşlevi yalnızca başlatma durumu olan BIR VMCS ile kullanılabilir `Clear` ve `__vmx_vmresume` işlev yalnızca başlatma durumu olan bir VMCS ile kullanılabilir `Launched` . Sonuç olarak, bir VMCS 'nin başlatma durumunu ' a ayarlamak için [__vmx_vmclear](../intrinsics/vmx-vmclear.md) işlevini kullanın `Clear` ve ardından `__vmx_vmlaunch` İlk VM-ENTER işleminizi ve `__vmx_vmresume` sonraki VM-ENTER işlemleri için işlevini kullanın.

`__vmx_vmresume`İşlev, `VMRESUME` makine yönergesine eşdeğerdir. Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) SITESINDE "ıa-32 Intel mimarisi Için Intel Sanallaştırma teknik belirtimi" belge numarası C97063-002 olan PDF belgesini arayın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__vmx_vmresume`|x64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)\
[__vmx_vmclear](../intrinsics/vmx-vmclear.md)
