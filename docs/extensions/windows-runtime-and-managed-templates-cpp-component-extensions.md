---
title: Windows çalışma zamanı ve yönetilen şablonlar (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- templates, with CLR types
ms.assetid: cf59d16b-5514-448b-9a95-e0b4fcb616a6
ms.openlocfilehash: a8cc429763d042ba262d5543f4a2d85bbf8aa29a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62264893"
---
# <a name="windows-runtime-and-managed-templates-ccli-and-ccx"></a>Windows çalışma zamanı ve yönetilen şablonlar (C++/CLI ve C++/CX)

Şablonları, bir Windows çalışma zamanı veya ortak dil çalışma zamanı türü prototipin tanımlamanıza olanak sağlar ve ardından farklı bir şablon türü parametreleri kullanarak bu tür çeşidi örneği.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

Değer veya başvuru türleri şablonları oluşturabilirsiniz.  Değer veya başvuru türleri oluşturma hakkında daha fazla bilgi için bkz. [sınıfları ve yapıları](classes-and-structs-cpp-component-extensions.md).

Standart C++ sınıf şablonları hakkında daha fazla bilgi için bkz: [sınıf şablonlarının](../cpp/class-templates.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

(Bu dil özelliğinin yalnızca Windows çalışma zamanı için geçerli olan açıklaması yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

Aşağıdaki kod örneklerinde gösterilmektedir yönetilen türlerinden sınıf şablonları oluşturmak için bazı sınırlamalar vardır.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Yönetilen tür şablonu parametresi olan bir genel tipi örneklemeli mümkündür, ancak bir genel tür şablonu parametresi ile yönetilen bir şablon örneği oluşturulamıyor. Genel türler çalışma zamanında çözümlenir olmasıdır. Daha fazla bilgi için [genel türler ve temsilciler (C++/CLI)](generics-and-templates-visual-cpp.md).

```cpp
// managed_templates.cpp
// compile with: /clr /c

generic<class T>
ref class R;

template<class T>
ref class Z {
   // Instantiate a generic with a template parameter.
   R<T>^ r;    // OK
};

generic<class T>
ref class R {
   // Cannot instantiate a template with a generic parameter.
   Z<T>^ z;   // C3231
};
```

Bir genel tür veya işlev yönetilen bir şablonda iç içe olamaz.

```cpp
// managed_templates_2.cpp
// compile with: /clr /c

template<class T> public ref class R {
   generic<class T> ref class W {};   // C2959
};
```

C + ile başvurulan bir derlemede tanımlanan şablonları erişemiyor +/ CLI dili söz dizimi, ancak yansıma kullanabilirsiniz. Bir şablon örneği değil, meta verilerde yayıldığını değil. Bir şablon örneği varsa, yalnızca başvurulan üye işlevleri meta verilerde görüntülenir.

```cpp
// managed_templates_3.cpp
// compile with: /clr

// Will not appear in metadata.
template<class T> public ref class A {};

// Will appear in metadata as a specialized type.
template<class T> public ref class R {
public:
   // Test is referenced, will appear in metadata
   void Test() {}

   // Test2 is not referenced, will not appear in metadata
   void Test2() {}
};

// Will appear in metadata.
generic<class T> public ref class G { };

public ref class S { };

int main() {
   R<int>^ r = gcnew R<int>;
   r->Test();
}
```

Kısmi özelleştirme veya bir sınıf şablonunun açık özelleştirme bir sınıfın yönetilen değiştiricisi değiştirebilirsiniz.

```cpp
// managed_templates_4.cpp
// compile with: /clr /c

// class template
// ref class
template <class T>
ref class A {};

// partial template specialization
// value type
template <class T>
value class A <T *> {};

// partial template specialization
// interface
template <class T>
interface class A<T%> {};

// explicit template specialization
// native class
template <>
class A <int> {};
```

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)