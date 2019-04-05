---
title: tlbid
ms.date: 10/18/2018
f1_keywords:
- tlbid
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
ms.openlocfilehash: ae79ce9245bb1c0425c3e9b92dd27b52fa443dba
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037947"
---
# <a name="tlbid"></a>tlbid

**C++ özgü**

Birincil tür kitaplığı dışında kitaplıklarını yüklemek için sağlar.

## <a name="syntax"></a>Sözdizimi

```
tlbid(number)
```

### <a name="parameters"></a>Parametreler

*sayı*<br/>
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

## <a name="see-also"></a>Ayrıca bkz.

[#import Öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import Yönergesi](../preprocessor/hash-import-directive-cpp.md)