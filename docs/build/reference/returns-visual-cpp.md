---
description: 'Daha fazla bilgi edinin: &lt; dönüşler&gt;'
title: '&lt;> döndürür (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- <returns>
helpviewer_keywords:
- returns C++ XML tag
- <returns> C++ XML tag
ms.assetid: 5e3b0ed9-838d-4953-a93e-76d2d0a19fb9
ms.openlocfilehash: 59b9a7d33a3b2695a2a5e22fdac465f17c915492
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126123"
---
# <a name="ltreturnsgt"></a>&lt;döndürdüğü&gt;

\<returns>Etiket, dönüş değerini betimleyen bir yöntem bildirimine ilişkin açıklamada kullanılmalıdır.

## <a name="syntax"></a>Sözdizimi

```
<returns>description</returns>
```

#### <a name="parameters"></a>Parametreler

*açıklaması*<br/>
Dönüş değerinin açıklaması.

## <a name="remarks"></a>Açıklamalar

Belge açıklamalarını bir dosyaya işlemek için [/doc](doc-process-documentation-comments-c-cpp.md) ile derleyin.

## <a name="example"></a>Örnek

```cpp
// xml_returns_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_returns_tag.dll

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <returns>Returns zero.</returns>
   int GetZero() { return 0; }
};
```

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](xml-documentation-visual-cpp.md)
