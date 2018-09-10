---
title: basic_iostream sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- istream/std::basic_iostream
- istream/std::basic_iostream::swap
dev_langs:
- C++
helpviewer_keywords:
- basic_iostream class
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ef4b993ec628771666ac3773b575ee518c18173
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106444"
---
# <a name="basiciostream-class"></a>basic_iostream Sınıfı

Hem giriş ve çıkış yapabileceği bir akışı sınıfı.

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

Şablon sınıfı, temel sınıfı aracılığıyla eklemeler denetleyen bir nesneyi tanımlayan [basic_ostream](../standard-library/basic-ostream-class.md)< `Elem`, `Tr`> ve temel sınıfı aracılığıyla ayıklama [basic_ istream](../standard-library/basic-istream-class.md)< `Elem`, `Tr`>. İki nesnenin ortak bir sanal temel sınıf paylaşma [basic_ios](../standard-library/basic-ios-class.md)< `Elem`, `Tr`>. Ayrıca türünde öğelere sahip ortak bir akış arabelleğinin yönettikleri `Elem`, olan karakter nitelikleri sınıfı tarafından belirlenen `Tr`. Oluşturucusu aracılığıyla temel sınıflarını başlatır `basic_istream`( **strbuf**) ve `basic_ostream`( **strbuf**).

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_iostream](#basic_iostream)|Oluşturma bir `basic_iostream` nesne.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[değiştirme](#swap)|Sağlanan içeriğini birbiriyle değiştirir `basic_iostream` bu nesnenin içeriği için nesne.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Belirtilen bir değeri atar `basic_iostream` bu nesne için nesne. Bu, bir taşıma ataması ilgili bir `rvalue` , olmayan bir kopyasını gerisine bırakmak.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<istream >

**Namespace:** std

## <a name="basic_iostream"></a>  basic_iostream::basic_iostream

Oluşturma bir `basic_iostream` nesne.

```cpp
explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

basic_iostream(basic_iostream&& right);

basic_iostream();
```

### <a name="parameters"></a>Parametreler

*strbuf*<br/>
Varolan bir `basic_streambuf` nesnesi.

*sağ*<br/>
Mevcut bir `basic_iostream` yeni oluşturmak için kullanılan nesne `basic_iostream`.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu sunar temel nesnelere başlatır `basic_istream(strbuf)` ve `basic_ostream(strbuf)`.

İkinci oluşturucu çağırarak temel nesnelere başlatır `move(right)`.

## <a name="op_eq"></a>  basic_iostream::operator =

Belirli bir değer atamak `basic_iostream` bu nesne için nesne. Bir kopya bırakmaz arkasındaki bir rvalue içeren bir taşıma ataması budur.

```cpp
basic_iostream& operator=(basic_iostream&& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bir `rvalue` başvurusu bir `basic_iostream` nesnesine atayın.

### <a name="remarks"></a>Açıklamalar

Üye işleci çağrıları `swap(right)`.

## <a name="swap"></a>  basic_iostream::Swap

Sağlanan içeriğini birbiriyle değiştirir `basic_iostream` bu nesnenin içeriği için nesne.

```cpp
void swap(basic_iostream& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
`basic_iostream` Değiştirilecek nesne.

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrıları `swap(right)`.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
