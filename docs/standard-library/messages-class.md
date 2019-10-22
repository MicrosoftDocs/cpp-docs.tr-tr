---
title: messages Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmes/std::messages
- xlocmes/std::messages::char_type
- xlocmes/std::messages::string_type
- xlocmes/std::messages::close
- xlocmes/std::messages::do_close
- xlocmes/std::messages::do_get
- xlocmes/std::messages::do_open
- xlocmes/std::messages::get
- xlocmes/std::messages::open
helpviewer_keywords:
- std::messages [C++]
- std::messages [C++], char_type
- std::messages [C++], string_type
- std::messages [C++], close
- std::messages [C++], do_close
- std::messages [C++], do_get
- std::messages [C++], do_open
- std::messages [C++], get
- std::messages [C++], open
ms.assetid: c4c71f40-4f24-48ab-9f7c-daccd8d5bd83
ms.openlocfilehash: 704ee2ce40b4026cc066213181c96cf0f744d152
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687679"
---
# <a name="messages-class"></a>messages Sınıfı

Sınıf şablonu, belirli bir yerel ayar için uluslararası iletilerin bir kataloğundan yerelleştirilmiş iletiler almak için bir yerel ayar modeli olarak kullanılabilecek bir nesneyi tanımlar.

Şu anda, ileti sınıfı uygulanırken bir ileti yok.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType>
class messages : public messages_base;
```

### <a name="parameters"></a>Parametreler

*CharType* \
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim, kimlik içinde benzersiz bir pozitif değer depolar **.**

Bu model, temelde, messages_base temel sınıfında tanımlanan iletilerin kataloğunu açar, gerekli bilgileri alır ve kataloğu kapatır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[iletilerine](#messages)|İleti modeli oluşturucu işlevi.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|İletileri görüntülemek için kullanılan bir karakter türü.|
|[string_type](#string_type)|@No__t_1 türünde karakterler içeren `basic_string` türünde bir dizeyi tanımlayan tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[close](#close)|İleti kataloğunu kapatır.|
|[do_close](#do_close)|İleti kataloğunu kapatmak için çağrılan sanal işlev.|
|[do_get](#do_get)|İleti kataloğunu almak için çağrılan sanal işlev.|
|[do_open](#do_open)|İleti kataloğunu açmak için çağrılan sanal işlev.|
|[get](#get)|İleti kataloğunu alır.|
|[open](#open)|İleti kataloğunu açar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<locale >

**Ad alanı:** std

## <a name="char_type"></a>iletiler:: char_type

İletileri görüntülemek için kullanılan bir karakter türü.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, **CharType**şablon parametresi için bir eş anlamlı.

## <a name="close"></a>Messages:: Close

İleti kataloğunu kapatır.

```cpp
void close(catalog _Catval) const;
```

### <a name="parameters"></a>Parametreler

*_Catval* \
Kapatılacak katalog.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, [do_close](#do_close)(_ *catval*) öğesini çağırır.

## <a name="do_close"></a>Mesajlar::d o_close

İleti kataloğunu kapatmak için çağrılan sanal işlev.

```cpp
virtual void do_close(catalog _Catval) const;
```

### <a name="parameters"></a>Parametreler

*_Catval* \
Kapatılacak katalog.

### <a name="remarks"></a>Açıklamalar

Protected member işlevi, daha önceki bir [do_open](#do_open)çağrısıyla açılmış olması gereken Ileti kataloğu *_Catval*'i kapatır.

*_Catval* kapalı olmayan daha önce açılmış bir katalogdan alınmalıdır.

### <a name="example"></a>Örnek

@No__t_1 çağıran [kapatma](#close)örneğine bakın.

## <a name="do_get"></a>Mesajlar::d o_get

İleti kataloğunu almak için çağrılan sanal işlev.

```cpp
virtual string_type do_get(
    catalog _Catval,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```

### <a name="parameters"></a>Parametreler

*_Catval* \
Aranacak ileti kataloğunu belirten kimlik değeri.

*_@No__t_1 ayarla*
İlk tanımlanan bir ileti kataloğunda bir iletiyi bulmak için kullanılır.

*_Ileti* \
Bir ileti kataloğunda bir iletiyi bulmak için kullanılan ikinci.

*_Dfault* \
Hata durumunda döndürülecek dize.

### <a name="return-value"></a>Dönüş Değeri

Hata durumunda *_Dfault* 'in bir kopyasını döndürür. Aksi halde, belirtilen ileti sırasının bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Protected member işlevi, ileti kataloğu *_Catval*öğesinden bir ileti sırası edinmeye çalışır. Bunu yapmak için _, *_Message*ve *_Dfault* *' ı kullanabilir*.

### <a name="example"></a>Örnek

@No__t_1 çağıran [Get](#get)için örneğe bakın.

## <a name="do_open"></a>Mesajlar::d o_open

İleti kataloğunu açmak için çağrılan sanal işlev.

```cpp
virtual catalog do_open(
    const string& _Catname,
    const locale& _Loc) const;
```

### <a name="parameters"></a>Parametreler

*_Catname* \
Aranacak kataloğun adı.

*_Loc* \
Katalogda aranan yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

Hata durumunda sıfırdan az bir değer karşılaştıran bir değer döndürür. Aksi takdirde, döndürülen değer sonraki bir [Get](#get)çağrısında ilk bağımsız değişken olarak kullanılabilir.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi, adı *_Catname*olan bir ileti kataloğunu açmaya çalışır. Bunu yaparken yerel ayar *_Loc ' i* kullanabilir

Dönüş değeri, daha sonra [kapatılacak](#close)bir çağrının bağımsız değişkeni olarak kullanılmalıdır.

### <a name="example"></a>Örnek

@No__t_1 çağıran [Açık](#open)için örneğe bakın.

## <a name="get"></a>Mesajlar:: Get

İleti kataloğunu alır.

```cpp
string_type get(
    catalog _CatVal,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```

### <a name="parameters"></a>Parametreler

*_Catval* \
Aranacak ileti kataloğunu belirten kimlik değeri.

*_@No__t_1 ayarla*
İlk tanımlanan bir ileti kataloğunda bir iletiyi bulmak için kullanılır.

*_Ileti* \
Bir ileti kataloğunda bir iletiyi bulmak için kullanılan ikinci.

*_Dfault* \
Hata durumunda döndürülecek dize.

### <a name="return-value"></a>Dönüş Değeri

Hata durumunda *_Dfault* 'in bir kopyasını döndürür. Aksi halde, belirtilen ileti sırasının bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_get](#do_get)döndürür (`_Catval`, `_Set`, `_Message`, `_Dfault`).

## <a name="messages"></a>Mesajlar:: iletiler

İleti modeli oluşturucu işlevi.

```cpp
explicit messages(
    size_t _Refs = 0);

protected: messages(
    const char* _Locname,
    size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_Refs* \
Nesnenin bellek yönetimi türünü belirtmek için kullanılan tamsayı değeri.

*_Locname* \
Yerel ayarın adı.

### <a name="remarks"></a>Açıklamalar

*_Refs* parametresi için olası değerler ve bunların önemi şunlardır:

- 0: nesnenin ömrü, kendisini içeren yerel ayarlara göre yönetilir.

- 1: nesnenin ömrü el ile yönetilmelidir.

- \> 1: Bu değerler tanımlı değil.

Yok edicisi korunduğu için doğrudan örnek mümkün değildir.

Oluşturucu kendi temel nesnesini **locale::** [model](../standard-library/locale-class.md#facet_class)(`_Refs`) ile başlatır.

## <a name="open"></a>Messages:: Open

İleti kataloğunu açar.

```cpp
catalog open(
    const string& _Catname,
    const locale& _Loc) const;
```

### <a name="parameters"></a>Parametreler

*_Catname* \
Aranacak kataloğun adı.

*_Loc* \
Katalogda aranan yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

Hata durumunda sıfırdan az bir değer karşılaştıran bir değer döndürür. Aksi takdirde, döndürülen değer sonraki bir [Get](#get)çağrısında ilk bağımsız değişken olarak kullanılabilir.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_open](#do_open)döndürür (`_Catname`, `_Loc`).

## <a name="string_type"></a>iletiler:: string_type

@No__t_1 türünde karakterler içeren `basic_string` türünde bir dizeyi tanımlayan tür.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, nesneleri ileti sıralarının kopyalarını depolayabilen [basic_string](../standard-library/basic-string-class.md) sınıf şablonu özelleştirmesi tanımlar.

## <a name="see-also"></a>Ayrıca bkz.

[\<locale >](../standard-library/locale.md) \
[Messages_base sınıfı](../standard-library/messages-base-class.md) \
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
