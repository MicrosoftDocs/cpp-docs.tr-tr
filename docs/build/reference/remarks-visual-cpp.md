---
description: 'Daha fazla bilgi edinin: &lt; açıklamalar&gt;'
title: '&lt;açıklamalar> (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- <remarks> C++ XML tag
- remarks C++ XML tag
ms.assetid: c820083b-3192-40ab-9ec8-1472c55b4247
ms.openlocfilehash: 0c919ba3101282fd755450489eacc6c0800fb437
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225225"
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
