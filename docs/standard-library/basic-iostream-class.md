---
title: basic_iostream Sınıfı
ms.date: 11/04/2016
f1_keywords:
- istream/std::basic_iostream
- istream/std::basic_iostream::swap
helpviewer_keywords:
- basic_iostream class
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
ms.openlocfilehash: 190c9aa23493cea67bae44be93fd3fdbdecc4447
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72690001"
---
# <a name="basic_iostream-class"></a>basic_iostream Sınıfı

Hem giriş hem de çıkış yapan bir akış sınıfı.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_iostream : public basic_istream<Elem, Tr>,
    public basic_ostream<Elem, Tr>
{
public:
    explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

    virtual ~basic_iostream();

};
```

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, eklemeleri, temel sınıfı [basic_ostream](../standard-library/basic-ostream-class.md) <  `Elem`, `Tr` > ve dışlamaları aracılığıyla, temel sınıfı [basic_istream](../standard-library/basic-istream-class.md) <  `Elem`, `Tr` > aracılığıyla denetleyen bir nesneyi tanımlar. İki nesne ortak bir sanal temel sınıf [basic_ios](../standard-library/basic-ios-class.md) <  `Elem`, `Tr` > paylaşır. Ayrıca, karakter nitelikleri `Tr` sınıfı tarafından belirlendiği şekilde, `Elem` türündeki öğelerle ortak bir akış arabelleğini yönetir. Oluşturucu temel sınıflarını `basic_istream` ( **strarabelleğe**) ve `basic_ostream` ( **strarabelleğe**) ile başlatır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_iostream](#basic_iostream)|@No__t_0 nesnesi oluşturun.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Kur](#swap)|Bu nesnenin içeriği için belirtilen `basic_iostream` nesnesinin içeriğini değiş tokuş eder.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_eq)|Belirtilen bir `basic_iostream` nesnesinin değerini bu nesneye atar. Bu, arkasında bir kopya bırakmayan bir `rvalue` içeren bir taşıma atamasıdır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<istream >

**Ad alanı:** std

## <a name="basic_iostream"></a>basic_iostream::basic_iostream

@No__t_0 nesnesi oluşturun.

```cpp
explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

basic_iostream(basic_iostream&& right);

basic_iostream();
```

### <a name="parameters"></a>Parametreler

*strarabelleğe* \
Varolan bir `basic_streambuf` nesnesi.

*sağ* \
Yeni bir `basic_iostream` oluşturmak için kullanılan mevcut bir `basic_iostream` nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu temel nesneleri `basic_istream(strbuf)` ve `basic_ostream(strbuf)` olarak başlatır.

İkinci Oluşturucu, `move(right)` çağırarak temel nesneleri başlatır.

## <a name="op_eq"></a>basic_iostream:: operator =

Belirtilen bir `basic_iostream` nesnesinin değerini bu nesneye atayın. Bu, arkasına kopya bırakmayan bir rvalue içeren bir taşıma atamasıdır.

```cpp
basic_iostream& operator=(basic_iostream&& right);
```

### <a name="parameters"></a>Parametreler

*sağ* \
' Den atanacak bir `basic_iostream` nesnesine bir `rvalue` başvurusu.

### <a name="remarks"></a>Açıklamalar

Üye işleci `swap(right)` çağırır.

## <a name="swap"></a>basic_iostream:: swap

Bu nesnenin içeriği için belirtilen `basic_iostream` nesnesinin içeriğini değiş tokuş eder.

```cpp
void swap(basic_iostream& right);
```

### <a name="parameters"></a>Parametreler

*sağ* \
Takas edilecek `basic_iostream` nesnesi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi `swap(right)` çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[Standart kitaplıkta Iş parçacığı güvenliği \ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[iostream programlama](../standard-library/iostream-programming.md) \
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
