---
description: 'Daha fazla bilgi için: messages sınıfı'
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
ms.openlocfilehash: fe8dcc9cd580f967a3d07a4744598dff72360d44
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230516"
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

*CharType*\
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
|[string_type](#string_type)|Türünde karakter içeren türde bir dizeyi tanımlayan tür `basic_string` `CharType` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[~eksik](#close)|İleti kataloğunu kapatır.|
|[do_close](#do_close)|İleti kataloğunu kapatmak için çağrılan sanal işlev.|
|[do_get](#do_get)|İleti kataloğunu almak için çağrılan sanal işlev.|
|[do_open](#do_open)|İleti kataloğunu açmak için çağrılan sanal işlev.|
|[get](#get)|İleti kataloğunu alır.|
|[açın](#open)|İleti kataloğunu açar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="messageschar_type"></a><a name="char_type"></a> Mesajlar:: char_type

İletileri görüntülemek için kullanılan bir karakter türü.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, **CharType** şablon parametresi için bir eş anlamlı.

## <a name="messagesclose"></a><a name="close"></a> Messages:: Close

İleti kataloğunu kapatır.

```cpp
void close(catalog _Catval) const;
```

### <a name="parameters"></a>Parametreler

*_Catval*\
Kapatılacak katalog.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_close](#do_close)(_ *catval*) öğesini çağırır.

## <a name="messagesdo_close"></a><a name="do_close"></a> Mesajlar::d o_close

İleti kataloğunu kapatmak için çağrılan sanal işlev.

```cpp
virtual void do_close(catalog _Catval) const;
```

### <a name="parameters"></a>Parametreler

*_Catval*\
Kapatılacak katalog.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi, [do_open](#do_open)daha önceki bir çağrı tarafından açılmış olması gereken *_Catval* ileti kataloğunu kapatır.

*_Catval* , kapatılmış olmayan daha önce açılmış bir katalogdan alınmalıdır.

### <a name="example"></a>Örnek

Öğesini çağıran [Close](#close)için örneğe bakın `do_close` .

## <a name="messagesdo_get"></a><a name="do_get"></a> Mesajlar::d o_get

İleti kataloğunu almak için çağrılan sanal işlev.

```cpp
virtual string_type do_get(
    catalog _Catval,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```

### <a name="parameters"></a>Parametreler

*_Catval*\
Aranacak ileti kataloğunu belirten kimlik değeri.

*_Set*\
İlk tanımlanan bir ileti kataloğunda bir iletiyi bulmak için kullanılır.

*_Message*\
Bir ileti kataloğunda bir iletiyi bulmak için kullanılan ikinci.

*_Dfault*\
Hata durumunda döndürülecek dize.

### <a name="return-value"></a>Dönüş Değeri

Hata durumunda *_Dfault* bir kopyasını döndürür. Aksi halde, belirtilen ileti sırasının bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi *_Catval* ileti kataloğu 'ndan bir ileti sırası almaya çalışır. Bunu yapmak için *_Set*, *_Message* ve *_Dfault* kullanabilir.

### <a name="example"></a>Örnek

Çağıran [Get](#get)için örneğe bakın `do_get` .

## <a name="messagesdo_open"></a><a name="do_open"></a> Mesajlar::d o_open

İleti kataloğunu açmak için çağrılan sanal işlev.

```cpp
virtual catalog do_open(
    const string& _Catname,
    const locale& _Loc) const;
```

### <a name="parameters"></a>Parametreler

*_Catname*\
Aranacak kataloğun adı.

*_Loc*\
Katalogda aranan yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

Hata durumunda sıfırdan az bir değer karşılaştıran bir değer döndürür. Aksi takdirde, döndürülen değer sonraki bir [Get](#get)çağrısında ilk bağımsız değişken olarak kullanılabilir.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi, adı *_Catname* olan bir ileti kataloğunu açmaya çalışır. Bunu yaparken yerel ayar *_Loc* kullanabilir

Dönüş değeri, daha sonra [kapatılacak](#close)bir çağrının bağımsız değişkeni olarak kullanılmalıdır.

### <a name="example"></a>Örnek

Öğesini çağıran [Açık](#open)için örneğe bakın `do_open` .

## <a name="messagesget"></a><a name="get"></a> Mesajlar:: Get

İleti kataloğunu alır.

```cpp
string_type get(
    catalog _CatVal,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```

### <a name="parameters"></a>Parametreler

*_Catval*\
Aranacak ileti kataloğunu belirten kimlik değeri.

*_Set*\
İlk tanımlanan bir ileti kataloğunda bir iletiyi bulmak için kullanılır.

*_Message*\
Bir ileti kataloğunda bir iletiyi bulmak için kullanılan ikinci.

*_Dfault*\
Hata durumunda döndürülecek dize.

### <a name="return-value"></a>Dönüş Değeri

Hata durumunda *_Dfault* bir kopyasını döndürür. Aksi halde, belirtilen ileti sırasının bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_get](#do_get)döndürür ( `_Catval` ,, `_Set` , `_Message` `_Dfault` ).

## <a name="messagesmessages"></a><a name="messages"></a> Mesajlar:: iletiler

İleti modeli oluşturucu işlevi.

```cpp
explicit messages(
    size_t _Refs = 0);

protected: messages(
    const char* _Locname,
    size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_Refs*\
Nesnenin bellek yönetimi türünü belirtmek için kullanılan tamsayı değeri.

*_Locname*\
Yerel ayarın adı.

### <a name="remarks"></a>Açıklamalar

*_Refs* parametresi için olası değerler ve bunların önemi şunlardır:

- 0: nesnenin ömrü, kendisini içeren yerel ayarlara göre yönetilir.

- 1: nesnenin ömrü el ile yönetilmelidir.

- \> 1: Bu değerler tanımlı değil.

Yok edicisi korunduğu için doğrudan örnek mümkün değildir.

Oluşturucu kendi temel nesnesini **locale::**[model](../standard-library/locale-class.md#facet_class)() ile başlatır `_Refs` .

## <a name="messagesopen"></a><a name="open"></a> Messages:: Open

İleti kataloğunu açar.

```cpp
catalog open(
    const string& _Catname,
    const locale& _Loc) const;
```

### <a name="parameters"></a>Parametreler

*_Catname*\
Aranacak kataloğun adı.

*_Loc*\
Katalogda aranan yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

Hata durumunda sıfırdan az bir değer karşılaştıran bir değer döndürür. Aksi takdirde, döndürülen değer sonraki bir [Get](#get)çağrısında ilk bağımsız değişken olarak kullanılabilir.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_open](#do_open)( `_Catname` ,) döndürür `_Loc` .

## <a name="messagesstring_type"></a><a name="string_type"></a> Mesajlar:: string_type

Türünde karakter içeren türde bir dizeyi tanımlayan tür `basic_string` `CharType` .

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, nesne ileti sıralarının kopyalarını depolayabilen [basic_string](../standard-library/basic-string-class.md) sınıf şablonu özelleştirmesi tanımlar.

## <a name="see-also"></a>Ayrıca bkz.

[\<locale>](../standard-library/locale.md)\
[messages_base sınıfı](../standard-library/messages-base-class.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
