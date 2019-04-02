---
title: Bağlama duyarlı anahtar sözcükler (C + +/ CLI ve C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- internal_CPP
helpviewer_keywords:
- context-sensitive keywords
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
ms.openlocfilehash: 488a047a51547eff09b519afc453138b2e386e73
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787579"
---
# <a name="context-sensitive-keywords--ccli-and-ccx"></a>Bağlama duyarlı anahtar sözcükler (C + +/ CLI ve C + +/ CX)

*Bağlama duyarlı anahtar sözcükler* yalnızca belirli bağlamlarda tanınan dil öğeleridir. Belirli bağlamı dışında bağlama duyarlı anahtar sözcük kullanıcı tanımlı bir sembol olabilir.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="remarks"></a>Açıklamalar

Bağlama duyarlı anahtar sözcüklerin listesi aşağıdadır:

- [abstract](abstract-cpp-component-extensions.md)

- [delegate](delegate-cpp-component-extensions.md)

- [event](event-cpp-component-extensions.md)

- [finally](../dotnet/finally.md)

- [for each, in](../dotnet/for-each-in.md)

- [initonly](../dotnet/initonly-cpp-cli.md)

- `internal`

- [değişmez değer](literal-cpp-component-extensions.md)

- [override](override-cpp-component-extensions.md)

- [property](property-cpp-component-extensions.md)

- [sealed](sealed-cpp-component-extensions.md)

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

## <a name="see-also"></a>Ayrıca Bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)