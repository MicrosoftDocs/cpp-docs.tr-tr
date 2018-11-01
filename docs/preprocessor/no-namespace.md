---
title: no_namespace
ms.date: 11/04/2016
f1_keywords:
- no_namespace
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
ms.openlocfilehash: b17bf5fb5f44d5453de29febe001f9e8737102b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540445"
---
# <a name="nonamespace"></a>no_namespace
**C++ özgü**

Ad alanı adı derleyici tarafından oluşturulmayan belirtir.

## <a name="syntax"></a>Sözdizimi

```
no_namespace
```

## <a name="remarks"></a>Açıklamalar

Tür kitaplığı içeriğini içinde `#import` üstbilgi dosyası normalde bir ad alanında tanımlı. Ad alanı adı belirtilen `library` özgün IDL dosyası ifadesi. Varsa **no_namespace** özniteliği belirtilmediyse, sonra bu ad alanı, derleyici tarafından oluşturulmaz.

Farklı bir ad kullanmak istiyorsanız, ardından kullanmak [rename_namespace](../preprocessor/rename-namespace.md) yerine özniteliği.

**END C++ özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)