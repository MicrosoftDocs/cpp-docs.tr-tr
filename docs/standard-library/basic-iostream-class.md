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
ms.openlocfilehash: de2f28feb775cd6e37116ea7c27691397d2dfce4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33844282"
---
# <a name="basiciostream-class"></a>basic_iostream Sınıfı

Hem giriş ve çıkış yapmak için bir akış sınıfı.

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

Şablon sınıfı devralınabilir. taban sınıf üzerinden eklenenler denetleyen bir nesneyi tanımlayan [basic_ostream](../standard-library/basic-ostream-class.md)< `Elem`, `Tr`> ve temel sınıfı aracılığıyla ayıklamaları [basic_ istream](../standard-library/basic-istream-class.md)< `Elem`, `Tr`>. İki nesne genel sanal temel sınıfı paylaşmak [basic_ios](../standard-library/basic-ios-class.md)< `Elem`, `Tr`>. Ayrıca türündeki öğeler ile ortak Akış Arabellek yönettikleri `Elem`, olan karakter nitelikler sınıfı tarafından belirlenir `Tr`. Oluşturucu, taban sınıflarından aracılığıyla başlatır `basic_istream`( **strbuf**) ve `basic_ostream`( **strbuf**).

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[basic_iostream](#basic_iostream)|Oluşturma bir `basic_iostream` nesnesi.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Değiştirme](#swap)|Sağlanan içeriğini alış verişleri `basic_iostream` bu nesnenin içeriği için nesne.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Belirtilen bir değeri atar `basic_iostream` bu nesnesini. Bu taşıma atama ilgili olan bir `rvalue` , değil ardınızda bir kopyası.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<IStream >

**Namespace:** std

## <a name="basic_iostream"></a>  basic_iostream::basic_iostream

Oluşturma bir `basic_iostream` nesnesi.

```cpp
explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

basic_iostream(basic_iostream&& right);

basic_iostream();
```

### <a name="parameters"></a>Parametreler

`strbuf` Varolan bir `basic_streambuf` nesnesi.

`right` Var olan `basic_iostream` yeni oluşturmak için kullanılan nesne `basic_iostream`.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu temel nesnelerin tarafından yolu başlatır `basic_istream(strbuf)` ve `basic_ostream(strbuf)`.

İkinci oluşturucu çağırarak temel nesnelere başlatır `move(right)`.

## <a name="op_eq"></a>  basic_iostream::operator =

Belirtilen bir değeri atamak `basic_iostream` bu nesnesini. Bir kopyasını bırakmaz arkasındaki bir rvalue içeren bir taşıma atama budur.

```cpp
basic_iostream& operator=(basic_iostream&& right);
```

### <a name="parameters"></a>Parametreler

`right` Bir `rvalue` başvuru bir `basic_iostream` nesne atayın.

### <a name="remarks"></a>Açıklamalar

Üye işleci çağrıları `swap(right)`.

## <a name="swap"></a>  basic_iostream::Swap

Sağlanan içeriğini alış verişleri `basic_iostream` bu nesnenin içeriği için nesne.

```cpp
void swap(basic_iostream& right);
```

### <a name="parameters"></a>Parametreler

`right` `basic_iostream` Değiştirilecek nesne.

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrılarını `swap(right)`.

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
