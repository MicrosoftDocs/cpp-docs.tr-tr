---
title: bad_exception sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- exception/std::bad_exception
dev_langs:
- C++
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3b1b332b4f76f24f873fd8a57d302fc2643a71f1
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="badexception-class"></a>bad_exception Class

Beklenmeyen bir işleyicisinden oluşturulan bir özel durum sınıfı tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class bad_exception    : public exception {};
```

## <a name="remarks"></a>Açıklamalar

[Beklenmeyen](../standard-library/exception-functions.md#unexpected) özel durum oluşturacak bir `bad_exception` sonlandırma yerine veya ile belirtilen başka bir işlevi çağırmak yerine [set_unexpected](../standard-library/exception-functions.md#set_unexpected) varsa `bad_exception` işlevi throw listesinde yer.

Tarafından döndürülen değer **ne** bir uygulama tanımlı C dize. Üye işlevleri hiçbiri tüm özel durumlar oluşturma.

Tarafından devralınan üyelerin listesi için `bad_exception` sınıfı için bkz: [özel durum sınıfı](../standard-library/exception-class.md).

## <a name="example"></a>Örnek

Bkz: [set_unexpected](../standard-library/exception-functions.md#set_unexpected) kullanımına ilişkin bir örnek [beklenmeyen](../standard-library/exception-functions.md#unexpected) atma bir `bad_exception`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<özel durum >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[exception Sınıfı](../standard-library/exception-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
