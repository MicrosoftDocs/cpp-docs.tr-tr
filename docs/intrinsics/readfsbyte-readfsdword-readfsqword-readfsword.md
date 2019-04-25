---
title: __readfsbyte, __readfsdword, __readfsqword, __readfsword
ms.date: 11/04/2016
f1_keywords:
- __readfsword
- __readfsdword
- __readfsbyte
- __readfsqword
helpviewer_keywords:
- __readfsword intrinsic
- readfsword intrinsic
- __readfsdword intrinsic
- readfsbyte intrinsic
- __readfsbyte intrinsic
- readfsdword intrinsic
- readfsqword intrinsic
- __readfsqword intrinsic
ms.assetid: f6ee7203-4179-402c-a464-0746c84ce6ac
ms.openlocfilehash: f291747d1f46ebdf3ea1f71cd9ab7e074058201d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262742"
---
# <a name="readfsbyte-readfsdword-readfsqword-readfsword"></a>__readfsbyte, __readfsdword, __readfsqword, __readfsword

**Microsoft'a özgü**

Bellek FS kesim başlangıcına göre bir uzaklık tarafından belirtilen bir konumdan okunamıyor.

## <a name="syntax"></a>Sözdizimi

```
unsigned char __readfsbyte(
   unsigned long Offset
);
unsigned short __readfsword(
   unsigned long Offset
);
unsigned long __readfsdword(
   unsigned long Offset
);
unsigned __int64 __readfsqword(
   unsigned long Offset
);
```

#### <a name="parameters"></a>Parametreler

*uzaklık*<br/>
[in] Başından uzaklık `FS` okuma için.

## <a name="return-value"></a>Dönüş Değeri

Bayt, word, doubleword veya (çağrılan işlev adı tarafından belirtildiği şekilde) quadword bellek içeriğini konumda `FS:[Offset]`.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__readfsbyte`|x86|
|`__readfsdword`|x86|
|`__readfsqword`|x86|
|`__readfsword`|x86|

**Üst bilgi dosyası** \<intrin.h >

## <a name="remarks"></a>Açıklamalar

Bu yordamlar, yalnızca iç öğe olarak kullanılabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__writefsbyte, \__writefsdword, \__writefsqword, \__writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)<br/>
[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)