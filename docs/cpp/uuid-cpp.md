---
title: uuid (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- uuid_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44799b507fb9c27cb1d9f166e86228ed6003a0d8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086193"
---
# <a name="uuid-c"></a>uuid (C++)

**Microsoft'a özgü**

Derleyici bir sınıf veya bildirildi veya tanımlandı yapısı (tam COM nesne tanımları yalnızca) ile bir GUID ekler **UUID** özniteliği.

## <a name="syntax"></a>Sözdizimi

```
__declspec( uuid("ComObjectGUID") ) declarator
```

## <a name="remarks"></a>Açıklamalar

**UUID** öznitelik bağımsız değişkeni olarak bir dize alır. Bu dize olan veya olmayan normal kayıt biçiminde bir GUID adları **{}** sınırlayıcı. Örneğin:

```cpp
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;
```

Bu öznitelik, bir yeniden bildirimi içinde uygulanabilir. Bu arabirimlerin tanımları gibi sağlamak sistem üstbilgileri sağlar `IUnknown`ve başka bir üst bilgisindeki yeniden bildirimi (gibi \<comdef.h >) GUID sağlamak için.

Anahtar sözcüğü [__uuidof](../cpp/uuidof-operator.md) GUID bağlı kullanıcı tanımlı bir tür sabiti almak için uygulanabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)