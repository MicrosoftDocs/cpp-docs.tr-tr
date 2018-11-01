---
title: uuid (C++)
ms.date: 11/04/2016
f1_keywords:
- uuid_cpp
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
ms.openlocfilehash: c121ad99dfbe0021a263f324ccdb9a95441bba33
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511663"
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