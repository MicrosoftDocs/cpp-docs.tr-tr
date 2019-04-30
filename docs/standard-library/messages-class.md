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
ms.openlocfilehash: 7a024a8cad8c536b25127d033468874de5ebd8af
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383587"
---
# <a name="messages-class"></a>messages Sınıfı

Verili bir yerel ayar için uluslararası iletilerin bir kataloğundan yerelleştirilmiş iletiler almak için bir yerel ayar olarak hizmet verebilen bir nesneyi tanımlayan bir şablon sınıfı.

Şu anda, ileti sınıfı uygulanırken bir ileti yok.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType>
class messages : public messages_base;
```

### <a name="parameters"></a>Parametreler

*CharType*<br/>
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim içinde benzersiz bir pozitif değer depolar **kimliği.**

Bu model, temelde, messages_base temel sınıfında tanımlanan iletilerin kataloğunu açar, gerekli bilgileri alır ve kataloğu kapatır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[İletileri](#messages)|İleti modeli oluşturucu işlevi.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|İletileri görüntülemek için kullanılan bir karakter türü.|
|[string_type](#string_type)|Türü dizeyi tanımlayan tür `basic_string` türü karakterler içeren `CharType`.|

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

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="char_type"></a>  Messages::char_type

İletileri görüntülemek için kullanılan bir karakter türü.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür **CharType**.

## <a name="close"></a>  Messages::Close

İleti kataloğunu kapatır.

```cpp
void close(catalog _Catval) const;
```

### <a name="parameters"></a>Parametreler

*_Catval*<br/>
Kapatılması Kataloğu.

### <a name="remarks"></a>Açıklamalar

Üye işlev çağrıları [do_close](#do_close)(_ *Catval*).

## <a name="do_close"></a>  Messages::do_close

İleti kataloğunu kapatmak için çağrılan sanal işlev.

```cpp
virtual void do_close(catalog _Catval) const;
```

### <a name="parameters"></a>Parametreler

*_Catval*<br/>
Kapatılması Kataloğu.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi ileti kataloğunu kapatır *_Catval*, hangi gerekir açıldı önceki bir çağrı tarafından [do_open](#do_open).

*_Catval* kapalı önceden açılmış bir kataloğundan elde edilebilir.

### <a name="example"></a>Örnek

Örneğin bakın [kapatmak](#close), çağıran `do_close`.

## <a name="do_get"></a>  Messages::do_get

İleti kataloğunu almak için çağrılan sanal işlev.

```cpp
virtual string_type do_get(
    catalog _Catval,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```

### <a name="parameters"></a>Parametreler

*_Catval*<br/>
İleti kataloğunu aranacak belirten kimlik değeri.

*_Küme*<br/>
İlk tanımlanan bir ileti bir ileti Kataloğu'nda bulmak için kullanılır.

*İl_eti*<br/>
İkinci belirlenen bir ileti bir ileti Kataloğu'nda bulmak için kullanılır.

*_Dfault*<br/>
Hata olduğunda döndürülecek dize.

### <a name="return-value"></a>Dönüş Değeri

Bir kopyasını döndürür *_Dfault* başarısız. Aksi takdirde, belirtilen ileti dizinin bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi bir ileti sırası iletiyi Kataloğu'ndan almayı dener *_Catval*. Bunu yapabilir kullanım *_Düz*, *il_eti*, ve *_Dfault* böylece.

### <a name="example"></a>Örnek

Örneğin bakın [alma](#get), çağıran `do_get`.

## <a name="do_open"></a>  Messages::do_open

İleti kataloğunu açmak için çağrılan sanal işlev.

```cpp
virtual catalog do_open(
    const string& _Catname,
    const locale& _Loc) const;
```

### <a name="parameters"></a>Parametreler

*_Catname*<br/>
Aranacak katalog adı.

*_Loc*<br/>
Katalogda Aranan yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

Küçüktür sıfır üzerinde hata karşılaştıran bir değer döndürür. Aksi takdirde, döndürülen değer sonraki çağrı sırasında ilk bağımsız değişkeni olarak kullanılabilir [alma](#get).

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlev adı olan bir ileti kataloğunu açmayı denediğinde *_Catname*. Bunu yapabilir yerel ayarı kullanmaları *_Loc* böylece

Dönüş değeri bir sonraki çağrısında bağımsız değişken olarak kullanılması gereken [kapatmak](#close).

### <a name="example"></a>Örnek

Örneğin bakın [açın](#open), çağıran `do_open`.

## <a name="get"></a>  Messages::get

İleti kataloğunu alır.

```cpp
string_type get(
    catalog _CatVal,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```

### <a name="parameters"></a>Parametreler

*_Catval*<br/>
İleti kataloğunu aranacak belirten kimlik değeri.

*_Küme*<br/>
İlk tanımlanan bir ileti bir ileti Kataloğu'nda bulmak için kullanılır.

*İl_eti*<br/>
İkinci belirlenen bir ileti bir ileti Kataloğu'nda bulmak için kullanılır.

*_Dfault*<br/>
Hata olduğunda döndürülecek dize.

### <a name="return-value"></a>Dönüş Değeri

Bir kopyasını döndürür *_Dfault* başarısız. Aksi takdirde, belirtilen ileti dizinin bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_get](#do_get)( `_Catval`, `_Set`, `_Message`, `_Dfault`).

## <a name="messages"></a>  Messages::Messages

İleti modeli oluşturucu işlevi.

```cpp
explicit messages(
    size_t _Refs = 0);

protected: messages(
    const char* _Locname,
    size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_Refs*<br/>
Bellek yönetimi için nesne türünü belirtmek için kullanılan tamsayı değeri.

*_Locname*<br/>
Yerel ayar adı.

### <a name="remarks"></a>Açıklamalar

Olası değerler için *_Refs* parametresi ve bunların önemi:

- 0: Nesnenin ömrünü, onu içeren yerel ayarlar tarafından yönetilir.

- 1: Nesnenin ömrünü el ile yönetilmesi gerekir.

- \> 1: Bu değerleri tanımlı değil.

Yok edici korumalı olduğundan doğrudan örnek mümkündür.

Oluşturucu, temel nesnesiyle başlatır **yerel::**[modeli](../standard-library/locale-class.md#facet_class)( `_Refs`).

## <a name="open"></a>  Messages::Open

İleti kataloğunu açar.

```cpp
catalog open(
    const string& _Catname,
    const locale& _Loc) const;
```

### <a name="parameters"></a>Parametreler

*_Catname*<br/>
Aranacak katalog adı.

*_Loc*<br/>
Katalogda Aranan yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

Küçüktür sıfır üzerinde hata karşılaştıran bir değer döndürür. Aksi takdirde, döndürülen değer sonraki çağrı sırasında ilk bağımsız değişkeni olarak kullanılabilir [alma](#get).

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_open](#do_open)( `_Catname`, `_Loc`).

## <a name="string_type"></a>  Messages::string_type

Türü dizeyi tanımlayan tür `basic_string` türü karakterler içeren `CharType`.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [basic_string](../standard-library/basic-string-class.md) ileti dizileri kopyalarını, nesneleri depolayabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel ayar >](../standard-library/locale.md)<br/>
[messages_base Sınıfı](../standard-library/messages-base-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
