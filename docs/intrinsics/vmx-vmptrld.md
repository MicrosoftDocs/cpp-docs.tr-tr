---
description: 'Hakkında daha fazla bilgi edinin: __vmx_vmptrld'
title: __vmx_vmptrld
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmptrld
helpviewer_keywords:
- __vmx_vmptrld intrinsic
- VMPTRLD instruction
ms.assetid: 95c9ec5b-1a81-41ba-983e-327bd6a65fcb
ms.openlocfilehash: 850311e4423940ebd34a203e6d43ec961b3258f4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333541"
---
# <a name="__vmx_vmptrld"></a>__vmx_vmptrld

**Microsoft'a Özgü**

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

## <a name="return-value"></a>Döndürülen değer

0
İşlem başarılı oldu.

1
İşlem, geçerli VNET 'lerin içinde kullanılabilir olan genişletilmiş durumla başarısız oldu `VM-instruction error field` .

iki
İşlem durum kullanılabilir olmadan başarısız oldu.

## <a name="remarks"></a>Açıklamalar

VMCS işaretçisi 64 bitlik bir fiziksel adrestir.

`__vmx_vmptrld`İşlev, `VMPTRLD` makine yönergesine eşdeğerdir. Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) SITESINDE "ıa-32 Intel mimarisi Için Intel Sanallaştırma teknik belirtimi" belge numarası C97063-002 olan belgeyi arayın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__vmx_vmptrld`|x64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmptrst](../intrinsics/vmx-vmptrst.md)
