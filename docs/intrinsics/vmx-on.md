---
description: 'Hakkında daha fazla bilgi edinin: __vmx_on'
title: __vmx_on
ms.date: 09/02/2019
f1_keywords:
- __vmx_on
helpviewer_keywords:
- VMXON instruction
- __vmx_on intrinsic
ms.assetid: 16804991-6a75-4adf-8ec2-bc95acfa4801
ms.openlocfilehash: a1e9171fe64a239b592f0d27ec49d4159b46523d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333577"
---
# <a name="__vmx_on"></a>__vmx_on

**Microsoft'a Özgü**

İşlemcisinde sanal makine uzantıları (VMX) işlemini etkinleştirir.

## <a name="syntax"></a>Sözdizimi

```C
unsigned char __vmx_on(
   unsigned __int64 *VmsSupportPhysicalAddress
);
```

### <a name="parameters"></a>Parametreler

*VmsSupportPhysicalAddress*\
'ndaki Bir sanal makine denetim yapısına (VMCS) işaret eden 64 bitlik bir fiziksel adrese yönelik bir işaretçi.

## <a name="return-value"></a>Döndürülen değer

|Değer|Anlamı|
|-----------|-------------|
|0|İşlem başarılı oldu.|
|1|İşlem, geçerli VNET 'lerin içinde kullanılabilir olan genişletilmiş durumla başarısız oldu `VM-instruction error field` .|
|2|İşlem durum kullanılabilir olmadan başarısız oldu.|

## <a name="remarks"></a>Açıklamalar

`__vmx_on`İşlev, `VMXON` makine yönergesine karşılık gelir. Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) SITESINDE "ıa-32 Intel mimarisi Için Intel Sanallaştırma teknik belirtimi" belge numarası C97063-002 olan belgeyi arayın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__vmx_on`|x64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
