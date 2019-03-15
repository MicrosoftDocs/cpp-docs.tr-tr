---
title: '&lt;Özet > (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C++ XML tag
- summary C++ XML tag
ms.assetid: cdeeefbb-1339-45d6-9002-10042a9a2726
ms.openlocfilehash: 68bb8b7c269b3406438e5cf21dde7179f7e67646
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823543"
---
# <a name="ltsummarygt"></a>&lt;Özeti&gt;

\<Özet > etiketi, bir tür veya tür üye tanımlamak için kullanılmalıdır. Kullanım [ \<remarks >](remarks-visual-cpp.md) ek bilgiler bir tür tanımı eklemek için.

## <a name="syntax"></a>Sözdizimi

```
<summary>description</summary>
```

#### <a name="parameters"></a>Parametreler

*Açıklaması*<br/>
Nesne bir özeti.

## <a name="remarks"></a>Açıklamalar

Metni \<Özet > etiketi yalnızca kaynak ıntellisense'te tür hakkında bilgilerin ve bir de görüntülenir [Nesne Tarayıcısı](/visualstudio/ide/viewing-the-structure-of-code) ve kod açıklaması Web raporu.

Derleme [/doc](doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.

## <a name="example"></a>Örnek

```
// xml_summary_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_summary_tag.dll

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <summary>MyMethod is a method in the MyClass class.
   /// <para>Here's how you could make a second paragraph in a description. <see cref="System::Console::WriteLine"/> for information about output statements.</para>
   /// <seealso cref="MyClass::MyMethod2"/>
   /// </summary>
   void MyMethod(int Int1) {}

   /// text
   void MyMethod2() {}
};
```

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](xml-documentation-visual-cpp.md)
