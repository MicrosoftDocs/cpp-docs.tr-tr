---
description: 'Daha fazla bilgi edinin: UUID (C++)'
title: uuid (C++)
ms.date: 11/04/2016
f1_keywords:
- uuid_cpp
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
ms.openlocfilehash: c841bb1813769ab70e756fe4edb7fd351c1dbc49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116737"
---
# <a name="uuid-c"></a>uuid (C++)

**Microsoft'a Özgü**

Derleyici, belirtilen veya tanımlanmış bir sınıfa veya yapıya bir GUID ekler (yalnızca tam COM nesne tanımları) **`uuid`** özniteliği ile.

## <a name="syntax"></a>Syntax

```
__declspec( uuid("ComObjectGUID") ) declarator
```

## <a name="remarks"></a>Açıklamalar

**`uuid`** Özniteliği bağımsız değişkeni olarak bir dize alır. Bu dize, **{}** sınırlayıcılarını içeren veya içermeyen normal kayıt defteri BIÇIMINDEKI bir GUID 'yi adlandırır. Örneğin:

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
