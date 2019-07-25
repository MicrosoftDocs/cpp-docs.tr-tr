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
ms.openlocfilehash: 45eeb7bdf944682ca168b8bff01b42815cfa7f28
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460007"
---
# <a name="timeget-class"></a>time_get Sınıfı

Şablon sınıfı, zaman değerlerine tür `CharType` dizileri dönüştürmelerini denetlemek için bir yerel ayar modeli olarak kullanılabilecek bir nesneyi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType,
    class InputIterator = istreambuf_iterator<CharType>>
class time_get : public time_base;
```

### <a name="parameters"></a>Parametreler

*CharType*\
Bir program içindeki karakterleri kodlamak için kullanılan tür.

*InputIterator*\
Saat değerlerinin okunacağı yineleyici.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim, kimlik içinde benzersiz bir pozitif değer depolar **.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[time_get](#time_get)|Türündeki `time_get`nesneler için Oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir giriş yineleyiciyi açıklayan tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[date_order](#date_order)|Bir model tarafından kullanılan tarih düzenini döndürür.|
|[do_date_order](#do_date_order)|Bir model tarafından kullanılan tarih düzenini döndürmek için çağrılan korumalı sanal üye işlevi.|
|[do_get](#do_get)|Karakter verilerini okur ve bir saat değerine dönüştürür.|
|[do_get_date](#do_get_date)|`x`Tanımlayıcıtarafından üretilen tarih olarak bir dizeyi ayrıştırmak için çağrılan korumalı bir sanal üye işlevi. `strftime`|
|[do_get_monthname](#do_get_monthname)|Bir dizeyi ayın adı olarak ayrıştırmak için çağrılan korumalı sanal üye işlevi.|
|[do_get_time](#do_get_time)|`X`Tanımlayıcıtarafından üretilen tarih olarak bir dizeyi ayrıştırmak için çağrılan korumalı bir sanal üye işlevi. `strftime`|
|[do_get_weekday](#do_get_weekday)|Bir dizeyi haftanın günü adı olarak ayrıştırmak için çağrılan korumalı sanal üye işlevi.|
|[do_get_year](#do_get_year)|Bir dizeyi yılın adı olarak ayrıştırmak için çağrılan korumalı sanal üye işlevi.|
|[get](#get)|Karakter verilerinin bir kaynağından okur ve bu verileri saat yapı biriminde depolanan bir saate dönüştürür.|
|[get_date](#get_date)|Bir dizeyi, `x` `strftime`belirleyici tarafından üretilen tarih olarak ayrıştırır.|
|[get_monthname](#get_monthname)|Bir dizeyi ayın adı olarak ayrıştırır.|
|[get_time](#get_time)|Bir dizeyi, `X` `strftime`belirleyici tarafından üretilen tarih olarak ayrıştırır.|
|[get_weekday](#get_weekday)|Bir dizeyi haftanın gününün adı olarak ayrıştırır.|
|[get_year](#get_year)|Bir dizeyi yılın adı olarak ayrıştırır.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<yerel ayar >

**Ad alanı:** std

## <a name="char_type"></a>  time_get::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, **CharType**şablon parametresi için bir eş anlamlı.

## <a name="date_order"></a>time_get::d ate_order

Bir model tarafından kullanılan tarih düzenini döndürür.

```cpp
dateorder date_order() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir model tarafından kullanılan tarih sırası.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_date_order](#do_date_order)döndürür.

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

## <a name="do_date_order"></a>  time_get::do_date_order

Bir model tarafından kullanılan tarih düzenini döndürmek için çağrılan korumalı sanal üye işlevi.

```cpp
virtual dateorder do_date_order() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir model tarafından kullanılan tarih sırası.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye işlevi, **time_base::d ateorder**türünde bir değer döndürür. Bu, tarih bileşenlerinin [do_get_date](#do_get_date)tarafından eşleştirildiği sırayı tanımlar. Bu uygulamada, değer **time_base:: mdy**, 2 Aralık 1979 biçiminde olan tarihlere karşılık gelir.

### <a name="example"></a>Örnek

Çağıran`do_date_order` [date_order](#date_order)için örneğe bakın.

## <a name="do_get"></a>  time_get::do_get

Karakter verilerini okur ve bir saat değerine dönüştürür. Bir dönüştürme belirticisi ve değiştirici kabul eder.

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

*adı*\
Dönüştürülecek dizinin başlangıcını gösteren bir giriş Yineleyici.

*soyadına*\
Dizinin sonunu gösteren bir giriş Yineleyici.

*iosbase*\
Stream nesnesi.

*durumunda*\
Itsbase 'de uygun bit maskesi öğelerinin hataları gösterecek şekilde ayarlandığı bir alan.

*PTM*\
Saatin depolanacağı zaman yapısına yönelik bir işaretçi.

*FMT*\
Bir dönüştürme belirleyici karakteri.

*alma*\
İsteğe bağlı bir değiştirici karakteri.

### <a name="return-value"></a>Dönüş Değeri

İlk dönüştürülmemiş öğeyi atayan bir yineleyici döndürür. ' De bir dönüştürme `ios_base::failbit` hatası `state` kümesi ve *ilk*olarak döndürür.

### <a name="remarks"></a>Açıklamalar

Sanal üye işlevi,`first` `last`bir veya daha fazla üyesi içinde depolanan değerleri belirlemede [,) aralığında bir veya daha fazla giriş öğesini dönüştürür ve atlar. `*pt` ' De bir dönüştürme `ios_base::failbit` hatası `state` kümesi ve *ilk*olarak döndürür. Aksi takdirde, işlev, ilk dönüştürülmemiş öğeyi tanımlayarak bir yineleyici döndürür.

Dönüştürme belirticileri şunlardır:

`'a'`ya `'A'` da-- [time_get:: get_weekday](#get_weekday)ile aynı şekilde davranır.

`'b'`, `'B'`, veya `'h'` -- [time_get:: get_monthname](#get_monthname)ile aynı şekilde davranır.

`'c'`--ile aynı şekilde `"%b %d %H : %M : %S %Y"`davranır.

`'C'`--[0, 99] aralığındaki bir ondalık giriş alanını içindeki `val` `pt-&tm_year`değere ve depolarına `val * 100 - 1900` dönüştürür.

`'d'`veya `'e'` --[1, 31] aralığındaki bir ondalık giriş alanını dönüştürür ve değerini içinde `pt-&tm_mday`depolar.

`'D'`--ile aynı şekilde `"%m / %d / %y"`davranır.

`'H'`--[0, 23] aralığındaki bir ondalık giriş alanını dönüştürür ve değerini içinde `pt-&tm_hour`depolar.

`'I'`--[0, 11] aralığındaki bir ondalık giriş alanını dönüştürür ve değerini içinde `pt-&tm_hour`depolar.

`'j'`--[1, 366] aralığındaki bir ondalık giriş alanını dönüştürür ve değerini içinde `pt-&tm_yday`depolar.

`'m'`--[1, 12] aralığındaki ondalık bir giriş alanını değerine `val` dönüştürür `val - 1` ve içindeki değerini `pt-&tm_mon`depolar.

`'M'`--[0, 59] aralığındaki bir ondalık giriş alanını dönüştürür ve değerini içinde `pt-&tm_min`depolar.

`'n'`ya `'t'` da--ile aynı şekilde `" "`davranır.

`'p'`--"har" veya "har" değerlerini sıfıra ve "PM" veya "PM" olarak dönüştürür ve bu değeri öğesine `pt-&tm_hour`ekler.

`'r'`--ile aynı şekilde `"%I : %M : %S %p"`davranır.

`'R'`--ile aynı şekilde `"%H %M"`davranır.

`'S'`--[0, 59] aralığındaki bir ondalık giriş alanını dönüştürür ve değerini içinde `pt-&tm_sec`depolar.

`'T'`ya `'X'` da--ile aynı şekilde `"%H : %M : S"`davranır.

`'U'`--[0, 53] aralığındaki bir ondalık giriş alanını dönüştürür ve değerini içinde `pt-&tm_yday`depolar.

`'w'`--[0, 6] aralığındaki bir ondalık giriş alanını dönüştürür ve değerini içinde `pt-&tm_wday`depolar.

`'W'`--[0, 53] aralığındaki bir ondalık giriş alanını dönüştürür ve değerini içinde `pt-&tm_yday`depolar.

`'x'`--ile aynı şekilde `"%d / %m / %y"`davranır.

`'y'`--[0, 99] aralığındaki bir ondalık giriş alanını içindeki `val` `pt-&tm_year`değere ve depolarına `val < 69  val + 100 : val` dönüştürür.

`'Y'`-- [time_get:: get_year](#get_year)ile aynı şekilde davranır.

Ve ' deki `state` diğer herhangi `ios_base::failbit` bir dönüştürme belirticisi kümesi. Bu uygulamada, herhangi bir değiştiricinin etkisi yoktur.

## <a name="do_get_date"></a>  time_get::do_get_date

İçin`strftime` *x* belirleyicisi tarafından üretilen tarih olarak bir dizeyi ayrıştırmak için çağrılan korumalı bir sanal üye işlevi.

```cpp
virtual iter_type do_get_date(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
Dönüştürülecek sıranın başlangıcını ele alarak giriş Yineleyici.

*soyadına*\
Dönüştürülecek dizinin sonunu ele alarak giriş Yineleyici.

*iosbase*\
Ayarlanan para birimi sembolünün isteğe bağlı olduğunu gösterdiği zaman bir biçim bayrağı. Aksi takdirde, gereklidir.

*durumunda*\
İşlem başarılı olup olmadığına göre akış durumu için uygun bit maskesi öğelerini ayarlar.

*PTM*\
Tarih bilgisinin depolanacağı işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının ötesinde ilk öğeyi ele alan bir giriş Yineleyici.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye işlevi, tamamlanmış ve boş olmayan bir tarih girişi alanı kabul edene kadar, `first`[ `last`,) dizisindeki ilk başlayarak sıralı öğeleri eşleştirmeyi dener. Başarılı olursa, bu alanı, **TM:\_: TM Mon**, **TM:: TM\_Day**ve **TM\_** `ptm->tm_mon`: `ptm->tm_day`: TM Year bileşenleri olarak eşdeğer değerine dönüştürür ve sonuçları,,, ve `ptm->tm_year`sırasıyla. Date giriş alanının ötesinde ilk öğeyi tanımlayarak bir yineleyici döndürür. Aksi takdirde işlev *durum*olarak `iosbase::failbit` ayarlanır. Geçerli bir tarih giriş alanının herhangi bir ön ekinin ötesinde ilk öğeyi tanımlayarak bir yineleyici döndürür. Her iki durumda da, dönüş değeri *en son*eşitse işlev *durum*olarak ayarlanır `ios_base::eofbit` .

Tarih giriş alanının biçimi yerel ayara bağımlıdır. Varsayılan yerel ayar için, tarih girişi alanı MMM gg, YYYY biçiminde bulunur, burada:

- AAA, [get_monthname](#get_monthname)çağırarak, ay sunarak eşleştirilir.

- GG, karşılık gelen sayısal değer [1, 31] aralığında olması gereken, ayın gününü sağlayan bir ondalık basamak dizisidir.

- YYYY, [get_year](#get_year)çağırarak yılı sunarak eşleştirilir.

Sabit değerli boşluklar ve virgüllerin Giriş dizisindeki karşılık gelen öğelerle eşleşmesi gerekir.

### <a name="example"></a>Örnek

Çağıran`do_get_date` [get_date](#get_date)için örneğe bakın.

## <a name="do_get_monthname"></a>  time_get::do_get_monthname

Bir dizeyi ayın adı olarak ayrıştırmak için çağrılan korumalı sanal üye işlevi.

```cpp
virtual iter_type do_get_monthname(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
Dönüştürülecek sıranın başlangıcını ele alarak giriş Yineleyici.

*soyadına*\
Dönüştürülecek dizinin sonunu ele alarak giriş Yineleyici.

*iosbase*\
Kullanılmayan.

*durumunda*\
İşlem başarılı olup olmadığına göre akış durumu için uygun bit maskesi öğelerini ayarlayan çıkış parametresi.

*PTM*\
Ay bilgilerinin depolanacağı işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının ötesinde ilk öğeyi ele alan bir giriş Yineleyici.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye işlevi, tamamlanmış ve boş olmayan bir ay girişi alanı tanınıncaya kadar, `first`[ `last`,) dizisindeki ilk başlayarak sıralı öğeleri eşleştirmeyi dener. Başarılı olursa, bu alanı buna karşılık gelen ona, **TM::\_TM Mon**bileşen olarak dönüştürür ve sonucu içinde `ptm->tm_mon`depolar. Month giriş alanının ötesinde ilk öğeyi tanımlayarak bir yineleyici döndürür. Aksi takdirde işlev *durum*olarak `ios_base::failbit` ayarlanır. Geçerli bir ay giriş alanının herhangi bir ön ekinin ötesinde ilk öğeyi tanımlayarak bir yineleyici döndürür. Her iki durumda da, dönüş değeri *en son*eşitse işlev *durum*olarak ayarlanır `ios_base::eofbit` .

Ay giriş alanı, Oca, Ocak, Şubat, Şubat vb. gibi bir yerel ayara özgü dizilerin en uzun bir kümesini karşılayan bir dizidir. Dönüştürülen değer, Ocak ayına göre geçen ay sayısıdır.

### <a name="example"></a>Örnek

Çağıran`do_get_monthname` [get_monthname](#get_monthname)için örneğe bakın.

## <a name="do_get_time"></a>  time_get::do_get_time

Için`strftime` *X* belirleyicisi tarafından üretilen tarih olarak bir dizeyi ayrıştırmak için çağrılan korumalı bir sanal üye işlevi.

```cpp
virtual iter_type do_get_time(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
Dönüştürülecek sıranın başlangıcını ele alarak giriş Yineleyici.

*soyadına*\
Dönüştürülecek dizinin sonunu ele alarak giriş Yineleyici.

*iosbase*\
Kullanılmayan.

*durumunda*\
İşlem başarılı olup olmadığına göre akış durumu için uygun bit maskesi öğelerini ayarlar.

*PTM*\
Tarih bilgisinin depolanacağı işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının ötesinde ilk öğeyi ele alan bir giriş Yineleyici.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye işlevi, bir tamamlanmış ve boş olmayan bir zaman girişi alanı tanınana kadar `first`, `last`[,) dizisindeki ilk başlayarak sıralı öğeleri eşleştirmeyi dener. Başarılı olursa, bu `tm::tm_hour`alanı bileşenleri `tm::tm_min`, ve `tm::tm_sec`gibi eşdeğer değerine dönüştürür ve sonuçları `ptm->tm_hour`sırasıyla, `ptm->tm_min`ve ile `ptm->tm_sec`depolar. İlk öğeyi, zaman girişi alanının ötesinde bir yineleyici döndürür. Aksi takdirde işlev *durum*olarak `ios_base::failbit` ayarlanır. Geçerli bir zaman girişi alanının herhangi bir ön ekinin ötesinde ilk öğeyi tanımlayarak bir yineleyici döndürür. Her iki durumda da, dönüş değeri *en son*eşitse işlev *durum*olarak ayarlanır `ios_base::eofbit` .

Bu uygulamada, saat girişi alanı HH: MM: SS biçiminde bulunur; burada:

- SS, karşılık gelen sayısal değer [0, 24) aralığında olması gereken, günün saatini sağlayan bir ondalık basamak dizisidir.

- Aa, karşılık gelen sayısal değer [0, 60) aralığında olması gereken ondalık basamaklar dizisidir ve bu da saati geçmiş bir süre verir.

- SS, karşılık gelen sayısal değer [0, 60) aralığında olması gereken ondalık basamakların dizilidir ve bu da dakikayı aşan saniyeleri verir.

İki nokta üst üste Giriş dizisindeki karşılık gelen öğelerle eşleşmelidir.

### <a name="example"></a>Örnek

Çağıran`do_get_time` [get_time](#get_time)için örneğe bakın.

## <a name="do_get_weekday"></a>  time_get::do_get_weekday

Bir dizeyi haftanın günü adı olarak ayrıştırmak için çağrılan korumalı sanal üye işlevi.

```cpp
virtual iter_type do_get_weekday(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
Dönüştürülecek sıranın başlangıcını ele alarak giriş Yineleyici.

*soyadına*\
Dönüştürülecek dizinin sonunu ele alarak giriş Yineleyici.

*iosbase*\
Ayarlanan para birimi sembolünün isteğe bağlı olduğunu gösterdiği zaman bir biçim bayrağı. Aksi takdirde, gereklidir.

*durumunda*\
İşlem başarılı olup olmadığına göre akış durumu için uygun bit maskesi öğelerini ayarlar.

*PTM*\
Hafta içi bilgilerin depolanacağı bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının ötesinde ilk öğeyi ele alan bir giriş Yineleyici.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye işlevi, tamamlanmış, boş bir hafta içi iş  günü giriş alanını kabul edene `first`kadar `last`[,) dizisindeki ilk başlayarak sıralı öğeleri eşleştirmeyi dener. Başarılı olursa, bu alanı buna karşılık gelen bir bileşen **TM:: TM\_wDay**olarak dönüştürür ve sonucu içinde `ptm->tm_wday`depolar. İlk öğeyi, hafta içi giriş alanının ötesinde bir yineleyici döndürür. Aksi takdirde işlev *durum*olarak `ios_base::failbit` ayarlanır. Geçerli bir iş günü giriş alanının herhangi bir ön ekinin ötesinde ilk öğeyi tanımlayarak bir yineleyici döndürür. Her iki durumda da, dönüş değeri *en son*eşitse işlev *durum*olarak ayarlanır `ios_base::eofbit` .

Hafta içi giriş alanı Sun, Pazar, Mon, Pazartesi vb. gibi bir yerel ayara özgü dizilerin en uzun bir kümesini karşılayan bir dizidir. Dönüştürülen değer Pazar tarihinden bu yana geçen gün sayısıdır.

### <a name="example"></a>Örnek

Çağıran`do_get_weekday` [get_weekday](#get_weekday)için örneğe bakın.

## <a name="do_get_year"></a>  time_get::do_get_year

Bir dizeyi yılın adı olarak ayrıştırmak için çağrılan korumalı sanal üye işlevi.

```cpp
virtual iter_type do_get_year(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
Dönüştürülecek sıranın başlangıcını ele alarak giriş Yineleyici.

*soyadına*\
Dönüştürülecek dizinin sonunu ele alarak giriş Yineleyici.

*iosbase*\
Ayarlanan para birimi sembolünün isteğe bağlı olduğunu gösterdiği zaman bir biçim bayrağı. Aksi takdirde, gereklidir.

*durumunda*\
İşlem başarılı olup olmadığına göre akış durumu için uygun bit maskesi öğelerini ayarlar.

*PTM*\
Yıl bilgisinin depolanacağı işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının ötesinde ilk öğeyi ele alan bir giriş Yineleyici.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye işlevi, bir tamamlanmış ve boş olmayan yıl girişi  alanı tanınana kadar, `first`[ `last`,) dizisindeki ilk başlayarak sıralı öğeleri eşleştirmeyi dener. Başarılı olursa, bu alanı buna karşılık gelen bu alanı buna ait **TM::\_TM Year**olarak dönüştürür ve sonucu içinde `ptm->tm_year`depolar. Yıl giriş alanının ötesinde ilk öğeyi tanımlayarak bir yineleyici döndürür. Aksi takdirde işlev *durum*olarak `ios_base::failbit` ayarlanır. Geçerli bir yıl giriş alanının herhangi bir ön ekinin ötesinde ilk öğeyi tanımlayarak bir yineleyici döndürür. Her iki durumda da, dönüş değeri *en son*eşitse işlev *durum*olarak ayarlanır `ios_base::eofbit` .

Yıl girişi alanı, karşılık gelen sayısal değer [1900, 2036) aralığında olması gereken bir ondalık basamak dizisidir. Depolanan değer bu değer eksi 1900 ' dir. Bu uygulamada, [69, 136) aralığındaki değerler [1969, 2036) yıl aralığını temsil eder. [0, 69) aralığındaki değerlere de izin verilir, ancak belirli bir çeviri ortamına bağlı olarak yıl aralığını [1900, 1969) veya [2000, 2069) temsil edebilir.

### <a name="example"></a>Örnek

Çağıran`do_get_year` [get_year](#get_year)için örneğe bakın.

## <a name="get"></a>time_get:: Get

Karakter verilerinin bir kaynağından okur ve bu verileri saat yapı biriminde depolanan bir saate dönüştürür. İlk işlev bir dönüştürme belirticisi ve değiştirici kabul eder, ikincisi birkaç kez kabul eder.

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

*adı*\
Dönüştürülecek sıranın başladığı yeri gösteren giriş Yineleyici.

*soyadına*\
Dönüştürülecek dizinin sonunu gösteren giriş Yineleyici.

*iosbase*\
Akış.

*durumunda*\
Uygun bit maskesi öğeleri, akış durumunun hataları göstermesi için ayarlanır.

*PTM*\
Saatin depolanacağı zaman yapısına yönelik işaretçi.

*FMT*\
Bir dönüştürme belirleyici karakteri.

*alma*\
İsteğe bağlı bir değiştirici karakteri.

*fmt_first*\
Biçim yönergelerinin başlayacağı yeri işaret eder.

*fmt_last*\
Biçim yönergelerinin sonuna işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Zaman yapısını `*ptm`atamak için kullanılan verilerden sonraki ilk karaktere bir yineleyici döndürür.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi döndürür `do_get(first, last, iosbase, state, ptm, fmt, mod)`.

İkinci üye işlevi tarafından `do_get` `[fmt_first, fmt_last)`ayrılan biçimin denetimi altında çağırır. Bu biçim, her biri, tarafından `[first, last)`ayrılmış sıfır veya daha fazla giriş öğesi dönüştürmeyi belirleyen, her biri bir alan dizisi olarak davranır. İlk dönüştürülmemiş öğeyi tanımlayarak bir yineleyici döndürür. Üç tür alan vardır:

Her sent (%) biçimde, sonra [EOQ #] kümesinde isteğe bağlı bir değiştirici *mod* ve ardından bir dönüştürme belirticisi *FMT*değeri, *ilk* olarak tarafından `do_get(first, last, iosbase, state, ptm, fmt, mod)`döndürülen değerle değiştirilir. Bir dönüştürme hatası, `ios_base::failbit` *durum* olarak ayarlanır ve döndürür.

Biçimdeki bir boşluk öğesi, son sıfır veya daha fazla giriş boşluğu öğesi atlar.

Biçimdeki diğer tüm öğeler, atlanan bir sonraki giriş öğesiyle eşleşmelidir. Bir eşleşme hatası `ios_base::failbit` , *durum* ve döndürür.

## <a name="get_date"></a>time_get::get_date

Bir dizeyi için `strftime` *x* belirleyicisi tarafından üretilen tarih olarak ayrıştırır.

```cpp
iter_type get_date(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
Dönüştürülecek sıranın başlangıcını ele alarak giriş Yineleyici.

*soyadına*\
Dönüştürülecek dizinin sonunu ele alarak giriş Yineleyici.

*iosbase*\
Ayarlanan para birimi sembolünün isteğe bağlı olduğunu gösterdiği zaman bir biçim bayrağı. Aksi takdirde, gereklidir.

*durumunda*\
İşlem başarılı olup olmadığına göre akış durumu için uygun bit maskesi öğelerini ayarlar.

*PTM*\
Tarih bilgisinin depolanacağı işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının ötesinde ilk öğeyi ele alan bir giriş Yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_get_date](#do_get_date)`first`döndürür ( `iosbase` `last` ,`state`,,,, ).`ptm`

Ayların 0 ' dan 11 ' e sayıldığını unutmayın.

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

## <a name="get_monthname"></a>time_get::get_monthname

Bir dizeyi ayın adı olarak ayrıştırır.

```cpp
iter_type get_monthname(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
Dönüştürülecek sıranın başlangıcını ele alarak giriş Yineleyici.

*soyadına*\
Dönüştürülecek dizinin sonunu ele alarak giriş Yineleyici.

*iosbase*\
Kullanılmayan.

*durumunda*\
İşlem başarılı olup olmadığına göre akış durumu için uygun bit maskesi öğelerini ayarlayan çıkış parametresi.

*PTM*\
Ay bilgilerinin depolanacağı işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının ötesinde ilk öğeyi ele alan bir giriş Yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_get_monthname](#do_get_monthname)`first`döndürür ( `iosbase` `last` ,`state`,,,, ).`ptm`

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

## <a name="get_time"></a>time_get::get_time

Bir dizeyi için `strftime` *X* belirleyicisi tarafından üretilen tarih olarak ayrıştırır.

```cpp
iter_type get_time(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
Dönüştürülecek sıranın başlangıcını ele alarak giriş Yineleyici.

*soyadına*\
Dönüştürülecek dizinin sonunu ele alarak giriş Yineleyici.

*iosbase*\
Kullanılmayan.

*durumunda*\
İşlem başarılı olup olmadığına göre akış durumu için uygun bit maskesi öğelerini ayarlar.

*PTM*\
Tarih bilgisinin depolanacağı işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının ötesinde ilk öğeyi ele alan bir giriş Yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_get_time](#do_get_time)`first`döndürür ( `iosbase` `last` ,`state`,,,, ).`ptm`

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

## <a name="get_weekday"></a>time_get::get_weekday

Bir dizeyi haftanın gününün adı olarak ayrıştırır.

```cpp
iter_type get_weekday(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
Dönüştürülecek sıranın başlangıcını ele alarak giriş Yineleyici.

*soyadına*\
Dönüştürülecek dizinin sonunu ele alarak giriş Yineleyici.

*iosbase*\
Ayarlanan para birimi sembolünün isteğe bağlı olduğunu gösterdiği zaman bir biçim bayrağı. Aksi takdirde, gereklidir.

*durumunda*\
İşlem başarılı olup olmadığına göre akış durumu için uygun bit maskesi öğelerini ayarlar.

*PTM*\
Hafta içi bilgilerin depolanacağı bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının ötesinde ilk öğeyi ele alan bir giriş Yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_get_weekday](#do_get_weekday)`first`döndürür ( `iosbase` `last` ,`state`,,,, ).`ptm`

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

## <a name="get_year"></a>time_get::get_year

Bir dizeyi yılın adı olarak ayrıştırır.

```cpp
iter_type get_year(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
Dönüştürülecek sıranın başlangıcını ele alarak giriş Yineleyici.

*soyadına*\
Dönüştürülecek dizinin sonunu ele alarak giriş Yineleyici.

*iosbase*\
Ayarlanan para birimi sembolünün isteğe bağlı olduğunu gösterdiği zaman bir biçim bayrağı. Aksi takdirde, gereklidir.

*durumunda*\
İşlem başarılı olup olmadığına göre akış durumu için uygun bit maskesi öğelerini ayarlar.

*PTM*\
Yıl bilgisinin depolanacağı işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanının ötesinde ilk öğeyi ele alan bir giriş Yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_get_year](#do_get_year)`first`döndürür ( `iosbase` `last` ,`state`,,,, ).`ptm`

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

## <a name="iter_type"></a>time_get::iter_type

Bir giriş yineleyiciyi açıklayan tür.

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, **InputIterator**şablon parametresi için bir eş anlamlı.

## <a name="time_get"></a>time_get::time_get

Türündeki `time_get`nesneler için Oluşturucu.

```cpp
explicit time_get(size_t refs = 0);
```

### <a name="parameters"></a>Parametreler

*refs*\
Nesnenin bellek yönetimi türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

*Refs* parametresi için olası değerler ve bunların önemi şunlardır:

- 0: Nesnenin ömrü, kendisini içeren yerel ayarlara göre yönetilir.

- 1: Nesnenin ömrü el ile yönetilmelidir.

- \>1: Bu değerler tanımlı değil.

Yok edicisi korunduğu için doğrudan örnek mümkün değildir.

Oluşturucu kendi temel nesnesini **locale::** [model](../standard-library/locale-class.md#facet_class)(`refs`) ile başlatır.

## <a name="see-also"></a>Ayrıca bkz.

[\<Yerel ayar >](../standard-library/locale.md)\
[time_base sınıfı](../standard-library/time-base-class.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
