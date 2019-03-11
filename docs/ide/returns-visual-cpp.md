---
title: '&lt;döndürür&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- returns C++ XML tag
- <returns> C++ XML tag
ms.assetid: 5e3b0ed9-838d-4953-a93e-76d2d0a19fb9
ms.openlocfilehash: 7861d57d474db3c45b2c773a057a545c15602822
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740848"
---
# <a name="ltreturnsgt-visual-c"></a>&lt;döndürür&gt; (Visual C++)

\<Döndürür > etiketi yöntemi bildirimi için açıklama dönüş değeri tanımlamak için kullanılmalıdır.

## <a name="syntax"></a>Sözdizimi

```
<returns>description</returns>
```

#### <a name="parameters"></a>Parametreler

*Açıklaması*<br/>
Dönüş değeri bir açıklaması.

## <a name="remarks"></a>Açıklamalar

Derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.

## <a name="example"></a>Örnek

```
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

[XML Belgeleri](../ide/xml-documentation-visual-cpp.md)
