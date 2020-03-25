---
title: Bağlama duyarlı anahtar sözcükler (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- internal_CPP
helpviewer_keywords:
- context-sensitive keywords
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
ms.openlocfilehash: 53fcaf13eb56ae14841861bffd1a29376304b8d6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182181"
---
# <a name="context-sensitive-keywords--ccli-and-ccx"></a>Bağlama duyarlı anahtar sözcükler (C++/CLI ve C++/CX)

*Bağlama duyarlı anahtar sözcükler* yalnızca belirli bağlamlarda tanınan dil öğeleridir. Belirli bağlam dışında, bağlama duyarlı bir anahtar sözcük Kullanıcı tanımlı bir sembol olabilir.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

### <a name="remarks"></a>Açıklamalar

Aşağıda, bağlama duyarlı anahtar sözcüklerin bir listesi verilmiştir:

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

- `where` ( [genel](generics-cpp-component-extensions.md)türlerin parçası)

Okunabilirlik amacıyla, bağlama duyarlı anahtar sözcüklerinizi Kullanıcı tanımlı semboller olarak sınırlamak isteyebilirsiniz.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

(Bu özellik için platforma özgü bir açıklama yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="remarks"></a>Açıklamalar

(Bu özellik için platforma özgü bir açıklama yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği, uygun bağlamda **özellik** bağlamı duyarlı anahtar sözcüğünün bir özelliği ve değişkeni tanımlamak için kullanılabileceğini gösterir.

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

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)
