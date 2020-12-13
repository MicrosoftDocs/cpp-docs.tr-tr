---
description: 'Daha fazla bilgi edinin: tldeklarasyon içeri aktarma özniteliği'
title: tldeklarasyon içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- tlbid
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
ms.openlocfilehash: 9bbf15f64c1813013fcd839a2d4f0a34c9872aff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339047"
---
# <a name="tlbid-import-attribute"></a>tldeklarasyon içeri aktarma özniteliği

**C++ özel**

Birincil tür kitaplığı dışındaki kitaplıkların yüklenmesine izin verir.

## <a name="syntax"></a>Syntax

> **#import** *türü-Library-DLL* **tldeklarasyon (** *sayı* **)**

### <a name="parameters"></a>Parametreler

*sayısından*\
*Type-Library-DLL* içindeki tür kitaplığının numarası.

## <a name="remarks"></a>Açıklamalar

Birden çok tür kitaplığı tek bir DLL 'de yerleşik ise, **tldeklarasyon** kullanarak birincil tür kitaplığı dışındaki kitaplıkları yüklemek mümkündür.

Örneğin:

```cpp
#import <MyResource.dll> tlbid(2)
```

eşittir:

```cpp
LoadTypeLib("MyResource.dll\\2");
```

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
