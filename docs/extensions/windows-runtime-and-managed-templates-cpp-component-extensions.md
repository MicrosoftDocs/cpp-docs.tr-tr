---
description: 'Hakkında daha fazla bilgi edinin: Windows Çalışma Zamanı ve yönetilen şablonlar (C++/CLı ve C++/CX)'
title: Windows Çalışma Zamanı ve Yönetilen Şablonlar (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- templates, with CLR types
ms.assetid: cf59d16b-5514-448b-9a95-e0b4fcb616a6
ms.openlocfilehash: 75b39c58bc42c23da313525f125dc98abdb0866b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274040"
---
# <a name="windows-runtime-and-managed-templates-ccli-and-ccx"></a>Windows Çalışma Zamanı ve Yönetilen Şablonlar (C++/CLI ve C++/CX)

Şablonlar, Windows Çalışma Zamanı veya ortak dil çalışma zamanı türünün bir prototipini tanımlamanızı ve sonra farklı şablon türü parametrelerini kullanarak bu türün çeşitlemelerini örneklemeyi sağlar.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

Değer veya başvuru türlerinden şablonlar oluşturabilirsiniz.  Değer veya başvuru türleri oluşturma hakkında daha fazla bilgi için bkz. [sınıflar ve yapılar](classes-and-structs-cpp-component-extensions.md).

Standart C++ sınıf şablonları hakkında daha fazla bilgi için bkz. [sınıf şablonları](../cpp/class-templates.md).

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

(Bu dil özelliği için yalnızca Windows Çalışma Zamanı uygulanan bir açıklama yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

Aşağıdaki kod örneklerinde gösterilen yönetilen türlerden sınıf şablonları oluşturmaya yönelik bazı sınırlamalar vardır.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Yönetilen tür şablonu parametresiyle genel bir tür oluşturmak mümkündür, ancak bir genel tür şablonu parametresiyle yönetilen bir şablon örneği oluşturamazsınız. Bunun nedeni genel türlerin çalışma zamanında çözümlenme türüdür. Daha fazla bilgi için bkz. [Genel türler ve şablonlar (C++/CLI)](generics-and-templates-visual-cpp.md).

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

Genel tür veya işlev, yönetilen bir şablonda iç içe geçirilemez.

```cpp
// managed_templates_2.cpp
// compile with: /clr /c

template<class T> public ref class R {
   generic<class T> ref class W {};   // C2959
};
```

Başvurulmuş bir derlemede tanımlanan şablonlara C++/CLı dil söz dizimi ile erişemezsiniz, ancak yansıma kullanabilirsiniz. Şablon örneği yoksa meta verilerde yer verilmez. Şablon örneği oluşturulduğunda, yalnızca başvurulan üye işlevleri meta verilerde görüntülenir.

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

Bir sınıfın yönetilen değiştiricisini, bir sınıf şablonunun kısmi özelleşmesi veya açık özelleştirmesi içinde değiştirebilirsiniz.

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

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)
