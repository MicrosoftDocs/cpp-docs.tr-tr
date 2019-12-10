---
title: '&lt;açıklamalar > (C++ belge açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- <remarks> C++ XML tag
- remarks C++ XML tag
ms.assetid: c820083b-3192-40ab-9ec8-1472c55b4247
ms.openlocfilehash: 096280526b12feff33377a705f7c03548a1f0f13
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988655"
---
# <a name="ltremarksgt"></a>&lt;açıklamalar&gt;

\<açıklamalar > etiketi, [\<özet >](summary-visual-cpp.md)ile belirtilen bilgileri kullanarak bir tür hakkında bilgi eklemek için kullanılır. Bu bilgiler [nesne tarayıcısı](/visualstudio/ide/viewing-the-structure-of-code) ve kod açıklaması Web raporunda görüntülenir.

## <a name="syntax"></a>Sözdizimi

```
<remarks>description</remarks>
```

#### <a name="parameters"></a>Parametreler

*description*<br/>
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
