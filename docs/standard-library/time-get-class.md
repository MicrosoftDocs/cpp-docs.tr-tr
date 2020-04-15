---
title: time_get Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_get
- locale/std::time_get::char_type
- locale/std::time_get::iter_type
- locale/std::time_get::date_order
- locale/std::time_get::do_date_order
- locale/std::time_get::do_get
- locale/std::time_get::do_get_date
- locale/std::time_get::do_get_monthname
- locale/std::time_get::do_get_time
- locale/std::time_get::do_get_weekday
- locale/std::time_get::do_get_year
- locale/std::time_get::get
- locale/std::time_get::get_date
- locale/std::time_get::get_monthname
- locale/std::time_get::get_time
- locale/std::time_get::get_weekday
- locale/std::time_get::get_year
helpviewer_keywords:
- std::time_get [C++]
- std::time_get [C++], char_type
- std::time_get [C++], iter_type
- std::time_get [C++], date_order
- std::time_get [C++], do_date_order
- std::time_get [C++], do_get
- std::time_get [C++], do_get_date
- std::time_get [C++], do_get_monthname
- std::time_get [C++], do_get_time
- std::time_get [C++], do_get_weekday
- std::time_get [C++], do_get_year
- std::time_get [C++], get
- std::time_get [C++], get_date
- std::time_get [C++], get_monthname
- std::time_get [C++], get_time
- std::time_get [C++], get_weekday
- std::time_get [C++], get_year
ms.assetid: 869d5f5b-dbab-4628-8333-bdea7e272023
ms.openlocfilehash: 9aebdaffc8bf3754bdbda08247f72ae08475711f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368046"
---
# <a name="time_get-class"></a>time_get Sınıfı

Sınıf şablonu, tür ve `CharType` zaman değerlerine dizilerin dönüşümlerini denetlemek için yerel bir yönü olarak hizmet verebilen bir nesneyi açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType,
    class InputIterator = istreambuf_iterator<CharType>>
class time_get : public time_base;
```

### <a name="parameters"></a>Parametreler

*Chartype*\
Bir program içindeki karakterleri kodlamak için kullanılan tür.

*GirişIterator*\
Saat değerlerinin okunacağı yineleyici.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için ilk **girişim, kimlikte** benzersiz bir pozitif değer depolar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[time_get](#time_get)|Tür `time_get`nesneleri için oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir giriş yineleyiciyi açıklayan tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[date_order](#date_order)|Bir model tarafından kullanılan tarih düzenini döndürür.|
|[do_date_order](#do_date_order)|Bir model tarafından kullanılan tarih düzenini döndürmek için çağrılan korumalı sanal üye işlevi.|
|[do_get](#do_get)|Karakter verilerini okur ve bir saat değerine dönüştürür.|
|[do_get_date](#do_get_date)|Bir dize için `x` belirtici tarafından üretilen tarih olarak ayrıştırmak için `strftime`çağrılan korumalı sanal üye işlevi.|
|[do_get_monthname](#do_get_monthname)|Bir dizeyi ayın adı olarak ayrıştırmak için çağrılan korumalı sanal üye işlevi.|
|[do_get_time](#do_get_time)|Bir dize için `X` belirtici tarafından üretilen tarih olarak ayrıştırmak için `strftime`çağrılan korumalı sanal üye işlevi.|
|[do_get_weekday](#do_get_weekday)|Bir dizeyi haftanın günü adı olarak ayrıştırmak için çağrılan korumalı sanal üye işlevi.|
|[do_get_year](#do_get_year)|Bir dizeyi yılın adı olarak ayrıştırmak için çağrılan korumalı sanal üye işlevi.|
|[get](#get)|Karakter verilerinin bir kaynağından okur ve bu verileri saat yapı biriminde depolanan bir saate dönüştürür.|
|[get_date](#get_date)|Bir dize için `x` belirtici tarafından üretilen `strftime`tarih olarak parses.|
|[get_monthname](#get_monthname)|Bir dizeyi ayın adı olarak ayrıştırır.|
|[get_time](#get_time)|Bir dize için `X` belirtici tarafından üretilen `strftime`tarih olarak parses.|
|[get_weekday](#get_weekday)|Bir dizeyi haftanın gününün adı olarak ayrıştırır.|
|[get_year](#get_year)|Bir dizeyi yılın adı olarak ayrıştırır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yerel>

**Ad alanı:** std

## <a name="time_getchar_type"></a><a name="char_type"></a>time_get:char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi **CharType**ile eş anlamlıdır.

## <a name="time_getdate_order"></a><a name="date_order"></a>time_get::date_order

Bir model tarafından kullanılan tarih düzenini döndürür.

```cpp
dateorder date_order() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir facet tarafından kullanılan tarih sırası.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_date_order](#do_date_order)döndürür.

### <a name="example"></a>Örnek

```cpp
// time_get_date_order.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
void po( char *p )
{
   locale loc( p );

   time_get <char>::dateorder order = use_facet <time_get <char> >( loc ).date_order ( );
   cout << loc.name( );
   switch (order){
      case time_base::dmy: cout << "(day, month, year)" << endl;
      break;
      case time_base::mdy: cout << "(month, day, year)" << endl;
      break;
      case time_base::ydm: cout << "(year, day, month)" << endl;
      break;
      case time_base::ymd: cout << "(year, month, day)"<< endl;
      break;
      case time_base::no_order: cout << "(no_order)"<< endl;
      break;
   }
}

int main( )
{
   po( "C" );
   po( "german" );
   po( "English_Britain" );
}
```

```Output
C(month, day, year)
German_Germany.1252(day, month, year)
English_United Kingdom.1252(day, month, year)
```

## <a name="time_getdo_date_order"></a><a name="do_date_order"></a>time_get::do_date_order

Bir model tarafından kullanılan tarih düzenini döndürmek için çağrılan korumalı sanal üye işlevi.

```cpp
virtual dateorder do_date_order() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir facet tarafından kullanılan tarih sırası.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye işlevi, tarih bileşenlerinin [do_get_date](#do_get_date)eşleşerek eşleşip eşleşme sini açıklayan **tip time_base::dateorder'** un değerini döndürür. Bu uygulamada, değeri **time_base::mdy**, formun tarihlerine karşılık gelen 2 Aralık 1979.

### <a name="example"></a>Örnek

[date_order](#date_order)için örnek bakın `do_date_order`, hangi çağırır .

## <a name="time_getdo_get"></a><a name="do_get"></a>time_get::do_get

Karakter verilerini okur ve bir saat değerine dönüştürür. Bir dönüştürme belirticisini ve değiştiricisini kabul eder.

```cpp
virtual iter_type
    do_get(
iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm,
    char fmt,
    char mod) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Dönüştürmek için sıranın başlangıcını gösteren bir Giriş yineleyici.

*Son*\
Dizinin sonunu gösteren bir Giriş yineleyicisi.

*iosbase*\
Bir akış nesnesi.

*Durum*\
Iosbase'de uygun bitmaskesi öğelerinin hataları belirtmek üzere ayarlandığı bir alan.

*ptm*\
Zamanın depolandığı zaman yapısına işaretçi.

*Fmt*\
Dönüşüm belirtici karakteri.

*mod*\
İsteğe bağlı bir değiştirici karakter.

### <a name="return-value"></a>Dönüş Değeri

Dönüştürülmemiş ilk öğeyi belirleyen bir yineleyici döndürür. Dönüşüm hatası `ios_base::failbit` önce `state` başlar ve *önce*döndürür.

### <a name="remarks"></a>Açıklamalar

Sanal üye işlevi, bir veya daha fazla üyede`first` `last` `*pt`depolanan değerleri belirlemek için aralıktaki bir veya daha fazla giriş öğesini dönüştürür ve atlar [ , ) Dönüşüm hatası `ios_base::failbit` önce `state` başlar ve *önce*döndürür. Aksi takdirde, işlev ilk dönüştürülmemiş öğeyi atamış bir yineleyici döndürür.

Dönüşüm belirteçleri şunlardır:

`'a'`veya `'A'` -- [time_get](#get_weekday)gibi aynı şekilde get_weekday.

`'b'`, `'B'`veya `'h'` -- [time_get](#get_monthname)gibi aynı şekilde get_monthname.

`'c'`-- aynı şekilde `"%b %d %H : %M : %S %Y"`olur.

`'C'`-- aralığındaki [0, 99] bir ondalık giriş alanını `val` değere `pt-&tm_year`dönüştürür ve .'deki depoları `val * 100 - 1900`

`'d'`veya `'e'` -- aralıktaki bir ondalık giriş alanını dönüştürür [1, 31] ve değerini `pt-&tm_mday`.

`'D'`-- aynı şekilde `"%m / %d / %y"`olur.

`'H'`-- aralığındaki bir ondalık giriş alanını dönüştürür [0, 23] `pt-&tm_hour`ve değerini .

`'I'`-- aralığındaki bir ondalık giriş alanını dönüştürür [0, 11] `pt-&tm_hour`ve değerini .

`'j'`-- aralıktaki bir ondalık giriş alanını dönüştürür [1, 366] `pt-&tm_yday`ve değerini .

`'m'`-- aralığındaki [1, 12] bir ondalık giriş alanını `val` değere dönüştürür ve `pt-&tm_mon`değerini .'de depolar `val - 1` ve depolar.

`'M'`-- aralığındaki bir ondalık giriş alanını dönüştürür [0, 59] `pt-&tm_min`ve değerini .

`'n'`ya `'t'` da -- aynı `" "`şekilde.

`'p'`-- veya ami sıfıra, PM veya PMi `pt-&tm_hour`12'ye dönüştürür ve bu değeri.

`'r'`-- aynı şekilde `"%I : %M : %S %p"`olur.

`'R'`-- aynı şekilde `"%H %M"`olur.

`'S'`-- aralığındaki bir ondalık giriş alanını dönüştürür [0, 59] `pt-&tm_sec`ve değerini .

`'T'`ya `'X'` da -- aynı `"%H : %M : S"`şekilde.

`'U'`-- aralığındaki bir ondalık giriş alanını dönüştürür [0, 53] `pt-&tm_yday`ve değerini .

`'w'`-- aralığındaki bir ondalık giriş alanını dönüştürür [0, 6] `pt-&tm_wday`ve değerini .

`'W'`-- aralığındaki bir ondalık giriş alanını dönüştürür [0, 53] `pt-&tm_yday`ve değerini .

`'x'`-- aynı şekilde `"%d / %m / %y"`olur.

`'y'`-- aralığındaki [0, 99] bir ondalık giriş alanını `val` değere `pt-&tm_year`dönüştürür ve .'deki depoları `val < 69  val + 100 : val`

`'Y'`-- time_get gibi aynı şekilde [olur::get_year](#get_year).

Diğer dönüşüm belirtici `ios_base::failbit` setleri `state` ve döndürür. Bu uygulamada, herhangi bir değiştirici nin hiçbir etkisi yoktur.

## <a name="time_getdo_get_date"></a><a name="do_get_date"></a>time_get::do_get_date

X *belirtici* tarafından üretilen tarih olarak bir dize ayrıştırmak için `strftime`çağrılan korumalı sanal üye işlevi.

```cpp
virtual iter_type do_get_date(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Dönüştürülecek dizinin başlangıcına hitap eden giriş yineleyici.

*Son*\
Dönüştürülecek dizinin sonunu ele alan giriş yineleyici.

*iosbase*\
Ayarlandığında para birimi simgesinin isteğe bağlı olduğunu gösteren biçim bayrağı; aksi takdirde, gereklidir.

*Durum*\
Akış durumu için uygun bitmask öğelerini, işlemlerin başarılı olup olmadığına göre ayarlar.

*ptm*\
Tarih bilgilerinin depolanacak yeri işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının dışındaki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye işlevi, tam, boş olmayan `first`bir `last`tarih giriş alanını tanıyana kadar sıralı öğeleri ilk sırada [, ) olarak eşleştirmeye çalışır. Başarılı olursa, bu alanı **\_tm::tm mon**, **tm::tm\_gün**ve **\_tm::tm yılı**bileşenleri olarak eşdeğer değerine dönüştürür ve sonuçları `ptm->tm_mon`sırasıyla , `ptm->tm_day`ve `ptm->tm_year`, Tarih giriş alanının ötesindeki ilk öğeyi ataen bir yineleyici döndürür. Aksi takdirde, `iosbase::failbit` işlev *duruma*göre ayarlar. Geçerli bir tarih giriş alanının herhangi bir önekinin ötesinde ilk öğeyi ataan bir yineleyici döndürür. Her iki durumda da, iade değeri *son* `ios_base::eofbit` eşitse, işlev *durum*olarak ayarlar.

Tarih giriş alanının biçimi yerel olarak bağlıdır. Varsayılan yerel olarak, tarih giriş alanı MMM DD, YYYY, nerede formu vardır:

- MMM, [get_monthname](#get_monthname)arayarak, ay vererek eşleşir.

- DD, karşılık gelen sayısal değeri ayın gününü veren [1, 31]aralığında olması gereken ondalık basamakdizisidir.

- YYYY [get_year](#get_year)arayarak eşleşir, yıl vererek.

Gerçek boşluklar ve virgüller giriş dizisindeki karşılık gelen öğelerle eşleşmelidir.

### <a name="example"></a>Örnek

[get_date](#get_date)için örnek bakın `do_get_date`, hangi çağırır .

## <a name="time_getdo_get_monthname"></a><a name="do_get_monthname"></a>time_get::do_get_monthname

Bir dizeyi ayın adı olarak ayrıştırmak için çağrılan korumalı sanal üye işlevi.

```cpp
virtual iter_type do_get_monthname(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Dönüştürülecek dizinin başlangıcına hitap eden giriş yineleyici.

*Son*\
Dönüştürülecek dizinin sonunu ele alan giriş yineleyici.

*iosbase*\
Kullanılmıyor.

*Durum*\
İşlemlerin başarılı olup olmadığına göre akış durumu için uygun bitmaskesi öğelerini ayarlayan bir çıkış parametresi.

*ptm*\
Ay bilgilerinin depolanacak yeri işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının dışındaki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye işlevi, tam, boş olmayan `first`ay `last`giriş alanını tanıyana kadar sıralı öğelerin ilk başta [, ) sırayla başlamasıyla eşleşmeye çalışır. Başarılı olursa, bu alanı **tm::tm\_mon**bileşeni olarak eşdeğer değerine dönüştürür `ptm->tm_mon`ve sonucu . Ay giriş alanının ötesindeki ilk öğeyi ataen bir yineleyici döndürür. Aksi takdirde, `ios_base::failbit` işlev *duruma*göre ayarlar. Geçerli bir ay giriş alanının herhangi bir önekinin ötesinde ilk öğeyi ataan bir yineleyici döndürür. Her iki durumda da, iade değeri *son* `ios_base::eofbit` eşitse, işlev *durum*olarak ayarlar.

Ay giriş alanı, Jan, Ocak, Şubat, Şubat ve benzeri yerel ayarlar kümesinin en uzun eşleyen dizisidir. Dönüştürülen değer, Ocak ayından bu yana geçen ay sayısıdır.

### <a name="example"></a>Örnek

[get_monthname](#get_monthname)için örneğe bakın `do_get_monthname`, hangi çağırır .

## <a name="time_getdo_get_time"></a><a name="do_get_time"></a>time_get::do_get_time

*X* için belirtimi yapan tarih olarak bir dize ayrıştırmak için `strftime`çağrılan korumalı sanal üye işlevi.

```cpp
virtual iter_type do_get_time(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Dönüştürülecek dizinin başlangıcına hitap eden giriş yineleyici.

*Son*\
Dönüştürülecek dizinin sonunu ele alan giriş yineleyici.

*iosbase*\
Kullanılmıyor.

*Durum*\
Akış durumu için uygun bitmask öğelerini, işlemlerin başarılı olup olmadığına göre ayarlar.

*ptm*\
Tarih bilgilerinin depolanacak yeri işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının dışındaki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye işlevi, tam, boş olmayan `first`bir `last`zaman giriş alanını tanıyana kadar sıralı öğeleri ilk sırada [, ) olarak eşleştirmeye çalışır. Başarılı olursa, bu alanı `tm::tm_hour`bileşenler olarak `tm::tm_min`eşdeğer değerine `tm::tm_sec`dönüştürür ve sonuçları `ptm->tm_hour`sırasıyla , `ptm->tm_min`ve `ptm->tm_sec`, olarak depolar. Zaman giriş alanının ötesindeki ilk öğeyi ataen bir yineleyici döndürür. Aksi takdirde, `ios_base::failbit` işlev *duruma*göre ayarlar. Geçerli bir zaman giriş alanının herhangi bir önekinin ötesinde ilk öğeyi ataan bir yineleyici döndürür. Her iki durumda da, iade değeri *son* `ios_base::eofbit` eşitse, işlev *durum*olarak ayarlar.

Bu uygulamada, zaman giriş alanı HH:MM:SS formuna sahiptir ve burada:

- HH, karşılık gelen sayısal değeri [0, 24) aralığında olması gereken ondalık basamakdizisidir ve günün saatini verir.

- MM, karşılık gelen sayısal değeri [0, 60) aralığında olması gereken ondalık basamakdizisidir ve dakikaları saati geçmiş olarak verir.

- SS, karşılık gelen sayısal değeri [0, 60) aralığında olması gereken ondalık basamakdizisidir ve saniyeleri dakikayı geçmiş olarak verir.

Gerçek iki nokta üst üste giriş dizisindeki karşılık gelen öğelerle eşleşmelidir.

### <a name="example"></a>Örnek

[get_time](#get_time)için örneğe bakın `do_get_time`, hangi çağırır .

## <a name="time_getdo_get_weekday"></a><a name="do_get_weekday"></a>time_get::do_get_weekday

Bir dizeyi haftanın günü adı olarak ayrıştırmak için çağrılan korumalı sanal üye işlevi.

```cpp
virtual iter_type do_get_weekday(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Dönüştürülecek dizinin başlangıcına hitap eden giriş yineleyici.

*Son*\
Dönüştürülecek dizinin sonunu ele alan giriş yineleyici.

*iosbase*\
Ayarlandığında para birimi simgesinin isteğe bağlı olduğunu gösteren biçim bayrağı; aksi takdirde, gereklidir.

*Durum*\
Akış durumu için uygun bitmask öğelerini, işlemlerin başarılı olup olmadığına göre ayarlar.

*ptm*\
Hafta içi bilgilerinin depolanacak yeri işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının dışındaki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye işlevi, sırayla *başlayan* sıralı `first` `last`öğeleri [ , ) tam, boş olmayan bir hafta içi giriş alanını tanıyana kadar eşleştirmeye çalışır. Başarılı olursa, bu alanı tm bileşeni olarak eşdeğer değerine **\_dönüştürür::tm wday**, `ptm->tm_wday`ve sonucu . Hafta içi giriş alanının ötesindeki ilk öğeyi ataen bir yineleyici döndürür. Aksi takdirde, `ios_base::failbit` işlev *duruma*göre ayarlar. Geçerli bir hafta içi giriş alanının herhangi bir önekinin ötesinde ilk öğeyi ataan bir yineleyici döndürür. Her iki durumda da, iade değeri *son* `ios_base::eofbit` eşitse, işlev *durum*olarak ayarlar.

Hafta içi giriş alanı, Sun, Sunday, Mon, Monday gibi yerel eve özgü dizilerin en uzunuyla eşleşen bir dizidir. Dönüştürülen değer, Pazar gününden bu yana geçen gün sayısıdır.

### <a name="example"></a>Örnek

[get_weekday](#get_weekday)için örneğe bakın `do_get_weekday`, hangi çağırır .

## <a name="time_getdo_get_year"></a><a name="do_get_year"></a>time_get::do_get_year

Bir dizeyi yılın adı olarak ayrıştırmak için çağrılan korumalı sanal üye işlevi.

```cpp
virtual iter_type do_get_year(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Dönüştürülecek dizinin başlangıcına hitap eden giriş yineleyici.

*Son*\
Dönüştürülecek dizinin sonunu ele alan giriş yineleyici.

*iosbase*\
Ayarlandığında para birimi simgesinin isteğe bağlı olduğunu gösteren biçim bayrağı; aksi takdirde, gereklidir.

*Durum*\
Akış durumu için uygun bitmask öğelerini, işlemlerin başarılı olup olmadığına göre ayarlar.

*ptm*\
Yıl bilgilerinin depolanacak yeri işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının dışındaki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye işlevi, tam, boş olmayan `first`bir `last`yıl giriş alanını tanıyana kadar *sıralı* öğeleri ilk sırada [, ) olarak eşleştirmeye çalışır. Başarılı olursa, bu alanı **tm::tm\_yılı**bileşeni olarak eşdeğer değerine dönüştürür `ptm->tm_year`ve sonucu . Yıl giriş alanının ötesindeki ilk öğeyi ataen bir yineleyici döndürür. Aksi takdirde, `ios_base::failbit` işlev *duruma*göre ayarlar. Geçerli bir yıl giriş alanının herhangi bir önekinin ötesinde ilk öğeyi ataen bir yineleyici döndürür. Her iki durumda da, iade değeri *son* `ios_base::eofbit` eşitse, işlev *durum*olarak ayarlar.

Yıl giriş alanı, karşılık gelen sayısal değeri aralıkta olması gereken ondalık basamaklar dizisidir [1900, 2036). Depolanan değer eksi 1900'dür. Bu uygulamada, aralıktaki değerler [69, 136) yıl aralığını temsil eder [1969, 2036). [0, 69) aralığındaki değerler de izin verilir, ancak belirli çeviri ortamına bağlı olarak yıl aralığını [1900, 1969) veya [2000, 2069) temsil edebilir.

### <a name="example"></a>Örnek

[get_year](#get_year)için örneğe bakın `do_get_year`, hangi çağırır .

## <a name="time_getget"></a><a name="get"></a>time_get::get

Karakter verilerinin bir kaynağından okur ve bu verileri saat yapı biriminde depolanan bir saate dönüştürür. İlk işlev bir dönüşüm belirtimi ve değiştirici kabul eder, ikinci birkaç kabul eder.

```cpp
iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm,
    char fmt,
    char mod) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm,
    char_type* fmt_first,
    char_type* fmt_last) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Dönüştürülecek dizinin nerede başladığını gösteren giriş yineleyici.

*Son*\
Dönüştürülecek dizinin sonunu gösteren giriş yineleyici.

*iosbase*\
Dere.

*Durum*\
Akış durumunun hataları göstermesi için uygun bitmaskesi öğeleri ayarlanır.

*ptm*\
Saatin depolanacağı zaman yapısını işaretleyin.

*Fmt*\
Dönüşüm belirtici karakteri.

*mod*\
İsteğe bağlı bir değiştirici karakter.

*fmt_first*\
Biçim yönergelerinin başladığı yeri işaret eder.

*fmt_last*\
Biçim yönergelerinin sonuna işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Zaman struct `*ptm`atamak için kullanılan verilerden sonra ilk karaktere bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

İlk üye işlev `do_get(first, last, iosbase, state, ptm, fmt, mod)`döndürür.

İkinci üye işlev, biçimin denetimi `do_get` altında `[fmt_first, fmt_last)`. Biçimi, her biri sıfır veya daha fazla giriş öğesinin `[first, last)`'le sınırlandırılmış dönüşümünün belirlenmesini belirleyen bir alan dizisi olarak ele Dönüştürülmemiş ilk öğeyi atamış bir yineleyici döndürür. Üç tür alan vardır:

Yüzde a (%) biçiminde, set [EOQ#], ardından bir dönüşüm belirtici *fmt*isteğe bağlı bir değiştirici *mod* takip , `do_get(first, last, iosbase, state, ptm, fmt, mod)`tarafından döndürülen değer ile *ilk* değiştirir . Dönüşüm hatası `ios_base::failbit` *duruma* göre ayarlar ve döndürür.

Biçimdeki bir beyaz uzay öğesi, sıfır veya daha fazla giriş beyaz alan öğesini atlar.

Biçimdeki herhangi bir diğer öğe, atlanan bir sonraki giriş öğesiyle eşleşmelidir. Bir eşleşme `ios_base::failbit` hatası *duruma* göre ayarlar ve döndürür.

## <a name="time_getget_date"></a><a name="get_date"></a>time_get:get_date

*X* belirtici tarafından üretilen tarih olarak bir `strftime`dize parses.

```cpp
iter_type get_date(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Dönüştürülecek dizinin başlangıcına hitap eden giriş yineleyici.

*Son*\
Dönüştürülecek dizinin sonunu ele alan giriş yineleyici.

*iosbase*\
Ayarlandığında para birimi simgesinin isteğe bağlı olduğunu gösteren biçim bayrağı; aksi takdirde, gereklidir.

*Durum*\
Akış durumu için uygun bitmask öğelerini, işlemlerin başarılı olup olmadığına göre ayarlar.

*ptm*\
Tarih bilgilerinin depolanacak yeri işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının dışındaki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_get_date](#do_get_date)`first`döndürür ( , `last`, `iosbase`, `state`, , ). `ptm`

Ayların 0'dan 11'e kadar sayıldığını unutmayın.

### <a name="example"></a>Örnek

```cpp
// time_get_get_date.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc;
   basic_stringstream< char > pszGetF, pszPutF, pszGetI, pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset(&t, 0, sizeof(struct tm));

   pszGetF << "July 4, 2000";
   pszGetF.imbue( loc );
   basic_istream<char>::_Iter i = use_facet <time_get<char> >
   (loc).get_date(basic_istream<char>::_Iter(pszGetF.rdbuf( ) ),
            basic_istream<char>::_Iter(0), pszGetF, st, &t);

   if ( st & ios_base::failbit )
      cout << "time_get("<< pszGetF.rdbuf( )->str( )<< ") FAILED on char: " << *i << endl;
   else

      cout << "time_get("<< pszGetF.rdbuf( )->str( )<< ") ="
      << "\ntm_sec: " << t.tm_sec
      << "\ntm_min: " << t.tm_min
      << "\ntm_hour: " << t.tm_hour
      << "\ntm_mday: " << t.tm_mday
      << "\ntm_mon: " << t.tm_mon
      << "\ntm_year: " << t.tm_year
      << "\ntm_wday: " << t.tm_wday
      << "\ntm_yday: " << t.tm_yday
      << "\ntm_isdst: " << t.tm_isdst
      << endl;
}
```

```Output
time_get(July 4, 2000) =
tm_sec: 0
tm_min: 0
tm_hour: 0
tm_mday: 4
tm_mon: 6
tm_year: 100
tm_wday: 0
tm_yday: 0
tm_isdst: 0
```

## <a name="time_getget_monthname"></a><a name="get_monthname"></a>time_get:get_monthname

Bir dizeyi ayın adı olarak ayrıştırır.

```cpp
iter_type get_monthname(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Dönüştürülecek dizinin başlangıcına hitap eden giriş yineleyici.

*Son*\
Dönüştürülecek dizinin sonunu ele alan giriş yineleyici.

*iosbase*\
Kullanılmıyor.

*Durum*\
İşlemlerin başarılı olup olmadığına göre akış durumu için uygun bitmaskesi öğelerini ayarlayan bir çıkış parametresi.

*ptm*\
Ay bilgilerinin depolanacak yeri işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının dışındaki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_get_monthname](#do_get_monthname)`first`döndürür ( , `last`, `iosbase`, `state`, , ). `ptm`

### <a name="example"></a>Örnek

```cpp
// time_get_get_monthname.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc ( "French" );
   basic_stringstream<char> pszGetF, pszPutF, pszGetI, pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset( &t, 0, sizeof( struct tm ) );

   pszGetF << "juillet";
   pszGetF.imbue( loc );
   basic_istream<char>::_Iter i = use_facet <time_get <char> >
   (loc).get_monthname(basic_istream<char>::_Iter(pszGetF.rdbuf( )),
              basic_istream<char>::_Iter(0), pszGetF, st, &t);

   if (st & ios_base::failbit)
      cout << "time_get("<< pszGetF.rdbuf( )->str( )<< ") FAILED on char: " << *i << endl;
   else

      cout << "time_get("<< pszGetF.rdbuf( )->str( )<< ") ="
      << "\ntm_sec: " << t.tm_sec
      << "\ntm_min: " << t.tm_min
      << "\ntm_hour: " << t.tm_hour
      << "\ntm_mday: " << t.tm_mday
      << "\ntm_mon: " << t.tm_mon
      << "\ntm_year: " << t.tm_year
      << "\ntm_wday: " << t.tm_wday
      << "\ntm_yday: " << t.tm_yday
      << "\ntm_isdst: " << t.tm_isdst
      << endl;
}
```

```Output
time_get(juillet) =
tm_sec: 0
tm_min: 0
tm_hour: 0
tm_mday: 0
tm_mon: 6
tm_year: 0
tm_wday: 0
tm_yday: 0
tm_isdst: 0
```

## <a name="time_getget_time"></a><a name="get_time"></a>time_get::get_time

*X* için belirtici tarafından üretilen tarih olarak `strftime`bir dize parses.

```cpp
iter_type get_time(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Dönüştürülecek dizinin başlangıcına hitap eden giriş yineleyici.

*Son*\
Dönüştürülecek dizinin sonunu ele alan giriş yineleyici.

*iosbase*\
Kullanılmıyor.

*Durum*\
Akış durumu için uygun bitmask öğelerini, işlemlerin başarılı olup olmadığına göre ayarlar.

*ptm*\
Tarih bilgilerinin depolanacak yeri işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının dışındaki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_get_time](#do_get_time)`first`döndürür ( , `last`, `iosbase`, `state`, . `ptm`

### <a name="example"></a>Örnek

```cpp
// time_get_get_time.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc;
   basic_stringstream<char> pszGetF, pszPutF, pszGetI, pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset( &t, 0, sizeof( struct tm ) );

   pszGetF << "11:13:20";
   pszGetF.imbue( loc );
   basic_istream<char>::_Iter i = use_facet
      <time_get <char> >
      (loc).get_time(basic_istream<char>::_Iter(pszGetF.rdbuf( )),
               basic_istream<char>::_Iter(0), pszGetF, st, &t);

   if (st & ios_base::failbit)
      cout << "time_get::get_time("<< pszGetF.rdbuf( )->str( )<< ") FAILED on char: " << *i << endl;
   else

      cout << "time_get::get_time("<< pszGetF.rdbuf( )->str( )<< ") ="
      << "\ntm_sec: " << t.tm_sec
      << "\ntm_min: " << t.tm_min
      << "\ntm_hour: " << t.tm_hour
      << endl;
}
```

```Output
time_get::get_time(11:13:20) =
tm_sec: 20
tm_min: 13
tm_hour: 11
```

## <a name="time_getget_weekday"></a><a name="get_weekday"></a>time_get:get_weekday

Bir dizeyi haftanın gününün adı olarak ayrıştırır.

```cpp
iter_type get_weekday(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Dönüştürülecek dizinin başlangıcına hitap eden giriş yineleyici.

*Son*\
Dönüştürülecek dizinin sonunu ele alan giriş yineleyici.

*iosbase*\
Ayarlandığında para birimi simgesinin isteğe bağlı olduğunu gösteren biçim bayrağı; aksi takdirde, gereklidir.

*Durum*\
Akış durumu için uygun bitmask öğelerini, işlemlerin başarılı olup olmadığına göre ayarlar.

*ptm*\
Hafta içi bilgilerinin depolanacak yeri işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının dışındaki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_get_weekday](#do_get_weekday)`first`döndürür ( , `last`, `iosbase`, `state`, , . `ptm`

### <a name="example"></a>Örnek

```cpp
// time_get_get_weekday.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc ( "French" );
   basic_stringstream< char > pszGetF, pszPutF, pszGetI, pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset( &t, 0, sizeof( struct tm ) );

   pszGetF << "mercredi";
   pszGetF.imbue(loc);
   basic_istream<char>::_Iter i = use_facet
      <time_get<char> >
      (loc).get_weekday(basic_istream<char>::_Iter(pszGetF.rdbuf( )),
               basic_istream<char>::_Iter(0), pszGetF, st, &t);

   if (st & ios_base::failbit)
      cout << "time_get::get_time("<< pszGetF.rdbuf( )->str( )<< ") FAILED on char: " << *i << endl;
   else

      cout << "time_get::get_time("<< pszGetF.rdbuf( )->str( )<< ") ="
      << "\ntm_wday: " << t.tm_wday
      << endl;
}
```

```Output
time_get::get_time(mercredi) =
tm_wday: 3
```

## <a name="time_getget_year"></a><a name="get_year"></a>time_get:get_year

Bir dizeyi yılın adı olarak ayrıştırır.

```cpp
iter_type get_year(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*Ilk*\
Dönüştürülecek dizinin başlangıcına hitap eden giriş yineleyici.

*Son*\
Dönüştürülecek dizinin sonunu ele alan giriş yineleyici.

*iosbase*\
Ayarlandığında para birimi simgesinin isteğe bağlı olduğunu gösteren biçim bayrağı; aksi takdirde, gereklidir.

*Durum*\
Akış durumu için uygun bitmask öğelerini, işlemlerin başarılı olup olmadığına göre ayarlar.

*ptm*\
Yıl bilgilerinin depolanacak yeri işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının dışındaki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_get_year](#do_get_year)`first`döndürür ( , `last`, `iosbase`, `state`, . `ptm`

### <a name="example"></a>Örnek

```cpp
// time_get_get_year.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc;
   basic_stringstream<char> pszGetF, pszPutF, pszGetI, pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset( &t, 0, sizeof( struct tm ) );

   pszGetF << "1928";

   pszGetF.imbue( loc );
   basic_istream<char>::_Iter i = use_facet
      <time_get<char> >
      (loc).get_year(basic_istream<char>::_Iter(pszGetF.rdbuf( )),
               basic_istream<char>::_Iter(0), pszGetF, st, &t);

   if (st & ios_base::failbit)
      cout << "time_get::get_year("<< pszGetF.rdbuf( )->str( )<< ") FAILED on char: " << *i << endl;
   else

      cout << "time_get::get_year("<< pszGetF.rdbuf( )->str( )<< ") ="
      << "\ntm_year: " << t.tm_year
      << endl;
}
```

```Output
time_get::get_year(1928) =
tm_year: 28
```

## <a name="time_getiter_type"></a><a name="iter_type"></a>time_get::iter_type

Bir giriş yineleyiciyi açıklayan tür.

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Tür şablon parametre **InputIterator**için eşanlamlıdır.

## <a name="time_gettime_get"></a><a name="time_get"></a>time_get:time_get

Tür `time_get`nesneleri için oluşturucu.

```cpp
explicit time_get(size_t refs = 0);
```

### <a name="parameters"></a>Parametreler

*refler*\
Nesneiçin bellek yönetimi türünü belirtmek için kullanılan eden arameger değeri.

### <a name="remarks"></a>Açıklamalar

*Refs* parametresi için olası değerler ve önemi şunlardır:

- 0: Nesnenin ömrü, onu içeren yerel nesneler tarafından yönetilir.

- 1: Nesnenin ömrü el ile yönetilmelidir.

- \>1: Bu değerler tanımlı değildir.

Yıkıcı korunduğundan, doğrudan örnek yoktur.

Kurucu, temel nesnesini yerel olarak başlaşır:: **locale::**[fason](../standard-library/locale-class.md#facet_class)( ).`refs`

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel>](../standard-library/locale.md)\
[time_base Sınıfı](../standard-library/time-base-class.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
