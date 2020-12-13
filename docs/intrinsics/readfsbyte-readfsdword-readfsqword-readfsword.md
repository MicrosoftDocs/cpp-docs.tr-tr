---
description: 'Hakkında daha fazla bilgi edinin: __readfsbyte, __readfsdword, __readfsqword, __readfsword'
title: __readfsbyte, __readfsdword, __readfsqword, __readfsword
ms.date: 09/02/2019
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
ms.openlocfilehash: 2b733ced12045253c78e823379c10a5e70f65143
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340989"
---
# <a name="__readfsbyte-__readfsdword-__readfsqword-__readfsword"></a>__readfsbyte, __readfsdword, __readfsqword, __readfsword

**Microsoft'a Özgü**

FS segmentinin başına göreli bir uzaklıktan belirtilen bir konumdan belleği okuyun.

## <a name="syntax"></a>Sözdizimi

```C
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

### <a name="parameters"></a>Parametreler

*Konumu*\
'ndaki Öğesinden okunacak kadar olan Aralık `FS` .

## <a name="return-value"></a>Döndürülen değer

Konumdaki Byte, Word, doubleword veya quadword (çağrılan işlevin adıyla gösterildiği gibi) bellek içeriği `FS:[Offset]` .

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__readfsbyte`|x86|
|`__readfsdword`|x86|
|`__readfsqword`|x86|
|`__readfsword`|x86|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu yordamlar yalnızca iç bilgiler olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__writefsbyte, \_ _writefsdword, \_ _writefsqword, \_ _writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
