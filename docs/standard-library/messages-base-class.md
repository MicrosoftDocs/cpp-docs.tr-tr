---
title: messages_base sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmes/std::messages_base
dev_langs:
- C++
helpviewer_keywords:
- messages_base class
ms.assetid: 9aad38c6-4c13-445d-b096-364bd0836efb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e402f103a29dd4c4af49fa1c34b9cae71fc6e9af
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964853"
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
