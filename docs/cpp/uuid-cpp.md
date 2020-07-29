---
title: uuid (C++)
ms.date: 11/04/2016
f1_keywords:
- uuid_cpp
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
ms.openlocfilehash: f775820fe7f84c5081a213ca9ecb07d617716a9d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226990"
---
# <a name="uuid-c"></a>uuid (C++)

**Microsoft'a Özgü**

Derleyici, belirtilen veya tanımlanmış bir sınıfa veya yapıya bir GUID ekler (yalnızca tam COM nesne tanımları) **`uuid`** özniteliği ile.

## <a name="syntax"></a>Sözdizimi

```
__declspec( uuid("ComObjectGUID") ) declarator
```

## <a name="remarks"></a>Açıklamalar

**`uuid`** Özniteliği bağımsız değişkeni olarak bir dize alır. Bu dize, **{}** sınırlayıcılarını içeren veya içermeyen normal kayıt defteri BIÇIMINDEKI bir GUID 'yi adlandırır. Örnek:

```cpp
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;
```

Bu öznitelik bir yeniden bildirimde uygulanabilir. Bu, sistem üstbilgilerinin, gibi arabirimlerin tanımlarını sağlamasına `IUnknown` ve diğer bir başlıktaki (gibi) yeniden BILDIRIME GUID sağlamak için izin verir \<comdef.h> .

Anahtar sözcüğü [__uuidof](../cpp/uuidof-operator.md) , Kullanıcı tanımlı bir türe eklenen sabit GUID 'i almak için uygulanabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
