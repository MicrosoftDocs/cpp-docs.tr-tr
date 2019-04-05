---
title: __writefsbyte, __writefsdword, __writefsqword, __writefsword
ms.date: 11/04/2016
f1_keywords:
- __writefsword
- __writefsbyte
- __writefsqword
- __writefsdword
helpviewer_keywords:
- writefsbyte intrinsic
- __writefsword intrinsic
- writefsqword intrinsic
- writefsdword intrinsic
- __writefsdword intrinsic
- __writefsqword intrinsic
- __writefsbyte intrinsic
- writefsword intrinsic
ms.assetid: 23ac6e8e-bc91-4e90-a4c6-da02993637ad
ms.openlocfilehash: 6461ef730760298e3159e4ac70dbbdf7bd827092
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025787"
---
# <a name="writefsbyte-writefsdword-writefsqword-writefsword"></a>__writefsbyte, __writefsdword, __writefsqword, __writefsword

**Microsoft'a Özgü**

Bellek FS kesim başlangıcına göre bir uzaklık tarafından belirtilen bir konuma yazma.

## <a name="syntax"></a>Sözdizimi

```
void __writefsbyte(
   unsigned long Offset,
   unsigned char Data
);
void __writefsword(
   unsigned long Offset,
   unsigned short Data
);
void __writefsdword(
   unsigned long Offset,
   unsigned long Data
);
void __writefsqword(
   unsigned long Offset,
   unsigned __int64 Data
);
```

#### <a name="parameters"></a>Parametreler

*Uzaklık*<br/>
[in] Yazılacak FS başından uzaklığı.

*Veri*<br/>
[in] Yazılacak değer.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__writefsbyte`|x86|
|`__writefsword`|x86|
|`__writefsdword`|x86|
|`__writefsqword`|x86|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu yordamlar, yalnızca iç öğe olarak kullanılabilir.

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__readfsbyte, \__readfsdword, \__readfsqword, \__readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)<br/>
[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)