---
description: 'Daha fazla bilgi edinin: &lt; açıklamalar&gt;'
title: '&lt;açıklamalar> (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- <remarks>
helpviewer_keywords:
- <remarks> C++ XML tag
- remarks C++ XML tag
ms.assetid: c820083b-3192-40ab-9ec8-1472c55b4247
ms.openlocfilehash: 3e3590bff827606ad38f3772b72fa4e79563c2e1
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126097"
---
# <a name="ltremarksgt"></a>&lt;açıklamalarının&gt;

\<remarks>Etiketi, ile belirtilen bilgileri kullanarak bir tür hakkında bilgi eklemek için kullanılır [\<summary>](summary-visual-cpp.md) . Bu bilgiler [nesne tarayıcısı](/visualstudio/ide/viewing-the-structure-of-code) ve kod açıklaması Web raporunda görüntülenir.

## <a name="syntax"></a>Sözdizimi

```
<remarks>description</remarks>
```

#### <a name="parameters"></a>Parametreler

*açıklaması*<br/>
Üyenin açıklaması.

## <a name="remarks"></a>Açıklamalar

Belge açıklamalarını bir dosyaya işlemek için [/doc](doc-process-documentation-comments-c-cpp.md) ile derleyin.

## <a name="example"></a>Örnek

```cpp
// xml_remarks_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_remarks_tag.dll

using namespace System;

/// <summary>
/// You may have some primary information about this class.
/// </summary>
/// <remarks>
/// You may have some additional information about this class.
/// </remarks>
public ref class MyClass {};
```

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](xml-documentation-visual-cpp.md)
