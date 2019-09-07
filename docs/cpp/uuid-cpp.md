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
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740457"
---
# <a name="uuid-c"></a>uuid (C++)

**Microsoft 'a özgü**

Derleyici, bir GUID veya tanımlanmış bir sınıfa veya yapıya (yalnızca tam COM nesne tanımları) **UUID** özniteliğiyle iliştirir.

## <a name="syntax"></a>Sözdizimi

```
__declspec( uuid("ComObjectGUID") ) declarator
```

## <a name="remarks"></a>Açıklamalar

**UUID** özniteliği bağımsız değişkeni olarak bir dize alır. Bu dize, **{}** sınırlayıcılarını içeren veya içermeyen normal kayıt defteri BIÇIMINDEKI bir GUID 'yi adlandırır. Örneğin:

```cpp
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;
```

Bu öznitelik bir yeniden bildirimde uygulanabilir. Bu, sistem üstbilgilerinin gibi arabirimlerin `IUnknown`tanımlarını sağlamasına ve diğer bir başlıktaki ( \<Comdef. h > gibi) yeniden bildirime GUID sağlamak için izin verir.

[__Uuidof](../cpp/uuidof-operator.md) anahtar sözcüğü, Kullanıcı tanımlı bir türe eklenen sabit GUID 'yi almak için uygulanabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)