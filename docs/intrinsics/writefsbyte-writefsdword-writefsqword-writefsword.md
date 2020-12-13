---
description: 'Hakkında daha fazla bilgi edinin: __writefsbyte, __writefsdword, __writefsqword, __writefsword'
title: __writefsbyte, __writefsdword, __writefsqword, __writefsword
ms.date: 09/02/2019
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
ms.openlocfilehash: cde85cd7fea5b65ced127da96033ecc5b1f4f058
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136064"
---
# <a name="__writefsbyte-__writefsdword-__writefsqword-__writefsword"></a>__writefsbyte, __writefsdword, __writefsqword, __writefsword

**Microsoft'a Özgü**

FS segmentinin başlangıcına göre bir uzaklıktan belirtilen bir konuma bellek yazın.

## <a name="syntax"></a>Sözdizimi

```C
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

### <a name="parameters"></a>Parametreler

*Konumu*\
'ndaki Yazılacak FS 'nin başından sonuna kadar olan fark.

*Verileri*\
'ndaki Yazılacak değer.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__writefsbyte`|x86|
|`__writefsword`|x86|
|`__writefsdword`|x86|
|`__writefsqword`|x86|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu yordamlar yalnızca iç bilgiler olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__readfsbyte, \_ _readfsdword, \_ _readfsqword, \_ _readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
