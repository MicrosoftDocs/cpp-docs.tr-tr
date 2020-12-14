---
description: 'Hakkında daha fazla bilgi edinin: __addgsbyte, __addgsword, __addgsdword, __addgsqword'
title: __addgsbyte, __addgsword, __addgsdword, __addgsqword
ms.date: 09/02/2019
f1_keywords:
- __addgsdword
- __addgsqword
- __addgsword_cpp
- __addgsword
- __addgsbyte_cpp
- __addgsqword_cpp
- __addgsbyte
- __addgsdword_cpp
helpviewer_keywords:
- __addgsword intrinsic
- __addgsqword intrinsic
- __addgsdword intrinsic
- __addgsbyte intrinsic
ms.assetid: 4fa03e69-d849-49ed-ba37-1d3aa23c2a21
ms.openlocfilehash: e139eb573dc8a4e21bdddff3ba8c756d572c5218
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222508"
---
# <a name="__addgsbyte-__addgsword-__addgsdword-__addgsqword"></a>__addgsbyte, __addgsword, __addgsdword, __addgsqword

**Microsoft'a Özgü**

Segmentin başına göreli bir uzaklıktan belirtilen bellek konumuna bir değer ekleyin `GS` .

## <a name="syntax"></a>Sözdizimi

```C
void __addgsbyte(
   unsigned long Offset,
   unsigned char Data
);
void __addgsword(
   unsigned long Offset,
   unsigned short Data
);
void __addgsdword(
   unsigned long Offset,
   unsigned long Data
);
void __addgsqword(
   unsigned long Offset,
   unsigned __int64 Data
);
```

### <a name="parameters"></a>Parametreler

*Konumu*\
'ndaki Öğesinin başından itibaren olan fark `GS` .

*Verileri*\
'ndaki Bellek konumuna eklenecek değer.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__addgsbyte`|x64|
|`__addgsword`|x64|
|`__addgsdword`|x64|
|`__addgsqword`|x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

Bu yordamlar yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__incgsbyte, \_ _incgsword, \_ _incgsdword, \_ _incgsqword](../intrinsics/incgsbyte-incgsword-incgsdword-incgsqword.md)\
[__readgsbyte, \_ _readgsdword, \_ _readgsqword, \_ _readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)\
[__writegsbyte, \_ _writegsdword, \_ _writegsqword, \_ _writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
