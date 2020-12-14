---
description: 'Daha fazla bilgi edinin: &lt; Özet&gt;'
title: '&lt;Özet> (C++ belgeleri açıklamaları)'
ms.date: 11/04/2016
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C++ XML tag
- summary C++ XML tag
ms.assetid: cdeeefbb-1339-45d6-9002-10042a9a2726
ms.openlocfilehash: 73e36367ff1a36f2b030525ea22f634ae74b64a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230230"
---
# <a name="ltsummarygt"></a>&lt;özetleme&gt;

\<summary>Etiket bir tür veya tür üyesini tanımlamakta kullanılmalıdır. [\<remarks>](remarks-visual-cpp.md)Bir tür açıklamasına ek bilgi eklemek için kullanın.

## <a name="syntax"></a>Sözdizimi

```
<summary>description</summary>
```

#### <a name="parameters"></a>Parametreler

*açıklaması*<br/>
Nesnenin Özeti.

## <a name="remarks"></a>Açıklamalar

Etiketi için olan metin, \<summary> IntelliSense 'deki türle ilgili tek bilgi kaynağıdır ve ayrıca [nesne tarayıcısı](/visualstudio/ide/viewing-the-structure-of-code) ve kod yorumu Web raporunda de görüntülenir.

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
