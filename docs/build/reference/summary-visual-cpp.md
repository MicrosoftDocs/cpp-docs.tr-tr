---
title: '&lt;Özet > (C++ belge açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C++ XML tag
- summary C++ XML tag
ms.assetid: cdeeefbb-1339-45d6-9002-10042a9a2726
ms.openlocfilehash: 0620273f24573539897809b7892d46ad49b7aa57
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988578"
---
# <a name="ltsummarygt"></a>&lt;Özet&gt;

\<Özet > etiketi, bir tür veya tür üyesini tanımlamakta kullanılmalıdır. Bir tür açıklamasına ek bilgi eklemek için [\<açıklamaları >](remarks-visual-cpp.md) kullanın.

## <a name="syntax"></a>Sözdizimi

```
<summary>description</summary>
```

#### <a name="parameters"></a>Parametreler

*description*<br/>
Nesnenin Özeti.

## <a name="remarks"></a>Açıklamalar

\<Summary > etiketinin metni, IntelliSense 'teki tür hakkındaki tek bilgi kaynağıdır ve ayrıca [nesne tarayıcısı](/visualstudio/ide/viewing-the-structure-of-code) ve kod yorumu Web raporunda de görüntülenir.

Belge açıklamalarını bir dosyaya işlemek için [/doc](doc-process-documentation-comments-c-cpp.md) ile derleyin.

## <a name="example"></a>Örnek

```cpp
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
