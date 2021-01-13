---
description: 'Hakkında daha fazla bilgi edinin: &lt; değer&gt;'
title: '&lt;değer> (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- <value>
helpviewer_keywords:
- value C++ XML tag
- <value> C++ XML tag
ms.assetid: 0ba0a0d5-bcd7-4862-a169-83f2721ad80e
ms.openlocfilehash: 5ebab554a33ff0d90b9306f3aec56b2552e18c5a
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126331"
---
# <a name="ltvaluegt"></a>&lt;value&gt;

\<value>Etiketi, özellik ve özellik erişimci yöntemlerini açıklamanıza olanak sağlar. Visual Studio tümleşik geliştirme ortamında kod sihirbazıyla bir özellik eklediğinizde, [\<summary>](summary-visual-cpp.md) yeni özellik için bir etiket ekleneceğini unutmayın. Ardından \<value> , özelliğin temsil ettiği değeri tanımlayacak şekilde el ile bir etiket eklemeniz gerekir.

## <a name="syntax"></a>Sözdizimi

```
<value>property-description</value>
```

#### <a name="parameters"></a>Parametreler

*Özellik-Açıklama*<br/>
Özelliği için bir açıklama.

## <a name="remarks"></a>Açıklamalar

Belge açıklamalarını bir dosyaya işlemek için [/doc](doc-process-documentation-comments-c-cpp.md) ile derleyin.

## <a name="example"></a>Örnek

```cpp
// xml_value_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_value_tag.dll
using namespace System;
/// Text for class Employee.
public ref class Employee {
private:
   String ^ name;
   /// <value>Name accesses the value of the name data member</value>
public:
   property String ^ Name {
      String ^ get() {
         return name;
      }
      void set(String ^ i) {
         name = i;
      }
   }
};
```

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](xml-documentation-visual-cpp.md)
