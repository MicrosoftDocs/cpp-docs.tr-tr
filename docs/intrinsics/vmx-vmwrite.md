---
description: 'Hakkında daha fazla bilgi edinin: __vmx_vmwrite'
title: __vmx_vmwrite
ms.date: 09/02/2019
f1_keywords:
- __vmx_vmwrite
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
ms.openlocfilehash: d8902d51b05fa96faf22cbb6d80400e1f67c5f3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257309"
---
# <a name="__vmx_vmwrite"></a>__vmx_vmwrite

**Microsoft'a Özgü**

Belirtilen değeri geçerli sanal makine denetim yapısında (VMCS) belirtilen alana yazar.

## <a name="syntax"></a>Sözdizimi

```C
unsigned char __vmx_vmwrite(
   size_t Field,
   size_t FieldValue
);
```

### <a name="parameters"></a>Parametreler

*Alanla*\
'ndaki Yazılacak VMCS alanı.

*Alandeğeri*\
'ndaki VMCS alanına yazılacak değer.

## <a name="return-value"></a>Döndürülen değer

0
İşlem başarılı oldu.

1
İşlem, geçerli VNET 'lerin içinde kullanılabilir olan genişletilmiş durumla başarısız oldu `VM-instruction error field` .

iki
İşlem durum kullanılabilir olmadan başarısız oldu.

## <a name="remarks"></a>Açıklamalar

`__vmx_vmwrite`İşlev, `VMWRITE` makine yönergesine eşdeğerdir. Parametresinin değeri, `Field` Intel belgelerinde açıklanan, kodlanmış bir alan dizinidir. Daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) SITESINDE "ıa-32 Intel mimarisi Için Intel Sanallaştırma teknik belirtimi" başlıklı Ek C 'yi arayın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__vmx_vmwrite`|x64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__vmx_vmread](../intrinsics/vmx-vmread.md)
