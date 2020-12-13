---
description: 'Hakkında daha fazla bilgi edinin: __readgsbyte, __readgsdword, __readgsqword, __readgsword'
title: __readgsbyte, __readgsdword, __readgsqword, __readgsword
ms.date: 09/02/2019
f1_keywords:
- __readgsbyte
- __readgsdword
- __readgsqword
- __readgsword
helpviewer_keywords:
- __readgsword intrinsic
- __readgsdword intrinsic
- __readgsqword intrinsic
- __readgsbyte intrinsic
ms.assetid: f822632d-854c-4558-a71b-cdfc3eea2236
ms.openlocfilehash: fb1faf0e785f0d0983d7d3611e68a7515298e61c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340976"
---
# <a name="__readgsbyte-__readgsdword-__readgsqword-__readgsword"></a>__readgsbyte, __readgsdword, __readgsqword, __readgsword

**Microsoft'a Özgü**

GS segmentinin başlangıcına göre bir uzaklıktan belirtilen konumdan belleği okuyun.

## <a name="syntax"></a>Sözdizimi

```C
unsigned char __readgsbyte(
   unsigned long Offset
);
unsigned short __readgsword(
   unsigned long Offset
);
unsigned long __readgsdword(
   unsigned long Offset
);
unsigned __int64 __readgsqword(
   unsigned long Offset
);
```

### <a name="parameters"></a>Parametreler

*Konumu*\
'ndaki Öğesinden okunacak kadar olan Aralık `GS` .

## <a name="return-value"></a>Döndürülen değer

Konumun bayt, sözcük, çift sözcük veya quadword (çağrılan işlevin adıyla gösterildiği gibi) bellek içeriği `GS:[Offset]` .

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__readgsbyte`|x64|
|`__readgsdword`|x64|
|`__readgsqword`|x64|
|`__readgsword`|x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu yordamlar yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__writegsbyte, \_ _writegsdword, \_ _writegsqword, \_ _writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
