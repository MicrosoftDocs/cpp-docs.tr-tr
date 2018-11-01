---
title: tlbid
ms.date: 10/18/2018
f1_keywords:
- tlbid
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
ms.openlocfilehash: 31b71f7c195a7e2ee649b40197551e4ff5efda2c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584524"
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