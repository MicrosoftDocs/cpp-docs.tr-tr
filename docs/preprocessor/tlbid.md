---
title: tldeklarasyon içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- tlbid
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
ms.openlocfilehash: 364fb224b0f2769cb0933e71d18ff70768189328
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216539"
---
# <a name="tlbid-import-attribute"></a>tldeklarasyon içeri aktarma özniteliği

**C++Belirli**

Birincil tür kitaplığı dışındaki kitaplıkların yüklenmesine izin verir.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür-kitaplık-dll* **tldeklarasyon (** *sayı* **)**

### <a name="parameters"></a>Parametreler

*sayısından*\
*Type-Library-DLL*içindeki tür kitaplığının numarası.

## <a name="remarks"></a>Açıklamalar

Birden çok tür kitaplığı tek bir DLL 'de yerleşik ise, **tldeklarasyon**kullanarak birincil tür kitaplığı dışındaki kitaplıkları yüklemek mümkündür.

Örneğin:

```cpp
#import <MyResource.dll> tlbid(2)
```

eşdeğerdir:

```cpp
LoadTypeLib("MyResource.dll\\2");
```

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
