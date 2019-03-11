---
title: '&lt;değer&gt; (Visual C++)'
ms.date: 11/04/2016
f1_keywords:
- value
- <value>
helpviewer_keywords:
- value C++ XML tag
- <value> C++ XML tag
ms.assetid: 0ba0a0d5-bcd7-4862-a169-83f2721ad80e
ms.openlocfilehash: 6add2d7fb6676d631a03d5f6e1764ebf221b4c52
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742504"
---
# <a name="ltvaluegt-visual-c"></a>&lt;değer&gt; (Visual C++)

\<Değer > etiketi, bir özellik ve özellik erişici yöntemlerini açıklamak olanak sağlar. Visual Studio tümleşik geliştirme ortamında bir kod Sihirbazı ile bir özellik eklediğinizde, bu ekleyeceğini unutmayın bir [ \<Özet >](../ide/summary-visual-cpp.md) yeni bir özellik için etiket. Daha sonra el ile eklemelisiniz bir \<değer > özelliği temsil eden bir değeri açıklamak için etiket.

## <a name="syntax"></a>Sözdizimi

```
<value>property-description</value>
```

#### <a name="parameters"></a>Parametreler

*özellik açıklaması*<br/>
Bir özellik için bir açıklama.

## <a name="remarks"></a>Açıklamalar

Derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.

## <a name="example"></a>Örnek

```
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

[XML Belgeleri](../ide/xml-documentation-visual-cpp.md)
