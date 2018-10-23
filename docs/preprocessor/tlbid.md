---
title: tlbıd | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- tlbid
dev_langs:
- C++
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6324ec9a64a0d1c47dab8d1beee021f6c8752a96
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49807984"
---
# <a name="tlbid"></a>tlbid

**C++ özgü**

Birincil tür kitaplığı dışında kitaplıklarını yüklemek için sağlar.

## <a name="syntax"></a>Sözdizimi

```
tlbid(number)
```

### <a name="parameters"></a>Parametreler

*Sayı*<br/>
Tür Kitaplığı'nda sayısını `filename`.

## <a name="remarks"></a>Açıklamalar

Birden çok tür kitaplıklarının tek bir DLL'nin, birincil tür kitaplığı dışında kitaplıkları kullanarak yüklemek mümkün içinde yerleşik olan, **tlbıd**.

Örneğin:

```cpp
#import <MyResource.dll> tlbid(2)
```

eşdeğerdir:

```cpp
LoadTypeLib("MyResource.dll\\2");
```

**END C++ özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)