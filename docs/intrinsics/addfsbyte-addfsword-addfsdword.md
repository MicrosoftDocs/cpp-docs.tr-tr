---
title: __addfsbyte, __addfsword, __addfsdword
ms.date: 11/04/2016
f1_keywords:
- __addfsbyte_cpp
- __addfsdword
- __addfsword_cpp
- __addfsbyte
- __addfsword
- __addfsdword_cpp
helpviewer_keywords:
- __addfsdword intrinsic
- __addfsword intrinsic
- __addfsbyte intrinsic
ms.assetid: 706c70df-6b52-4401-9268-2977ed8ad715
ms.openlocfilehash: 477d8ddfe970c6d04e61a47eb4bb10e3fbc570de
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51329078"
---
# <a name="addfsbyte-addfsword-addfsdword"></a>__addfsbyte, __addfsword, __addfsdword

**Microsoft'a özgü**

Başlangıcına göre bir uzaklık tarafından belirtilen bellek konumuna bir değer ekleyin `FS` kesimi.

## <a name="syntax"></a>Sözdizimi

```
void __addfsbyte(
   unsigned long Offset,
   unsigned char Data
);
void __addfsword(
   unsigned long Offset,
   unsigned short Data
);
void __addfsdword(
   unsigned long Offset,
   unsigned long Data
);
```

#### <a name="parameters"></a>Parametreler

*uzaklık*<br/>
[in] Başından uzaklık `FS`.

*Veri*<br/>
[in] Bellek konumuna eklenecek değer.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|
|---------------|------------------|
|`__addfsbyte`|x86|
|`__addfsword`|x86|
|`__addfsdword`|x86|

## <a name="remarks"></a>Açıklamalar

Bu yordamlar, yalnızca iç öğe olarak kullanılabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[__incfsbyte, \__incfsword, \__incfsdword](../intrinsics/incfsbyte-incfsword-incfsdword.md)<br/>
[__readfsbyte, \__readfsdword, \__readfsqword, \__readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)<br/>
[__writefsbyte, \__writefsdword, \__writefsqword, \__writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)<br/>
[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)