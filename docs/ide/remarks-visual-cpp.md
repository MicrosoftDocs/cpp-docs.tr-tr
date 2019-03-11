---
title: '&lt;Açıklamalar&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- <remarks> C++ XML tag
- remarks C++ XML tag
ms.assetid: c820083b-3192-40ab-9ec8-1472c55b4247
ms.openlocfilehash: 2a897b20cbee797bd1e9a7477e30460f2ed4064c
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57748989"
---
# <a name="ltremarksgt-visual-c"></a>&lt;Açıklamalar&gt; (Visual C++)

\<Remarks > etiketi, bir tür hakkında bilgi eklemek için kullanılır, ek bilgiler ile belirtilen [ \<Özet >](../ide/summary-visual-cpp.md). Bu bilgileri görüntülenen [Nesne Tarayıcısı](/visualstudio/ide/viewing-the-structure-of-code) ve kod açıklaması Web raporu.

## <a name="syntax"></a>Sözdizimi

```
<remarks>description</remarks>
```

#### <a name="parameters"></a>Parametreler

*Açıklaması*<br/>
Üye açıklaması.

## <a name="remarks"></a>Açıklamalar

Derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.

## <a name="example"></a>Örnek

```
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

[XML Belgeleri](../ide/xml-documentation-visual-cpp.md)
