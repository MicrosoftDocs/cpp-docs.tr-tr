---
description: 'Hakkında daha fazla bilgi edinin: __vmx_off'
title: __vmx_off
ms.date: 09/02/2019
f1_keywords:
- __vmx_off
helpviewer_keywords:
- VMXOFF instruction
- __vmx_off intrinsic
ms.assetid: 78a32d46-9291-406c-b982-a550855aff18
ms.openlocfilehash: d36b9079165dd68b207658d6141bdf11bd9747cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333593"
---
# <a name="__vmx_off"></a>__vmx_off

**Microsoft'a Özgü**

İşlemcisinde sanal makine uzantıları (VMX) işlemini devre dışı bırakır.

## <a name="syntax"></a>Syntax

```C
void __vmx_off();
```

## <a name="remarks"></a>Açıklamalar

`__vmx_off`İşlev, `VMXOFF` makine yönergesine eşdeğerdir. Bu işlev, bir konağın sanal makine izleyicisinin Konuk işletim sistemiyle ve uygulamalarına yönelik etkileşimini destekler. Daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) SITESINDE "ıa-32 Intel mimarisi Için Intel Sanallaştırma teknik belirtimi" belge numarası C97063-002 olan belgeyi arayın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__vmx_off`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
