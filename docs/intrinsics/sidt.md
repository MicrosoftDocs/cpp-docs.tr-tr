---
title: __sidt
ms.date: 11/04/2016
f1_keywords:
- __sidt
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
ms.openlocfilehash: 88dbb4713577fcf224e1c5646bf4c38b2a1dfafe
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59036766"
---
# <a name="sidt"></a>__sidt

**Microsoft'a Özgü**

Kesme tanımlayıcısı tablosu kaydı (IDTR) değeri, belirtilen bellek konumunda depolar.

## <a name="syntax"></a>Sözdizimi

```
void __sidt(void * Destination);
```

#### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Hedef*|[in] IDTR depolandığı konumun bellek işaretçisi.|

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__sidt`|x86, x64|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

`__sidt` İşlev, eşdeğer `SIDT` makine yönergesi. Belge için daha fazla bilgi için arama "Intel mimarisi yazılım geliştirici el ile 2 birim: Yönerge kümesi başvurusu"konumunda [Intel Corporation'da](https://software.intel.com/articles/intel-sdm) site.

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[__lidt](../intrinsics/lidt.md)