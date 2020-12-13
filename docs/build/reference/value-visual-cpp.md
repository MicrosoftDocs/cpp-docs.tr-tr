---
description: 'Hakkında daha fazla bilgi edinin: &lt; değer&gt;'
title: '&lt;değer> (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- value
- <value>
helpviewer_keywords:
- value C++ XML tag
- <value> C++ XML tag
ms.assetid: 0ba0a0d5-bcd7-4862-a169-83f2721ad80e
ms.openlocfilehash: 110091607af7c973591384d44816f372f0d15b14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187038"
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
