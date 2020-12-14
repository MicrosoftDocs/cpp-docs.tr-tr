---
description: 'Hakkında daha fazla bilgi edinin: messages_base sınıfı'
title: messages_base Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmes/std::messages_base
helpviewer_keywords:
- messages_base class
ms.assetid: 9aad38c6-4c13-445d-b096-364bd0836efb
ms.openlocfilehash: 45ea81b02bd15011c9f98b9364ea9918e248692a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230594"
---
# <a name="messages_base-class"></a>messages_base Sınıfı

Temel sınıf, **`int`** ileti kataloğu için bir tür tanımlar.

## <a name="syntax"></a>Syntax

```cpp
struct messages_base : locale::facet {
    typedef int catalog;
    explicit messages_base(size_t _Refs = 0)
};
```

## <a name="remarks"></a>Açıklamalar

Tür kataloğu, **`int`** iletilerden gelen olası dönüş değerlerini açıklayan tür için bir eş anladır:: [do_open](../standard-library/messages-class.md#do_open).

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
