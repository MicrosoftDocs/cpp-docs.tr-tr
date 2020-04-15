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
ms.openlocfilehash: deb9eaedba3c99bb2fcb8399ac412ccedb11545f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375919"
---
# <a name="messages-class"></a>messages Sınıfı

Sınıf şablonu, belirli bir yerel alan için uluslararası iletiler kataloğundan yerelleştirilmiş iletileri almak için yerel bir yönü olarak hizmet verebilecek bir nesneyi açıklar.

Şu anda, ileti sınıfı uygulanırken bir ileti yok.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType>
class messages : public messages_base;
```

### <a name="parameters"></a>Parametreler

*Chartype*\
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için ilk **girişim, kimlikte** benzersiz bir pozitif değer depolar.

Bu model, temelde, messages_base temel sınıfında tanımlanan iletilerin kataloğunu açar, gerekli bilgileri alır ve kataloğu kapatır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[sayısı](#messages)|İleti modeli oluşturucu işlevi.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Char_type](#char_type)|İletileri görüntülemek için kullanılan bir karakter türü.|
|[string_type](#string_type)|Tür karakterleri içeren bir `basic_string` tür dizesini `CharType`açıklayan bir tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Yakın](#close)|İleti kataloğunu kapatır.|
|[do_close](#do_close)|İleti kataloğunu kapatmak için çağrılan sanal işlev.|
|[do_get](#do_get)|İleti kataloğunu almak için çağrılan sanal işlev.|
|[do_open](#do_open)|İleti kataloğunu açmak için çağrılan sanal işlev.|
|[get](#get)|İleti kataloğunu alır.|
|[açık](#open)|İleti kataloğunu açar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yerel>

**Ad alanı:** std

## <a name="messageschar_type"></a><a name="char_type"></a>mesajlar::char_type

İletileri görüntülemek için kullanılan bir karakter türü.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi **CharType**ile eş anlamlıdır.

## <a name="messagesclose"></a><a name="close"></a>mesajlar::kapat

İleti kataloğunu kapatır.

```cpp
void close(catalog _Catval) const;
```

### <a name="parameters"></a>Parametreler

*_Catval*\
Katalog kapatılmalı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_close](#do_close)çağırır (_ *Catval).*

## <a name="messagesdo_close"></a><a name="do_close"></a>mesajlar::do_close

İleti kataloğunu kapatmak için çağrılan sanal işlev.

```cpp
virtual void do_close(catalog _Catval) const;
```

### <a name="parameters"></a>Parametreler

*_Catval*\
Katalog kapatılmalı.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi, [do_open](#do_open)için daha önceki bir çağrı yla açılmış olması gereken ileti *kataloğunu _Catval*kapatır.

*_Catval,* daha önce açılmış ve kapatılmamış bir katalogdan alınmalıdır.

### <a name="example"></a>Örnek

[Bkz. yakın](#close), hangi `do_close`çağırır .

## <a name="messagesdo_get"></a><a name="do_get"></a>mesajlar::do_get

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
Aranacak ileti kataloğunu belirten tanımlama değeri.

*_Set*\
İleti kataloğundaki bir iletiyi bulmak için kullanılan ilk tanım.

*_Message*\
Tanımlanan ikinci ileti kataloğunda bir ileti bulmak için kullanılır.

*_Dfault*\
Dize başarısızlık döndürülecek.

### <a name="return-value"></a>Dönüş Değeri

Bu hata *_Dfault* bir kopyasını döndürür. Aksi takdirde, belirtilen ileti dizisinin bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı üye *işlev, ileti*kataloğundan _Catval bir ileti sırası elde etmeye çalışır. Bunu yaparken *_Set,* *_Message*ve *_Dfault* yararlanabilir.

### <a name="example"></a>Örnek

[Get](#get)için örneğe bakın `do_get`, hangi çağrıları .

## <a name="messagesdo_open"></a><a name="do_open"></a>mesajlar::do_open

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
Katalogda aranan yerel alan.

### <a name="return-value"></a>Dönüş Değeri

Hatada sıfırdan daha az karşılaştıran bir değer döndürür. Aksi takdirde, döndürülen değer [almak](#get)için daha sonraki bir çağrıda ilk bağımsız değişken olarak kullanılabilir.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlev, adı *_Catname*bir ileti kataloğu açmaya çalışır. Bunu yaparken yerel *_Loc* yararlanabilir

İade değeri kapatmak [için](#close)daha sonraki bir çağrıda bağımsız değişken olarak kullanılmalıdır.

### <a name="example"></a>Örnek

[Çağıran açık](#open)için örneğe `do_open`bakın.

## <a name="messagesget"></a><a name="get"></a>mesajlar::get

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
Aranacak ileti kataloğunu belirten tanımlama değeri.

*_Set*\
İleti kataloğundaki bir iletiyi bulmak için kullanılan ilk tanım.

*_Message*\
Tanımlanan ikinci ileti kataloğunda bir ileti bulmak için kullanılır.

*_Dfault*\
Dize başarısızlık döndürülecek.

### <a name="return-value"></a>Dönüş Değeri

Bu hata *_Dfault* bir kopyasını döndürür. Aksi takdirde, belirtilen ileti dizisinin bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_get](#do_get) `_Catval`döndürür ( , , `_Set` `_Message`, . `_Dfault`

## <a name="messagesmessages"></a><a name="messages"></a>mesajlar::mesajlar

İleti modeli oluşturucu işlevi.

```cpp
explicit messages(
    size_t _Refs = 0);

protected: messages(
    const char* _Locname,
    size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_refs*\
Nesneiçin bellek yönetimi türünü belirtmek için kullanılan eden arameger değeri.

*_Locname*\
Yerel yerin adı.

### <a name="remarks"></a>Açıklamalar

*_Refs* parametresi için olası değerler ve önemi şunlardır:

- 0: Nesnenin ömrü, onu içeren yerel nesneler tarafından yönetilir.

- 1: Nesnenin ömrü el ile yönetilmelidir.

- \>1: Bu değerler tanımlı değildir.

Yıkıcı korunduğundan, doğrudan örnek yoktur.

Kurucu, temel nesnesini yerel olarak başlaşır:: **locale::**[fason](../standard-library/locale-class.md#facet_class)( ). `_Refs`

## <a name="messagesopen"></a><a name="open"></a>mesajlar::açık

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
Katalogda aranan yerel alan.

### <a name="return-value"></a>Dönüş Değeri

Hatada sıfırdan daha az karşılaştıran bir değer döndürür. Aksi takdirde, döndürülen değer [almak](#get)için daha sonraki bir çağrıda ilk bağımsız değişken olarak kullanılabilir.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_open](#do_open) `_Catname`döndürür ( , `_Loc`).

## <a name="messagesstring_type"></a><a name="string_type"></a>mesajlar::string_type

Tür karakterleri içeren bir `basic_string` tür dizesini `CharType`açıklayan bir tür.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, nesneleri ileti dizilerinin kopyalarını depolayabilen sınıf şablonu [basic_string](../standard-library/basic-string-class.md) uzmanlık açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel>](../standard-library/locale.md)\
[messages_base Sınıfı](../standard-library/messages-base-class.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
