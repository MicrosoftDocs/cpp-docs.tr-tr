---
title: '&lt;type_traits&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_assignable
- type_traits/std::is_copy_assignable
- type_traits/std::is_copy_constructible
- type_traits/std::is_default_constructible
- type_traits/std::is_move_assignable
- type_traits/std::is_move_constructible
- type_traits/std::is_nothrow_move_assignable
- type_traits/std::is_trivially_copy_assignable
- type_traits/std::is_trivially_move_assignable
- type_traits/std::is_trivially_move_constructible
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
ms.openlocfilehash: 05e72f07117cd5317dd0b8ea3590be9e87ae7b6d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653637"
---
# <a name="lttypetraitsgt-functions"></a>&lt;type_traits&gt; işlevleri

||||
|-|-|-|
|[is_assignable](#is_assignable)|[is_copy_assignable](#is_copy_assignable)|[is_copy_constructible](#is_copy_constructible)|
|[is_default_constructible](#is_default_constructible)|[is_move_assignable](#is_move_assignable)|[is_move_constructible](#is_move_constructible)|
|[is_nothrow_move_assignable](#is_nothrow_move_assignable)|[is_trivially_copy_assignable](#is_trivially_copy_assignable)|[is_trivially_move_assignable](#is_trivially_move_assignable)|
|[is_trivially_move_constructible](#is_trivially_move_constructible)|

## <a name="is_assignable"></a>  is_assignable

Bir değeri olup olmadığını test *gelen* türüne atanabilen bir *için* türü.

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>Parametreler

*Hedef*<br/>
Atamayı alan nesnenin türü.

*Kaynak*<br/>
Değer sağlayan bir nesne türü.

### <a name="remarks"></a>Açıklamalar

Değerlendirilmemiş ifade `declval<To>() = declval<From>()` iyi biçimlendirilmiş olmalıdır. Her ikisi de *gelen* ve *için* tam türler olmalıdır **void**, veya bilinmeyen bağlı bir dizi.

## <a name="is_copy_assignable"></a>  is_copy_assignable

Türüne sahip olup olmadığını test atamada kopyalanabilir.

```cpp
template <class Ty>
struct is_copy_assignable;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *Ty* tuttuğu yanlış bir kopya atama işleci, aksi takdirde sahip bir sınıftır. İs_assignable eşdeğer\<Ty &, const Ty & >.

## <a name="is_copy_constructible"></a>  is_copy_constructible

Kopya Oluşturucu türüne sahip olmadığını sınar.

```cpp
template <class Ty>
struct is_copy_constructible;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *Ty* tuttuğu yanlış bir kopya Oluşturucu, aksi takdirde sahip bir sınıftır.

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

## <a name="is_default_constructible"></a>  is_default_constructible

Bir türe varsayılan bir oluşturucuya sahip olmadığını sınar.

```cpp
template <class Ty>
struct is_default_constructible;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *T* false tuttuğu varsayılan bir oluşturucu, aksi durumda olan bir sınıf türüdür. Bu koşulu eşdeğerdir `is_constructible<T>`. Tür *T* tam bir tür olmalıdır **void**, veya bilinmeyen bağlı bir dizi.

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

## <a name="is_move_assignable"></a>  is_move_assignable

Atanan türü olabilir, testleri taşıyın.

```cpp
template <class T>
struct is_move_assignable;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

Bir türü taşıma atanabilir ise bir başvuru türü bir rvalue başvuru türüne atanabilir. Tür koşulu eşdeğerdir `is_assignable<T&, T&&>`. Atanabilir türleri başvurulabilir skaler türler ve taşıma atama işleçleri derleyici tarafından oluşturulan veya kullanıcı tanımlı olan sınıf türleri taşıyın.

## <a name="is_move_constructible"></a>  is_move_constructible

Türü bir taşıma oluşturucusuna sahip olup olmadığını test eder.

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Değerlendirilecek tür

### <a name="remarks"></a>Açıklamalar

Gerekirse true değerlendirir türü bir tür koşulu *T* taşıma işlemi kullanılarak oluşturulabilir. Bu koşulu eşdeğerdir `is_constructible<T, T&&>`.

## <a name="is_nothrow_move_assignable"></a>  is_nothrow_move_assignable

Türüne sahip olup olmadığını test bir **nothrow** atama işleçlerini taşıyın.

```cpp
template <class Ty>
struct is_nothrow_move_assignable;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *Ty* false tuttuğu nothrow taşıma atama işleci, aksi takdirde sahiptir.

## <a name="is_trivially_copy_assignable"></a>  is_trivially_copy_assignable

Türü, Önemsiz kopya atama işlecine sahip olup olmadığını test eder.

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *T* false tuttuğu Önemsiz kopya atama işlecine, aksi takdirde sahip bir sınıftır.

Bir sınıf için bir atama Oluşturucu *T* , sınıf, örtük olarak sağlanan Önemsiz olduğundan *T* sahip sanal işlev yok, sınıf *T* sahip hiçbir sanal tabanları olan sınıfları tüm statik olmayan veri üyeleri sınıf türünün basit atama işleçleri, ve önemsiz atama işleçleri dizi sınıf türünde tüm statik olmayan veri üyelerinin sınıflarını sahiptir.

## <a name="is_trivially_move_assignable"></a>  is_trivially_move_assignable

Önemsiz taşıma atama işleci türünde olup olmadığını sınar.

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *Ty* false tuttuğu Önemsiz taşıma atama işleci, aksi takdirde sahip bir sınıftır.

Bir sınıf için bir taşıma atama işlecini *Ty* gereksizse, varsa:

örtük olarak sağlanan

sınıf *Ty* sahip sanal işlev yok

sınıf *Ty* hiçbir sanal temellere sahip

tüm statik olmayan veri üyeleri sınıf türünün sınıflarını sahip Önemsiz taşıma atama işleçleri

Önemsiz taşıma atama işleçleri dizi sınıf türünde tüm statik olmayan veri üyelerinin sınıflarını sahip

## <a name="is_trivially_move_constructible"></a>  is_trivially_move_constructible

Taşıma Oluşturucu türü, Önemsiz varsa testleri.

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Sorgulanacak tür.

### <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *Ty* false tuttuğu Önemsiz taşıma oluşturucusu, aksi takdirde sahip bir sınıftır.

Bir sınıf için bir taşıma Oluşturucusu *Ty* gereksizse, varsa:

örtük olarak bildirilen

Bu örtük bir bildirimi eşdeğer parametre türleri

sınıf *Ty* sahip sanal işlev yok

sınıf *Ty* hiçbir sanal temellere sahip

Geçici statik olmayan veri üyeleri sınıf yoktur

tüm doğrudan tabanları sınıfının *Ty* Önemsiz taşıma oluşturucuları sahip

Önemsiz taşıma oluşturucuları sınıfları sınıf türünün tüm statik olmayan veri üyelerinin olması

Önemsiz taşıma oluşturucuları sınıflarını dizi sınıf türünde tüm statik olmayan veri üyelerine sahip

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
