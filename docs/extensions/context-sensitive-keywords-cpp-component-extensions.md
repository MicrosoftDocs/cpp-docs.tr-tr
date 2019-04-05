---
title: Bağlama duyarlı anahtar sözcükler (C + +/ CLI ve C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- internal_CPP
helpviewer_keywords:
- context-sensitive keywords
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
ms.openlocfilehash: ca289a7ebd4578d5c67bb5d3e403d2a9a2756520
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038674"
---
# <a name="context-sensitive-keywords--ccli-and-ccx"></a>Bağlama duyarlı anahtar sözcükler (C + +/ CLI ve C + +/ CX)

*Bağlama duyarlı anahtar sözcükler* yalnızca belirli bağlamlarda tanınan dil öğeleridir. Belirli bağlamı dışında bağlama duyarlı anahtar sözcük kullanıcı tanımlı bir sembol olabilir.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="remarks"></a>Açıklamalar

Bağlama duyarlı anahtar sözcüklerin listesi aşağıdadır:

- [abstract](abstract-cpp-component-extensions.md)

- [temsilci](delegate-cpp-component-extensions.md)

- [olay](event-cpp-component-extensions.md)

- [finally](../dotnet/finally.md)

- [for each, in](../dotnet/for-each-in.md)

- [initonly](../dotnet/initonly-cpp-cli.md)

- `internal`

- [değişmez değer](literal-cpp-component-extensions.md)

- [override](override-cpp-component-extensions.md)

- [özellik](property-cpp-component-extensions.md)

- [korumalı](sealed-cpp-component-extensions.md)

- `where` (parçası [genel türler](generics-cpp-component-extensions.md))

Okunabilirlik için içeriğe duyarlı anahtar sözcükler kullanıcı tanımlı simgeler olarak kullanımını sınırlamak isteyebilirsiniz.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

(Bu özelliğin platforma özel açıklaması yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

(Bu özelliğin platforma özel açıklaması yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği uygun içerikte gösteren **özelliği** bağlama duyarlı anahtar sözcüğü, bir özellik ve bir değişkeni tanımlamak için kullanılabilir.

```cpp
// context_sensitive_keywords.cpp
// compile with: /clr
public ref class C {
   int MyInt;
public:
   C() : MyInt(99) {}

   property int Property_Block {   // context-sensitive keyword
      int get() { return MyInt; }
   }
};

int main() {
   int property = 0;               // variable name
   C ^ MyC = gcnew C();
   property = MyC->Property_Block;
   System::Console::WriteLine(++property);
}
```

```Output
100
```

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)