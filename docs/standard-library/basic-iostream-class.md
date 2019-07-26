---
title: basic_iostream Sınıfı
ms.date: 11/04/2016
f1_keywords:
- istream/std::basic_iostream
- istream/std::basic_iostream::swap
helpviewer_keywords:
- basic_iostream class
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
ms.openlocfilehash: 052271e2e2cc929875489e27abde2147bc5c070a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460096"
---
# <a name="basiciostream-class"></a>basic_iostream Sınıfı

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

Şablon sınıfı, temel sınıfı [basic_ostream](../standard-library/basic-ostream-class.md)< `Elem`, `Tr`> ve Dışlamalar aracılığıyla eklemeleri denetleyen bir nesneyi temel sınıf [basic_istream](../standard-library/basic-istream-class.md) <  aracılığıylaaçıklar.`Elem` ,`Tr`>. İki nesne,< `Elem` [](../standard-library/basic-ios-class.md) >ortakbirsanaltemelsınıfıpaylaşır`Tr`basic_ios. Ayrıca, karakter nitelikleri sınıfı `Elem` `Tr`tarafından belirlendiği şekilde, türündeki öğelerle ortak bir akış arabelleğini yönetir. Oluşturucu, temel sınıflarını `basic_istream`( **strarabelleğe**) ve `basic_ostream`( **strarabelleğe**) ile başlatır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_iostream](#basic_iostream)|Bir `basic_iostream` nesne oluşturun.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Kur](#swap)|Bu nesnenin içeriği için belirtilen `basic_iostream` nesnenin içeriğini değiş tokuş eder.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Belirtilen `basic_iostream` nesnenin değerini bu nesneye atar. Bu, arkasında bir kopya bırakmayan `rvalue` bir taşıma atamasıdır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<IStream >

**Ad alanı:** std

## <a name="basic_iostream"></a>basic_iostream::basic_iostream

Bir `basic_iostream` nesne oluşturun.

```cpp
explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

basic_iostream(basic_iostream&& right);

basic_iostream();
```

### <a name="parameters"></a>Parametreler

*strarabelleğe*\
Varolan bir `basic_streambuf` nesnesi.

*Right*\
`basic_iostream` Yeni`basic_iostream`bir oluşturmak için kullanılan varolan bir nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu temel nesneleri `basic_istream(strbuf)` ve `basic_ostream(strbuf)`şeklinde başlatır.

İkinci Oluşturucu çağırarak `move(right)`temel nesneleri başlatır.

## <a name="op_eq"></a>basic_iostream:: operator =

Belirtilen `basic_iostream` nesnenin değerini bu nesneye atayın. Bu, arkasına kopya bırakmayan bir rvalue içeren bir taşıma atamasıdır.

```cpp
basic_iostream& operator=(basic_iostream&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Atanacak bir`basic_iostream` nesneye başvuru. `rvalue`

### <a name="remarks"></a>Açıklamalar

Üye işleci çağırır `swap(right)`.

## <a name="swap"></a>basic_iostream:: swap

Bu nesnenin içeriği için belirtilen `basic_iostream` nesnenin içeriğini değiş tokuş eder.

```cpp
void swap(basic_iostream& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Takas `basic_iostream` edilecek nesne.

### <a name="remarks"></a>Açıklamalar

Üye işlevi çağırır `swap(right)`.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
