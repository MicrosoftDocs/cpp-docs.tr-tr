---
title: '&lt;type_traits&gt; fonksiyonlar'
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
ms.openlocfilehash: bc25c82629139c5bc2f6fa53d3555068374dca35
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367992"
---
# <a name="lttype_traitsgt-functions"></a>&lt;type_traits&gt; fonksiyonlar

||||
|-|-|-|
|[is_assignable](#is_assignable)|[is_copy_assignable](#is_copy_assignable)|[is_copy_constructible](#is_copy_constructible)|
|[is_default_constructible](#is_default_constructible)|[is_move_assignable](#is_move_assignable)|[is_move_constructible](#is_move_constructible)|
|[is_nothrow_move_assignable](#is_nothrow_move_assignable)|[is_nothrow_swappable](#is_nothrow_swappable)|[is_nothrow_swappable_with](#is_nothrow_swappable_with)|
|[is_swappable](#is_swappable)|[is_swappable_with](#is_swappable_with)|[is_trivially_copy_assignable](#is_trivially_copy_assignable)|
|[is_trivially_move_assignable](#is_trivially_move_assignable)|[is_trivially_move_constructible](#is_trivially_move_constructible)|

## <a name="is_assignable"></a><a name="is_assignable"></a>is_assignable

*From* türünden bir değerin *To* türüne atanıp atanamayacağını sınar.

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>Parametreler

*Hedef*\
Atamayı alan nesnenin türü.

*Kaynak*\
Değeri sağlayan nesnenin türü.

### <a name="remarks"></a>Açıklamalar

Değerlendirilmemiş ifade `declval<To>() = declval<From>()` iyi biçimlendirilmiş olmalıdır. *Hem From* hem *de To* tam türleri, **geçersiz**veya bilinmeyen bağlı diziler olmalıdır.

## <a name="is_copy_assignable"></a><a name="is_copy_assignable"></a>is_copy_assignable

Tür atamada kopyalanıp kopyalanamayacağını sınar.

```cpp
template <class Ty>
struct is_copy_assignable;
```

### <a name="parameters"></a>Parametreler

*Ty*\
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

Tip yükleminin bir *örneği, Ty* türü kopya atama işleci olan bir sınıfsa geçerlidir, aksi takdirde yanlış tutar. is_assignable\<Ty&'a eşdeğer, const Ty&>.

## <a name="is_copy_constructible"></a><a name="is_copy_constructible"></a>is_copy_constructible

Türbir kopya oluşturucu varsa sınar.

```cpp
template <class Ty>
struct is_copy_constructible;
```

### <a name="parameters"></a>Parametreler

*Ty*\
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

Tip yükleminin bir *örneği, Ty* türü kopya oluşturucusu olan bir sınıfsa geçerlidir, aksi takdirde yanlış tutar.

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

## <a name="is_default_constructible"></a><a name="is_default_constructible"></a>is_default_constructible

Bir tür varsayılan oluşturucu varsa sınar.

```cpp
template <class Ty>
struct is_default_constructible;
```

### <a name="parameters"></a>Parametreler

*T*\
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

*T* türü varsayılan bir oluşturucuolan bir sınıf türüyse, aksi takdirde yanlış tutar, tür yüklemi nin bir örneği geçerlidir. Bu yüklemin `is_constructible<T>`eşdeğeridir. *T* türü tam bir tür, **boşluk**veya bilinmeyen bir bağlı dizi olmalıdır.

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

## <a name="is_move_assignable"></a><a name="is_move_assignable"></a>is_move_assignable

Tür atanabilir sınama.

```cpp
template <class T>
struct is_move_assignable;
```

### <a name="parameters"></a>Parametreler

*T*\
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

Türe bir rvalue başvurusu türe bir başvuru atanabilirse, bir tür devredilebilir. Tür yüklemi ' nin `is_assignable<T&, T&&>`eşdeğeri. Devredilebilir taşıyın türleri, derleyici tarafından oluşturulan veya kullanıcı tanımlı taşıma atama işleçleri olan başvurulabilir skaler türleri ve sınıf türlerini içerir.

## <a name="is_move_constructible"></a><a name="is_move_constructible"></a>is_move_constructible

Türün bir hareket oluşturucusu olup olmadığını sınar.

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Parametreler

*T*\
Değerlendirilecek tür

### <a name="remarks"></a>Açıklamalar

*T* türü bir hareket işlemi kullanılarak oluşturulabilir sayılsa doğru olarak değerlendiren bir tür yüklemi. Bu yüklem ' `is_constructible<T, T&&>`e eşdeğerdir.

## <a name="is_nothrow_move_assignable"></a><a name="is_nothrow_move_assignable"></a>is_nothrow_move_assignable

Türün **nothrow** move atama işleci olup olmadığını sınar.

```cpp
template <class Ty>
struct is_nothrow_move_assignable;
```

### <a name="parameters"></a>Parametreler

*Ty*\
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

Tip yükleminin bir *örneği, Ty* türünde bir nothrow move atama işleci varsa, aksi takdirde yanlış tutar geçerlidir.

## <a name="is_nothrow_swappable"></a><a name="is_nothrow_swappable"></a>is_nothrow_swappable

```cpp
template <class T> struct is_nothrow_swappable;
```

## <a name="is_nothrow_swappable_with"></a><a name="is_nothrow_swappable_with"></a>is_nothrow_swappable_with

```cpp
template <class T, class U> struct is_nothrow_swappable_with;
```

## <a name="is_swappable"></a><a name="is_swappable"></a>is_swappable

```cpp
template <class T> struct is_swappable;
```

## <a name="is_swappable_with"></a><a name="is_swappable_with"></a>is_swappable_with

```cpp
template <class T, class U> struct is_swappable_with;
```

## <a name="is_trivially_copy_assignable"></a><a name="is_trivially_copy_assignable"></a>is_trivially_copy_assignable

Türün önemsiz bir kopya atama işleci olup olmadığını sınar.

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>Parametreler

*T*\
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

*T* türü önemsiz bir kopya atama işleci olan bir sınıfsa, aksi takdirde yanlış tutar türü yüklemi bir örnek doğru tutar.

*T* sınıfı için bir atama oluşturucu örtülü olarak sağlanıyorsa önemsizdir, *T* sınıfının sanal işlevleri yoktur, *T* sınıfının sanal temelleri yoktur, sınıf türündeki tüm statik olmayan veri üyelerinin sınıfları önemsiz atama işleçlerine sahiptir ve sınıf türü dizideki tüm statik olmayan veri üyelerinin sınıflarında önemsiz atama işleçleri vardır.

## <a name="is_trivially_move_assignable"></a><a name="is_trivially_move_assignable"></a>is_trivially_move_assignable

Türün önemsiz bir taşıma atama işleci olup olmadığını sınar.

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>Parametreler

*Ty*\
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

Tip yükleminin bir *örneği, Ty* türü önemsiz bir hareket atama işleci olan bir sınıfsa geçerlidir, aksi takdirde yanlış tutar.

Bir sınıf *Ty* için bir hareket atama işleci önemsiz ise:

bu örtülü olarak sağlanır

sınıf *Ty* hiçbir sanal işlevleri vardır

sınıf *Ty* hiçbir sanal üsleri vardır

sınıf türündeki tüm statik olmayan veri üyelerinin sınıfları önemsiz hareket atama işleçleri var

sınıf türü dizisinin tüm statik olmayan veri üyelerinin sınıfları önemsiz hareket atama işleçleri var

## <a name="is_trivially_move_constructible"></a><a name="is_trivially_move_constructible"></a>is_trivially_move_constructible

Türü önemsiz hareket oluşturucu varsa sınar.

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>Parametreler

*Ty*\
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

Tip yükleminin bir *örneği, Ty* türü önemsiz bir hareket oluşturucusu olan bir sınıfsa geçerlidir, aksi takdirde yanlış tutar.

Bir sınıf *Ty* için bir hareket oluşturucu önemsiz ise:

bu örtülü olarak ilan edilir

parametre türleri örtülü bir beyannameninkilere eşdeğerdir

sınıf *Ty* hiçbir sanal işlevleri vardır

sınıf *Ty* hiçbir sanal üsleri vardır

sınıfın geçici statik olmayan veri üyeleri yoktur

*Sınıf Ty* tüm doğrudan üsleri önemsiz hareket yapıcılar var

sınıf türündeki tüm statik olmayan veri üyelerinin sınıfları önemsiz hareket oluşturucuları var

sınıf türü dizisinin tüm statik olmayan veri üyelerinin sınıfları önemsiz hareket yapıcıları var

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
