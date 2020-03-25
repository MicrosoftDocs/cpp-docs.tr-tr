---
title: uuid (C++)
ms.date: 11/04/2016
f1_keywords:
- uuid_cpp
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
ms.openlocfilehash: 09e40d38382bea0f902fda03d15d24e0cf1a627d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187810"
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

Bu öznitelik bir yeniden bildirimde uygulanabilir. Bu, sistem üstbilgilerinin `IUnknown`gibi arabirimlerin tanımlarını sağlamasına izin verir ve diğer bir başlıktaki (örneğin \<Comdef. h >) bir yeniden bildirimi GUID sağlar.

Anahtar sözcüğü [__uuidof](../cpp/uuidof-operator.md) , Kullanıcı tanımlı bir türe eklenen sabit GUID 'i almak için uygulanabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
