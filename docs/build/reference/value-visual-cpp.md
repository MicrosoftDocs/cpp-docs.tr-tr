---
title: '&lt;değeri > (C++ belge açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- value
- <value>
helpviewer_keywords:
- value C++ XML tag
- <value> C++ XML tag
ms.assetid: 0ba0a0d5-bcd7-4862-a169-83f2721ad80e
ms.openlocfilehash: de84d1faca59a6c8e4f82fba3605cbd54a05bd2e
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988598"
---
# <a name="ltvaluegt"></a>&lt;value&gt;

\<Value > etiketi, bir özellik ve özellik erişimcisi yöntemlerini açıklamanıza olanak sağlar. Visual Studio tümleşik geliştirme ortamında kod sihirbazıyla bir özellik eklediğinizde, yeni özellik için bir [\<summary >](summary-visual-cpp.md) etiketi ekleneceğini unutmayın. Sonra özelliğin temsil ettiği değeri tanımlayan bir \<değer > etiketi eklemeniz gerekir.

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
