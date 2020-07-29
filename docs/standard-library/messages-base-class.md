---
title: messages_base Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmes/std::messages_base
helpviewer_keywords:
- messages_base class
ms.assetid: 9aad38c6-4c13-445d-b096-364bd0836efb
ms.openlocfilehash: b0fe7d66842fb77c6fd03f62b012babcbc9f7f3a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215653"
---
# <a name="messages_base-class"></a>messages_base Sınıfı

Temel sınıf, **`int`** ileti kataloğu için bir tür tanımlar.

## <a name="syntax"></a>Sözdizimi

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
