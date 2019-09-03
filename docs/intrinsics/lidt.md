---
title: __lidt
ms.date: 09/02/2019
f1_keywords:
- __lidt
- __lidt_cpp
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
ms.openlocfilehash: 24778b761ada56830b155a2fc65e90f54ba729ed
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217513"
---
# <a name="__lidt"></a>__lidt

**Microsoft 'a özgü**

Kesme tanımlayıcısı tablo kaydını (ıDTR) belirtilen bellek konumundaki değerle yükler.

## <a name="syntax"></a>Sözdizimi

```C
void __lidt(void * Source);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Kaynak*|'ndaki IDTR 'a kopyalanacak değere yönelik işaretçi.|

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__lidt`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

`__lidt` İşlevi `LIDT` makine yönergesine eşdeğerdir ve yalnızca çekirdek modunda kullanılabilir. Daha fazla bilgi için belgeyi arayın, "Intel mimarisi yazılım geliştiricisi El Ile, birim 2: Yönerge kümesi başvurusu, " [Intel Corporation](https://software.intel.com/articles/intel-sdm) sitesinde.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[__sidt](../intrinsics/sidt.md)
