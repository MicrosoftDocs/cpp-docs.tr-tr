---
title: rename_namespace | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- rename_namespace
dev_langs:
- C++
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 966c6dda7e5e0bd28e78f37967397c3b64e4e55c
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808478"
---
# <a name="renamenamespace"></a>rename_namespace

**C++ özgü**

Tür kitaplığı içeriğini içeren ad uzayı yeniden adlandırır.

## <a name="syntax"></a>Sözdizimi

```
rename_namespace("NewName")
```

### <a name="parameters"></a>Parametreler

*Yeni ad*<br/>
Yeni ad alanı adı.

## <a name="remarks"></a>Açıklamalar

Tek bir bağımsız değişken alan *NewName*, ad alanı için yeni adı belirtir.

Ad alanı kaldırmak için [no_namespace](../preprocessor/no-namespace.md) yerine özniteliği.

**END C++ özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)