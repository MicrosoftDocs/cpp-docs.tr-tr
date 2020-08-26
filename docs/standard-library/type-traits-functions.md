---
title: '&lt;type_traits &gt; işlevleri'
ms.date: 11/04/2016
ms.assetid: dce4492f-f3e4-4d5e-bdb4-5875321254ec
helpviewer_keywords:
- std::is_assignable
- std::is_copy_assignable
- std::is_copy_constructible
- std::is_default_constructible
- std::is_move_assignable
- std::is_move_constructible
- std::is_nothrow_move_assignable
- std::is_trivially_copy_assignable
- std::is_trivially_move_assignable
- std::is_trivially_move_constructible
ms.openlocfilehash: 11defadff0b1785f6e4c5aba6356f7b68a78b9fc
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841785"
---
# <a name="lttype_traitsgt-functions"></a>&lt;type_traits &gt; işlevleri

[is_assignable](#is_assignable)\
[is_copy_assignable](#is_copy_assignable)\
[is_copy_constructible](#is_copy_constructible)\
[is_default_constructible](#is_default_constructible)\
[is_move_assignable](#is_move_assignable)\
[is_move_constructible](#is_move_constructible)\
[is_nothrow_move_assignable](#is_nothrow_move_assignable)\
[is_nothrow_swappable](#is_nothrow_swappable)\
[is_nothrow_swappable_with](#is_nothrow_swappable_with)\
[is_swappable](#is_swappable)\
[is_swappable_with](#is_swappable_with)\
[is_trivially_copy_assignable](#is_trivially_copy_assignable)\
[is_trivially_move_assignable](#is_trivially_move_assignable)\
[is_trivially_move_constructible](#is_trivially_move_constructible)

## <a name="is_assignable"></a><a name="is_assignable"></a> is_assignable

Türden bir değerin bir *to* *türüne atanıp* atanamayacağını sınar.

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>Parametreler

*Hedef*\
Atamayı alan nesnenin türü.

*Kaynak*\
Değer sağlayan nesnenin türü.

### <a name="remarks"></a>Açıklamalar

Değerlendirilmeyecek ifade `declval<To>() = declval<From>()` düzgün biçimlendirilmiş olmalıdır. Hem *öğesinden* hem *de* ' nin, bilinmeyen bir tür, **`void`** veya dizileri olması gerekir.

## <a name="is_copy_assignable"></a><a name="is_copy_assignable"></a> is_copy_assignable

Tür, atamaya kopyalanıp kopyalanamayacağını sınar.

```cpp
template <class Ty>
struct is_copy_assignable;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

*Tür değeri* , kopya atama operatörü olan bir sınıfdaysa, tür koşulunun bir örneği true, aksi takdirde false değerini taşır. İs_assignable eşdeğerdir \<Ty&, const Ty&> .

## <a name="is_copy_constructible"></a><a name="is_copy_constructible"></a> is_copy_constructible

Türün bir kopya Oluşturucusu varsa sınar.

```cpp
template <class Ty>
struct is_copy_constructible;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

*Tür değeri* , kopya Oluşturucusu olan bir sınıfdaysa, tür koşulu true, aksi takdirde false barındırır.

### <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

struct Copyable
{
    int val;
};

struct NotCopyable
{
   NotCopyable(const NotCopyable&) = delete;
   int val;

};

int main()
{
    std::cout << "is_copy_constructible<Copyable> == " << std::boolalpha
        << std::is_copy_constructible<Copyable>::value << std::endl;
    std::cout << "is_copy_constructible<NotCopyable> == " << std::boolalpha
        << std::is_copy_constructible<NotCopyable>::value << std::endl;

    return (0);
}
```

```Output
is_copy_constructible<Copyable> == true
is_copy_constructible<NotCopyable > == false
```

## <a name="is_default_constructible"></a><a name="is_default_constructible"></a> is_default_constructible

Bir türün varsayılan Oluşturucusu olup olmadığını sınar.

```cpp
template <class Ty>
struct is_default_constructible;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

Tür *T* türü, varsayılan oluşturucuya sahip bir sınıf türü ise true, aksi takdirde false barındırır. Bu koşul ile eşdeğerdir `is_constructible<T>` . Tür *T* , bir **`void`** tamsayı veya bilinmeyen bir dize olmalıdır.

### <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iostream>

struct Simple
{
    Simple() : val(0) {}
    int val;
};

struct Simple2
{
    Simple2(int v) : val(v) {}
    int val;
};

int main()
{
    std::cout << "is_default_constructible<Simple> == " << std::boolalpha
        << std::is_default_constructible<Simple>::value << std::endl;
    std::cout << "is_default_constructible<Simple2> == " << std::boolalpha
        << std::is_default_constructible<Simple2>::value << std::endl;

    return (0);
}
```

```Output
is_default_constructible<Simple> == true
is_default_constructible<Simple2> == false
```

## <a name="is_move_assignable"></a><a name="is_move_assignable"></a> is_move_assignable

Tür atanmış olarak taşınabileceği test eder.

```cpp
template <class T>
struct is_move_assignable;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

Türe bir rvalue başvurusu, türe bir başvuruya atanabileceği takdirde tür atanabilir. Tür koşulu ile eşdeğerdir `is_assignable<T&, T&&>` . Atanabilir türleri, derleyici tarafından oluşturulan veya Kullanıcı tanımlı taşıma atama işleçleri olan başvurulabilir skaler türlerini ve sınıf türlerini içerir.

## <a name="is_move_constructible"></a><a name="is_move_constructible"></a> is_move_constructible

Türün bir taşıma oluşturucusuna sahip olup olmadığını sınar.

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Değerlendirilecek tür

### <a name="remarks"></a>Açıklamalar

Tür *T* bir taşıma işlemi kullanılarak oluşturulabiliyorsa true olarak değerlendirilen bir tür koşulu. Bu koşul ile eşdeğerdir `is_constructible<T, T&&>` .

## <a name="is_nothrow_move_assignable"></a><a name="is_nothrow_move_assignable"></a> is_nothrow_move_assignable

Türün bir **`nothrow`** taşıma ataması operatörüne sahip olup olmadığını sınar.

```cpp
template <class Ty>
struct is_nothrow_move_assignable;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

*Tür olarak* bir nothrow taşıma atama işleci varsa, tür koşulunda bir örnek true, aksi takdirde false barındırır.

## <a name="is_nothrow_swappable"></a><a name="is_nothrow_swappable"></a> is_nothrow_swappable

```cpp
template <class T> struct is_nothrow_swappable;
```

## <a name="is_nothrow_swappable_with"></a><a name="is_nothrow_swappable_with"></a> is_nothrow_swappable_with

```cpp
template <class T, class U> struct is_nothrow_swappable_with;
```

## <a name="is_swappable"></a><a name="is_swappable"></a> is_swappable

```cpp
template <class T> struct is_swappable;
```

## <a name="is_swappable_with"></a><a name="is_swappable_with"></a> is_swappable_with

```cpp
template <class T, class U> struct is_swappable_with;
```

## <a name="is_trivially_copy_assignable"></a><a name="is_trivially_copy_assignable"></a> is_trivially_copy_assignable

Türün bir Önemsiz kopya atama işlecine sahip olup olmadığını sınar.

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

Tür *T* , Önemsiz kopya atama operatörü olan bir sınıf ise true, aksi takdirde false barındırır.

Sınıf t için atama Oluşturucusu, örtük olarak sağlanmışsa, *t* sınıfı sanal bir işleve *sahip değildir,* *t* sınıfının sanal bir tabanı yoktur, sınıf türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz atama işleçlerine sahiptir ve sınıf dizisi türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz atama işleçleridir.

## <a name="is_trivially_move_assignable"></a><a name="is_trivially_move_assignable"></a> is_trivially_move_assignable

Türün bir önemsiz taşıma atama işlecine sahip olup olmadığını sınar.

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

*Tür değeri* , önemsiz taşıma atama operatörü olan bir sınıfdaysa, tür koşulu true, aksi takdirde false barındırır.

Sınıf *Ty* için bir taşıma atama işleci şu durumlarda önemsiz:

örtülü olarak sağlanır

sınıf *Ty* 'nin sanal işlevleri yok

sınıf *Ty* 'nin sanal tabanı yok

sınıf türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz taşıma atama işleçlerine sahiptir

Sınıf dizisi türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz taşıma atama işleçlerine sahiptir

## <a name="is_trivially_move_constructible"></a><a name="is_trivially_move_constructible"></a> is_trivially_move_constructible

Türün önemsiz taşıma Oluşturucusu varsa sınar.

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

*Tür değeri* , önemsiz bir taşıma oluşturucusuna sahip bir sınıfdaysa, tür belirtiminin bir örneği true, aksi takdirde false değerini taşır.

Sınıf *Ty* için bir taşıma Oluşturucusu şu durumlarda önemsiz:

örtülü olarak bildirilmiştir

parametre türleri örtük bildirimdekilerle eşdeğerdir

sınıf *Ty* 'nin sanal işlevleri yok

sınıf *Ty* 'nin sanal tabanı yok

sınıfta geçici bir statik olmayan veri üyesi yok

sınıf *Ty* 'nin tüm doğrudan temellerine önemsiz taşıma oluşturucuları sahiptir

sınıf türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz taşıma oluşturuculara sahiptir

Sınıf dizisi türündeki tüm statik olmayan veri üyelerinin sınıfları, önemsiz taşıma oluşturuculara sahiptir

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
