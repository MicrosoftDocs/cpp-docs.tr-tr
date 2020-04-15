---
title: Windows Çalışma Zamanı ve Yönetilen Şablonlar (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- templates, with CLR types
ms.assetid: cf59d16b-5514-448b-9a95-e0b4fcb616a6
ms.openlocfilehash: 5765370e611e5822b3b2d156d2eee5d21e5b453d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376313"
---
# <a name="windows-runtime-and-managed-templates-ccli-and-ccx"></a>Windows Çalışma Zamanı ve Yönetilen Şablonlar (C++/CLI ve C++/CX)

Şablonlar, Windows Runtime veya ortak dil çalışma zamanı türünün bir prototipini tanımlamanızı ve ardından farklı şablon türü parametreleri kullanarak bu türvaryasyonları anında oluşturmanıza olanak tanır.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

Değer veya başvuru türlerinden şablonlar oluşturabilirsiniz.  Değer veya başvuru türleri oluşturma hakkında daha fazla bilgi için [Sınıflar ve Structs'a](classes-and-structs-cpp-component-extensions.md)bakın.

Standart C++ sınıfı şablonları hakkında daha fazla bilgi için [Sınıf Şablonları'na](../cpp/class-templates.md)bakın.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

(Bu dil özelliği için yalnızca Windows Runtime için geçerli olan bir açıklama yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:`/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

Yönetilen türlerden sınıf şablonları oluşturmak için aşağıdaki kod örneklerinde gösterilen bazı sınırlamalar vardır.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:`/clr`

### <a name="examples"></a>Örnekler

Yönetilen bir tür şablon parametresi ile genel bir türü anında atabilmek mümkündür, ancak genel bir tür şablonu parametresi ile yönetilen bir şablonu anında oluşturamazsınız. Bunun nedeni, genel türlerin çalışma zamanında çözülmesidir. Daha fazla bilgi için genel bilgiler [ve Şablonlar (C++/CLI)](generics-and-templates-visual-cpp.md)bakın.

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

Genel bir tür veya işlev yönetilen bir şablonda iç içe geçemez.

```cpp
// managed_templates_2.cpp
// compile with: /clr /c

template<class T> public ref class R {
   generic<class T> ref class W {};   // C2959
};
```

C++/CLI dil sözdizimi ile başvurulan bir derlemede tanımlanan şablonlara erişemezsiniz, ancak yansımayı kullanabilirsiniz. Bir şablon anlık olarak kullanılmazsa, meta verilere yayınılmez. Bir şablon anında kullanılırsa, meta verilerde yalnızca başvurulan üye işlevler görüntülenir.

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

Bir sınıfın yönetilen değiştiricisini kısmi uzmanlık veya sınıf şablonunun açık uzmanlık alanı olarak değiştirebilirsiniz.

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
