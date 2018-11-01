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
ms.openlocfilehash: 2ed21b1a7b0bca12185e054b3b5452e0bf04d4d7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494516"
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

## <a name="see-also"></a>Ayrıca Bkz.

[XML Belgeleri](../ide/xml-documentation-visual-cpp.md)