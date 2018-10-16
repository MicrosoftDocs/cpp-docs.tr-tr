---
title: Öznitelik parametre türleri (C + +/ CLI ve C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- custom attributes, parameter types
ms.assetid: d9f127a3-7f08-456f-acc6-256805632712
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8db82e2b31984429165ce39a328abc28ba6e2cfd
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2018
ms.locfileid: "49328174"
---
# <a name="attribute-parameter-types--ccli-and-ccx"></a>Öznitelik parametre türleri (C + +/ CLI ve C + +/ CX)

Öznitelikler için geçirilen değer derleyiciye derleme zamanında bilinen gerekir.  Öznitelik parametreleri aşağıdaki türde olabilir:

- **bool**

- **char**, **işaretsiz karakter**

- **kısa**, **işaretsiz**

- **int**, **işaretsiz int**

- **uzun**, **işaretsiz uzun**

- **__int64**, **unsigned __int64**

- **float**, **çift**

- **wchar_t**

- `char*` veya `wchar_t*` veya `System::String*`

- `System::Type ^`

- `System::Object ^`

- **enum**

## <a name="example"></a>Örnek

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

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Öznitelikleri belirtirken, tüm adlandırılmamış (konumsal) bağımsız değişkenler adlandırılmış bağımsız değişkenler gelmelidir.

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

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Öznitelik parametreleri önceki türlerinin tek boyutlu diziler olabilir.

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

## <a name="see-also"></a>Ayrıca Bkz.

[Kullanıcı tanımlı öznitelikler](../windows/user-defined-attributes-cpp-component-extensions.md)