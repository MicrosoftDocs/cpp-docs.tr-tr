---
title: Üye İşlev Şablonları
ms.date: 11/04/2016
helpviewer_keywords:
- function templates, member functions
ms.assetid: 83d51835-6a27-40ed-997c-7d90dc9182d8
ms.openlocfilehash: 8514c8ffe630f5bc44d8d287d6ccf08c7755e3a0
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008558"
---
# <a name="member-function-templates"></a>Üye İşlev Şablonları

Terim üye şablonu hem üye işlevi şablonlarına hem de iç içe geçmiş sınıf şablonlarına başvurur. Üye işlevi şablonları, bir sınıfı veya sınıf şablonunun üyeleri olan şablon işlevleridir.

Üye işlevleri çeşitli bağlamlarda işlev şablonları olabilir. Sınıf şablonlarının tüm işlevleri geneldir ancak bunlara üye şablonları veya üye işlevi şablonları olarak başvurulmaz. Bu üye işlevleri kendi şablon bağımsız değişkenlerini alırsa, üye işlev şablonları olarak kabul edilir.

## <a name="example-declare-member-function-templates"></a>Örnek: üye işlev şablonlarını bildirin

Şablon dışı veya şablon sınıflarındaki üye işlev şablonları, kendi şablon parametreleriyle işlev şablonları olarak bildirilir.

```cpp
// member_function_templates.cpp
struct X
{
   template <class T> void mf(T* t) {}
};

int main()
{
   int i;
   X* x = new X();
   x->mf(&i);
}
```

## <a name="example-member-function-template-of-template-class"></a>Örnek: şablon sınıfının üye işlev şablonu

Aşağıdaki örnekte bir şablon sınıfının üye işlevi şablonu gösterilmektedir.

```cpp
// member_function_templates2.cpp
template<typename T>
class X
{
public:
   template<typename U>
   void mf(const U &u)
   {
   }
};

int main()
{
}
```

## <a name="example-define-member-templates-outside-class"></a>Örnek: sınıf dışındaki üye şablonlarını tanımlama

```cpp
// defining_member_templates_outside_class.cpp
template<typename T>
class X
{
public:
   template<typename U>
   void mf(const U &u);
};

template<typename T> template <typename U>
void X<T>::mf(const U &u)
{
}

int main()
{
}
```

## <a name="example-templated-user-defined-conversion"></a>Örnek: şablonlu kullanıcı tanımlı dönüştürme

Yerel sınıfların üye şablonlarına sahip olmasına izin verilmez.

Üye şablonu işlevleri sanal işlevler olamaz ve bir temel sınıf sanal işlevi olarak aynı adla bildirildiklerinde bir temel sınıftan olan sanal işlevleri geçersiz kılamaz.

Aşağıdaki örnekte, şablonlu kullanıcı tanımlı bir dönüştürme gösterilmektedir:

```cpp
// templated_user_defined_conversions.cpp
template <class T>
struct S
{
   template <class U> operator S<U>()
   {
      return S<U>();
   }
};

int main()
{
   S<int> s1;
   S<long> s2 = s1;  // Convert s1 using UDC and copy constructs S<long>.
}
```

## <a name="see-also"></a>Ayrıca bkz.

[İşlev şablonları](../cpp/function-templates.md)
