---
title: __incfsbyte, __incfsword, __incfsdword
ms.date: 11/04/2016
f1_keywords:
- __incfsword
- __incfsbyte_cpp
- __incfsbyte
- __incfsdword
- __incfsword_cpp
- __incfsdword_cpp
helpviewer_keywords:
- __incfsword intrinsic
- __incfsdword intrinsic
- __incfsbyte intrinsic
ms.assetid: 820457fb-e35e-42d3-bcb6-725da3281c64
ms.openlocfilehash: 9e1e2630f8c0a66b681be2aa550f9c9255c92173
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59027009"
---
# <a name="incfsbyte-incfsword-incfsdword"></a>__incfsbyte, __incfsword, __incfsdword

**Microsoft'a özgü**

Bir değere başlangıcına göre bir uzaklık tarafından belirtilen bellek konumunda ekleme `FS` kesimi.

## <a name="syntax"></a>Sözdizimi

```
void __incfsbyte(
   unsigned long Offset
);
void __incfsword(
   unsigned long Offset
);
void __incfsdword(
   unsigned long Offset
);
```

#### <a name="parameters"></a>Parametreler

*uzaklık*<br/>
[in] Başından uzaklık `FS`.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__incfsbyte`|x86|
|`__incfsword`|x86|
|`__incfsdword`|x86|

## <a name="remarks"></a>Açıklamalar

Bu iç öğeler yalnızca çekirdek modunda kullanılabilir ve yordamlar yalnızca iç öğe olarak kullanılabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__addfsbyte, \__addfsword, \__addfsdword](../intrinsics/addfsbyte-addfsword-addfsdword.md)<br/>
[__readfsbyte, \__readfsdword, \__readfsqword, \__readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)<br/>
[__writefsbyte, \__writefsdword, \__writefsqword, \__writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)<br/>
[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)