---
description: 'Daha fazla bilgi edinin: öznitelik parametre türleri (C++/CLı ve C++/CX)'
title: Öznitelik Parametre Türleri (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- custom attributes, parameter types
ms.assetid: d9f127a3-7f08-456f-acc6-256805632712
ms.openlocfilehash: 7f2d5dd2def4e61d5b2b0406cc193bf818bc3d9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177100"
---
# <a name="attribute-parameter-types--ccli-and-ccx"></a>Öznitelik Parametre Türleri (C++/CLI ve C++/CX)

Özniteliklere geçirilen değerler derleme zamanında derleyici tarafından bilinmelidir.  Öznitelik parametreleri aşağıdaki türlerde olabilir:

- **`bool`**

- **`char`**, **`unsigned char`**

- **`short`**, **`unsigned short`**

- **`int`**, **`unsigned int`**

- **`long`**, **`unsigned long`**

- **`__int64`**, **imzasız __int64**

- **`float`**, **`double`**

- **`wchar_t`**

- **`char*`** or `wchar_t*` veya `System::String*`

- `System::Type ^`

- `System::Object ^`

- **`enum`**

## <a name="example-attribute-parameter-types"></a>Örnek: öznitelik parametre türleri

### <a name="code"></a>Kod

```cpp
// attribute_parameter_types.cpp
// compile with: /clr /c
using namespace System;
ref struct AStruct {};

[AttributeUsage(AttributeTargets::ReturnValue)]
ref struct Attr : public Attribute {
   Attr(AStruct ^ i){}
   Attr(bool i){}
   Attr(){}
};

ref struct MyStruct {
   static AStruct ^ x = gcnew AStruct;
   [returnvalue:Attr(x)] int Test() { return 0; }   // C3104
   [returnvalue:Attr] int Test2() { return 0; }   // OK
   [returnvalue:Attr(true)] int Test3() { return 0; }   // OK
};
```

## <a name="example-unnamed-arguments-precede-named-arguments"></a>Örnek: adlandırılmamış bağımsız değişkenler adlandırılmış bağımsız değişkenlerden önce gelmeli

### <a name="description"></a>Açıklama

Öznitelikleri belirtirken, adlandırılmamış (konumsal) bağımsız değişkenlerin tümü adlandırılmış bağımsız değişkenlerden önce gelmelidir.

### <a name="code"></a>Kod

```cpp
// extending_metadata_c.cpp
// compile with: /clr /c
using namespace System;
[AttributeUsage(AttributeTargets::Class)]
ref class MyAttr : public Attribute {
public:
   MyAttr() {}
   MyAttr(int i) {}
   property int Priority;
   property int Version;
};

[MyAttr]
ref class ClassA {};   // No arguments

[MyAttr(Priority = 1)]
ref class ClassB {};   // Named argument

[MyAttr(123)]
ref class ClassC {};   // Positional argument

[MyAttr(123, Version = 1)]
ref class ClassD {};   // Positional and named
```

## <a name="example-one-dimensional-array-attribute-parameter"></a>Örnek: tek boyutlu dizi öznitelik parametresi

### <a name="description"></a>Açıklama

Öznitelik parametreleri, önceki türlerin tek boyutlu dizileri olabilir.

### <a name="code"></a>Kod

```cpp
// extending_metadata_d.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::Class)]
public ref struct ABC : public Attribute {
   ABC(array<int>^){}
   array<double> ^ param;
};

[ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]
ref struct AStruct{};
```

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı tanımlı öznitelikler](user-defined-attributes-cpp-component-extensions.md)
