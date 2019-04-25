---
title: tlbid
ms.date: 10/18/2018
f1_keywords:
- tlbid
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
ms.openlocfilehash: ae79ce9245bb1c0425c3e9b92dd27b52fa443dba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179613"
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

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)