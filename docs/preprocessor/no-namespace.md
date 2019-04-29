---
title: no_namespace
ms.date: 11/04/2016
f1_keywords:
- no_namespace
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
ms.openlocfilehash: f6bd60de02bf0166d5cf0b0cd1bc1de56ceda5bf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62326566"
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

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)