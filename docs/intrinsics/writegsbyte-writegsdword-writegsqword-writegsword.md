---
description: 'Hakkında daha fazla bilgi edinin: __writegsbyte, __writegsdword, __writegsqword, __writegsword'
title: __writegsbyte, __writegsdword, __writegsqword, __writegsword
ms.date: 09/02/2019
f1_keywords:
- __writegsbyte
- __writegsqword
- __writegsdword
- __writegsword
helpviewer_keywords:
- __writegsqword intrinsic
- __writegsbyte intrinsic
- __writegsword intrinsic
- __writegsdword intrinsic
ms.assetid: 7746cf6d-2259-4139-9aab-c07dd75c8037
ms.openlocfilehash: e3dd3284d38f4c1518fbf5f7184d15fc0c9d67d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331835"
---
# <a name="__writegsbyte-__writegsdword-__writegsqword-__writegsword"></a>__writegsbyte, __writegsdword, __writegsqword, __writegsword

**Microsoft'a Özgü**

GS segmentinin başlangıcına göre bir uzaklıktan belirtilen bir konuma bellek yazın.

## <a name="syntax"></a>Sözdizimi

```C
void __writegsbyte(
   unsigned long Offset,
   unsigned char Data
);
void __writegsword(
   unsigned long Offset,
   unsigned short Data
);
void __writegsdword(
   unsigned long Offset,
   unsigned long Data
);
void __writegsqword(
   unsigned long Offset,
   unsigned __int64 Data
);
```

### <a name="parameters"></a>Parametreler

*Konumu*\
'ndaki Başlangıç olarak, yazılacak kadar olan Aralık.

*Verileri*\
'ndaki Yazılacak değer.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__writegsbyte`|x64|
|`__writegsdword`|x64|
|`__writegsqword`|x64|
|`__writegsword`|x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu yordamlar yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__readgsbyte, \_ _readgsdword, \_ _readgsqword, \_ _readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
