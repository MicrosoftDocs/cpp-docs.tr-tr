---
title: messages_base Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmes/std::messages_base
helpviewer_keywords:
- messages_base class
ms.assetid: 9aad38c6-4c13-445d-b096-364bd0836efb
ms.openlocfilehash: 750c9f36ce7f96a065e0e29111ea379a48595328
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167770"
---
# <a name="messagesbase-class"></a>messages_base Sınıfı

Temel sınıf açıklayan bir **int** iletilerin kataloğu için türü.

## <a name="syntax"></a>Sözdizimi

```cpp
struct messages_base : locale::facet {
    typedef int catalog;
    explicit messages_base(size_t _Refs = 0)
};
```

## <a name="remarks"></a>Açıklamalar

Türe ilişkin bir eşanlam türü kataloğudur **int** iletileri olası dönüş değerlerini açıklayan:: [do_open](../standard-library/messages-class.md#do_open).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
