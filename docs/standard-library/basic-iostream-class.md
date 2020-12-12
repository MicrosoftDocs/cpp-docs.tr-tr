---
description: 'Hakkında daha fazla bilgi edinin: basic_iostream sınıfı'
title: basic_iostream Sınıfı
ms.date: 11/04/2016
f1_keywords:
- istream/std::basic_iostream
- istream/std::basic_iostream::swap
helpviewer_keywords:
- basic_iostream class
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
ms.openlocfilehash: c9b605c5eb36a0bc725ce21e2c89617357078d40
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321520"
---
# <a name="basic_iostream-class"></a>basic_iostream Sınıfı

Hem giriş hem de çıkış yapan bir akış sınıfı.

## <a name="syntax"></a>Syntax

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

Sınıf şablonu, eklenen temel sınıf [basic_ostream](../standard-library/basic-ostream-class.md) <  `Elem` , `Tr`> ve Dışlamalar aracılığıyla eklemeleri denetleyen bir nesneyi [basic_istream](../standard-library/basic-istream-class.md) <  `Elem` `Tr`>. İki nesne,> [basic_ios](../standard-library/basic-ios-class.md)ortak bir sanal taban sınıfı paylaşır <  `Elem` `Tr` . Ayrıca, `Elem` karakter nitelikleri sınıfı tarafından belirlendiği şekilde, türündeki öğelerle ortak bir akış arabelleğini yönetir `Tr` . Oluşturucu, temel sınıflarını `basic_istream` ( **strarabelleğe**) ve `basic_ostream` ( **strarabelleğe**) ile başlatır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_iostream](#basic_iostream)|Bir `basic_iostream` nesne oluşturun.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Kur](#swap)|`basic_iostream`Bu nesnenin içeriği için belirtilen nesnenin içeriğini değiş tokuş eder.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_eq)|Belirtilen `basic_iostream` nesnenin değerini bu nesneye atar. Bu, `rvalue` arkasında bir kopya bırakmayan bir taşıma atamasıdır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<istream>

**Ad alanı:** std

## <a name="basic_iostreambasic_iostream"></a><a name="basic_iostream"></a> basic_iostream:: basic_iostream

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
`basic_iostream`Yeni bir oluşturmak için kullanılan varolan bir nesne `basic_iostream` .

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu temel nesneleri ve şeklinde başlatır `basic_istream(strbuf)` `basic_ostream(strbuf)` .

İkinci Oluşturucu çağırarak temel nesneleri başlatır `move(right)` .

## <a name="basic_iostreamoperator"></a><a name="op_eq"></a> basic_iostream:: operator =

Belirtilen `basic_iostream` nesnenin değerini bu nesneye atayın. Bu, arkasına kopya bırakmayan bir rvalue içeren bir taşıma atamasıdır.

```cpp
basic_iostream& operator=(basic_iostream&& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
`rvalue`Atanacak bir nesneye başvuru `basic_iostream` .

### <a name="remarks"></a>Açıklamalar

Üye işleci çağırır `swap(right)` .

## <a name="basic_iostreamswap"></a><a name="swap"></a> basic_iostream:: swap

`basic_iostream`Bu nesnenin içeriği için belirtilen nesnenin içeriğini değiş tokuş eder.

```cpp
void swap(basic_iostream& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
`basic_iostream`Takas edilecek nesne.

### <a name="remarks"></a>Açıklamalar

Üye işlevi çağırır `swap(right)` .

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
