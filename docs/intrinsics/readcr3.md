---
description: 'Hakkında daha fazla bilgi edinin: __readcr3'
title: __readcr3
ms.date: 09/02/2019
f1_keywords:
- __readcr3
helpviewer_keywords:
- __readcr3 intrinsic
ms.assetid: e24392c3-cad7-4788-8f31-94bf2e9e0053
ms.openlocfilehash: f430694af6a54dde4839292a10a5267c000ccb86
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257348"
---
# <a name="__readcr3"></a>__readcr3

**Microsoft'a Özgü**

CR3 yazmacın okur ve değerini döndürür.

## <a name="syntax"></a>Sözdizimi

```C
unsigned __int64 __readcr3(void);
```

## <a name="return-value"></a>Döndürülen değer

CR3 kaydındaki değer.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__readcr3`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

## <a name="remarks"></a>Açıklamalar

İç öğe yalnızca çekirdek modunda kullanılabilir ve yordam yalnızca iç öğe olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
