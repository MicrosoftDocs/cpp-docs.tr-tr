---
title: __lidt
ms.date: 11/04/2016
f1_keywords:
- __lidt
- __lidt_cpp
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
ms.openlocfilehash: 757309603af48820a17668cfe272bbeaad9239b3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62263691"
---
# <a name="lidt"></a>__lidt

**Microsoft'a özgü**

Değer belirtilen bellek konumunda bulunan kesme tanımlayıcısı tablosu kaydı (IDTR) yükler.

## <a name="syntax"></a>Sözdizimi

```
void __lidt(void * Source);
```

#### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Kaynak*|[in] İşaretçi değeri için IDTR kopyalanacak.|

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__lidt`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

`__lidt` İşlev, eşdeğer `LIDT` makine yönerge ve yalnızca çekirdek modunda kullanılabilir. Belge için daha fazla bilgi için arama "Intel mimarisi yazılım geliştirici el ile 2 birim: Yönerge kümesi başvurusu"konumunda [Intel Corporation'da](https://software.intel.com/articles/intel-sdm) site.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__sidt](../intrinsics/sidt.md)