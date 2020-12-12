---
description: 'Hakkında daha fazla bilgi edinin: __lidt'
title: __lidt
ms.date: 09/02/2019
f1_keywords:
- __lidt
- __lidt_cpp
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
ms.openlocfilehash: 9b9f4bc51bab07a578671932c16548a0a49d155b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167779"
---
# <a name="__lidt"></a>__lidt

**Microsoft'a Özgü**

Kesme tanımlayıcısı tablo kaydını (ıDTR) belirtilen bellek konumundaki değerle yükler.

## <a name="syntax"></a>Sözdizimi

```C
void __lidt(void * Source);
```

### <a name="parameters"></a>Parametreler

*Kaynaktaki*\
'ndaki IDTR 'a kopyalanacak değere yönelik işaretçi.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__lidt`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

`__lidt`İşlevi `LIDT` makine yönergesine eşdeğerdir ve yalnızca çekirdek modunda kullanılabilir. Daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) sitesinde "Intel mimarisi yazılım geliştiricisi el kitabı, toplu 2: yönerge kümesi başvurusu" belgesinde arama yapın.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__sidt](../intrinsics/sidt.md)
