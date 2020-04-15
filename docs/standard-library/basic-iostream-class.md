---
title: basic_iostream Sınıfı
ms.date: 11/04/2016
f1_keywords:
- istream/std::basic_iostream
- istream/std::basic_iostream::swap
helpviewer_keywords:
- basic_iostream class
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
ms.openlocfilehash: e2a892525afbbad6d5b42d0b836fee096a70c297
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376812"
---
# <a name="basic_iostream-class"></a>basic_iostream Sınıfı

Hem giriş hem de çıktı yapabilen bir akış sınıfı.

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

Sınıf şablonu, temel [sınıf](../standard-library/basic-ostream-class.md)< `Elem` `Tr` [basic_ostream,](../standard-library/basic-istream-class.md)< `Elem`> ve çıkarmalar aracılığıyla, temel sınıf basic_istream , `Tr`> aracılığıyla eklemeleri denetleyen bir nesneyi açıklar. İki nesne ortak bir sanal [basic_ios](../standard-library/basic-ios-class.md)< `Elem`taban `Tr` sınıf basic_ios ,> paylaşır. Ayrıca, karakter özellikleri sınıf `Elem` `Tr`tarafından belirlenen tür öğeleri ile ortak bir akış arabelleği yönetmek. Kurucu temel sınıflarını **(strbuf)** ve `basic_ostream`( **strbuf)** aracılığıyla `basic_istream`başlatifleştirir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Basic_iostream](#basic_iostream)|Bir `basic_iostream` nesne oluşturun.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Takas](#swap)|Bu nesnenin içeriği `basic_iostream` için sağlanan nesnenin içeriğini değiştirir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç=](#op_eq)|Bu nesneye belirtilen `basic_iostream` bir nesnenin değerini atar. Bu, bir kopyasını `rvalue` geride bırakmayan bir taşıma atamasıdır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<istream>

**Ad alanı:** std

## <a name="basic_iostreambasic_iostream"></a><a name="basic_iostream"></a>basic_iostream:basic_iostream

Bir `basic_iostream` nesne oluşturun.

```cpp
explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

basic_iostream(basic_iostream&& right);

basic_iostream();
```

### <a name="parameters"></a>Parametreler

*strbuf*\
Varolan bir `basic_streambuf` nesnesi.

*Doğru*\
Yeni `basic_iostream` `basic_iostream` bir nesne oluşturmak için kullanılan varolan bir nesne.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, temel nesneleri ve `basic_istream(strbuf)` . `basic_ostream(strbuf)`

İkinci oluşturucu çağırarak `move(right)`temel nesneleri başharf.

## <a name="basic_iostreamoperator"></a><a name="op_eq"></a>basic_iostream::operator=

Bu nesneye belirtilen `basic_iostream` nesnenin değerini atayın. Bu, bir kopyasını geride bırakmayan bir rvalue içeren bir taşıma atamasIdır.

```cpp
basic_iostream& operator=(basic_iostream&& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Atamak `basic_iostream` için bir nesneye `rvalue` başvuru.

### <a name="remarks"></a>Açıklamalar

Üye operatör `swap(right)`çağırır.

## <a name="basic_iostreamswap"></a><a name="swap"></a>basic_iostream::takas

Bu nesnenin içeriği `basic_iostream` için sağlanan nesnenin içeriğini değiştirir.

```cpp
void swap(basic_iostream& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Takas `basic_iostream` etmek için nesne.

### <a name="remarks"></a>Açıklamalar

Üye işlev `swap(right)`çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream Programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
