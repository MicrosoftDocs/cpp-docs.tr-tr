---
title: '&lt;> döndürür (C++ belge açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- returns C++ XML tag
- <returns> C++ XML tag
ms.assetid: 5e3b0ed9-838d-4953-a93e-76d2d0a19fb9
ms.openlocfilehash: 1315ec09271c2c97f7bcaf3fb6f9c75f514b5d2d
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988637"
---
# <a name="ltreturnsgt"></a>&lt;&gt; döndürür

\<, dönüş değerini açıklayacak bir yöntem bildirimine ilişkin açıklamada > etiketini döndürür.

## <a name="syntax"></a>Sözdizimi

```
<returns>description</returns>
```

#### <a name="parameters"></a>Parametreler

*description*<br/>
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
