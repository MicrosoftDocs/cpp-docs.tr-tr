---
title: time_get sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98ef24f5a714b1df5cb9be0875cdfd5adcb3fe62
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704880"
---
# <a name="timeget-class"></a>time_get Sınıfı

Şablon sınıfı türü dönüştürülmelerini denetlemek için bir yerel ayar modeli olarak hizmet verebilen bir nesneyi tanımlayan `CharType` saat değerlerine.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType,
    class InputIterator = istreambuf_iterator<CharType>>
class time_get : public time_base;
```

### <a name="parameters"></a>Parametreler

*CharType*<br/>
Bir program içindeki karakterleri kodlamak için kullanılan tür.

*Inputıterator*<br/>
Saat değerlerinin okunacağı yineleyici.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim içinde benzersiz bir pozitif değer depolar **kimliği.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[time_get](#time_get)|Türündeki nesneler için oluşturucu `time_get`.|

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
|[do_get_date](#do_get_date)|Korumalı sanal üye işlevi tarafından üretilen tarih olarak bir dizeyi ayrıştırmak için çağrılan `x` tanımlayıcısı için `strftime`.|
|[do_get_monthname](#do_get_monthname)|Bir dizeyi ayın adı olarak ayrıştırmak için çağrılan korumalı sanal üye işlevi.|
|[do_get_time](#do_get_time)|Korumalı sanal üye işlevi tarafından üretilen tarih olarak bir dizeyi ayrıştırmak için çağrılan `X` tanımlayıcısı için `strftime`.|
|[do_get_weekday](#do_get_weekday)|Bir dizeyi haftanın günü adı olarak ayrıştırmak için çağrılan korumalı sanal üye işlevi.|
|[do_get_year](#do_get_year)|Bir dizeyi yılın adı olarak ayrıştırmak için çağrılan korumalı sanal üye işlevi.|
|[get](#get)|Karakter verilerinin bir kaynağından okur ve bu verileri saat yapı biriminde depolanan bir saate dönüştürür.|
|[get_date](#get_date)|Tarafından üretilen tarih olarak bir dizeyi ayrıştırır `x` tanımlayıcısı için `strftime`.|
|[get_monthname](#get_monthname)|Bir dizeyi ayın adı olarak ayrıştırır.|
|[get_time](#get_time)|Tarafından üretilen tarih olarak bir dizeyi ayrıştırır `X` tanımlayıcısı için `strftime`.|
|[get_weekday](#get_weekday)|Bir dizeyi haftanın gününün adı olarak ayrıştırır.|
|[get_year](#get_year)|Bir dizeyi yılın adı olarak ayrıştırır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="char_type"></a>  time_get::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür **CharType**.

## <a name="date_order"></a>  time_get::date_order

Bir model tarafından kullanılan tarih düzenini döndürür.

```cpp
dateorder date_order() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir model tarafından kullanılan tarih düzenini.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_date_order](#do_date_order).

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

Bir model tarafından kullanılan tarih düzenini.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlev türünde bir değer döndürür **time_base::dateorder**, hangi tarih bileşenleri tarafından eşleştirilir siparişi açıklayan [do_get_date](#do_get_date). Bu uygulamada değerdir **time_base::mdy**, tarih biçiminde 2 aralık 1979 ilişkili.

### <a name="example"></a>Örnek

Örneğin bakın [date_order](#date_order), çağıran `do_date_order`.

## <a name="do_get"></a>  time_get::do_get

Karakter verilerini okur ve bir saat değerine dönüştürür. Bir dönüştürme belirleyicisine ve değiştiricisini kabul eder.

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

*ilk*<br/>
Dönüştürülecek dizisi başlangıcını gösteren bir giriş yineleyici.

*Son*<br/>
Dizinin sonuna belirten bir giriş yineleyici.

*iosbase*<br/>
Bir akış nesnesi.

*durumu*<br/>
Bir alan iosbase içinde hatalarını belirtmek için uygun bir bit maskesi öğeleri nerede ayarlanır.

*ptm*<br/>
Depolanacak süresinin olduğu zaman yapısı işaretçisi.

*FMT*<br/>
Bir dönüştürme tanımlayıcı karakteri.

*mod*<br/>
Bir isteğe bağlı bir değiştirici karakter.

### <a name="return-value"></a>Dönüş Değeri

İlk Dönüştürülmeyen öğeyi belirleyen bir yineleyici döndürür. Dönüştürme hatası ayarlar `ios_base::failbit` içinde `state` ve döndürür *ilk*.

### <a name="remarks"></a>Açıklamalar

Sanal üye işlevi dönüştürür ve atlayan bir veya daha fazla giriş aralıktaki öğeleri [`first`, `last`) bir veya daha fazla üyesi içinde depolanan değerleri belirlemek için `*pt`. Dönüştürme hatası ayarlar `ios_base::failbit` içinde `state` ve döndürür *ilk*. Aksi halde, işlev Dönüştürülmeyen ilk öğeyi gösteren bir yineleyici döndürür.

Dönüştürme tanımlayıcılarıdır:

`'a'` veya `'A'` --gibi davranır [time_get::get_weekday](#get_weekday).

`'b'`, `'B'`, veya `'h'` --gibi davranır [time_get::get_monthname](#get_monthname).

`'c'` --gibi davranır `"%b %d %H : %M : %S %Y"`.

`'C'` --değeri [0, 99] aralığında bir ondalık giriş alanını dönüştürür `val` ve depolar `val * 100 - 1900` içinde `pt-&tm_year`.

`'d'` veya `'e'` --[1, 31] aralığında bir ondalık giriş alanını dönüştürür ve onun değeri depolar `pt-&tm_mday`.

`'D'` --gibi davranır `"%m / %d / %y"`.

`'H'` --[0, 23] aralığında bir ondalık giriş alanını dönüştürür ve değeriyle depolar `pt-&tm_hour`.

`'I'` --[0, 11] aralığında bir ondalık giriş alanını dönüştürür ve değeriyle depolar `pt-&tm_hour`.

`'j'` --[1, 366] aralığında bir ondalık giriş alanını dönüştürür ve değeriyle depolar `pt-&tm_yday`.

`'m'` --[1, 12] aralığında bir ondalık giriş alan değerine dönüştürür `val` ve depolar `val - 1` içinde ve değeriyle depolar `pt-&tm_mon`.

`'M'` --[0, 59] aralığında bir ondalık giriş alanını dönüştürür ve değeriyle depolar `pt-&tm_min`.

`'n'` veya `'t'` --gibi davranır `" "`.

`'p'` --"AM" veya "am" sıfır ve "PM" veya "PM" 12'ye dönüştürür ve bu değeri ekler `pt-&tm_hour`.

`'r'` --gibi davranır `"%I : %M : %S %p"`.

`'R'` --gibi davranır `"%H %M"`.

`'S'` --[0, 59] aralığında bir ondalık giriş alanını dönüştürür ve değeriyle depolar `pt-&tm_sec`.

`'T'` veya `'X'` --gibi davranır `"%H : %M : S"`.

`'U'` --[0, 53] aralığında bir ondalık giriş alanını dönüştürür ve değeriyle depolar `pt-&tm_yday`.

`'w'` --[0, 6] aralığında bir ondalık giriş alanını dönüştürür ve değeriyle depolar `pt-&tm_wday`.

`'W'` --[0, 53] aralığında bir ondalık giriş alanını dönüştürür ve değeriyle depolar `pt-&tm_yday`.

`'x'` --gibi davranır `"%d / %m / %y"`.

`'y'` --değeri [0, 99] aralığında bir ondalık giriş alanını dönüştürür `val` ve depolar `val < 69  val + 100 : val` içinde `pt-&tm_year`.

`'Y'` --gibi davranır [time_get::get_year](#get_year).

Başka bir dönüştürme belirleyici kümeleri `ios_base::failbit` içinde `state` ve döndürür. Bu uygulama, tüm değiştirici etkisi yoktur.

## <a name="do_get_date"></a>  time_get::do_get_date

Korumalı sanal üye işlevi tarafından üretilen tarih olarak bir dizeyi ayrıştırmak için çağrılan *x* tanımlayıcısı için `strftime`.

```cpp
virtual iter_type do_get_date(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Dönüştürülecek dizisi başına ele alan giriş yineleyici.

*Son*<br/>
Dönüştürülecek dizisi sonunu ele alan giriş yineleyici.

*iosbase*<br/>
Bir biçim, bayrak kümesi para birimi simgesi isteğe bağlı; olduğunu belirtiyorsa Aksi takdirde, gerekli değildir.

*durumu*<br/>
İşlem başarılı olup olmadığını göre akış durumu için uygun bir bit maskesi öğeleri ayarlar.

*ptm*<br/>
Tarih bilgisi depolanacak olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesindeki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi dizideki ilk konumunda başlayan ardışık öğeleri eşleştirmeyi dener [ `first`, `last`) tam tanıdığını kadar alan boş olmayan bir tarih girin. Başarılı olursa, bu alan eşdeğer değerine bileşenleri olarak dönüştürür, **tm::tm\_Pzt**, **tm::tm\_gün**, ve **tm::tm\_yıl** ve sonuçları depolar `ptm->tm_mon`, `ptm->tm_day`, ve `ptm->tm_year`sırasıyla. Tarih giriş alanı ötesindeki ilk öğeyi gösteren bir yineleyici döndürür. Aksi halde, işlev ayarlar `iosbase::failbit` içinde *durumu*. Giriş geçerli bir tarih alanının herhangi bir önek ötesindeki ilk öğeyi gösteren bir yineleyici döndürür. Her iki durumda da dönüş değeri eşitse *son*, işlev kümeleri `ios_base::eofbit` içinde *durumu*.

Tarih giriş alanı için yerel ayara bağımlı biçimidir. Varsayılan yerel ayar için tarih giriş alanı formu AAA gg, YYYY, sahip olduğu:

- MMM çağırarak eşleşir [get_monthname](#get_monthname), ayı verir.

- GG ayın gününü vermiş gerekir karşılık gelen sayısal değeri [1, 31] aralığında, ondalık basamak dizisi ' dir.

- YYYY çağırarak eşleşir [get_year](#get_year), yılın verir.

Değişmez değer boşluk ve virgül Giriş dizisindeki karşılık gelen öğelerle eşleşmesi gerekir.

### <a name="example"></a>Örnek

Örneğin bakın [get_date](#get_date), çağıran `do_get_date`.

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

*ilk*<br/>
Dönüştürülecek dizisi başına ele alan giriş yineleyici.

*Son*<br/>
Dönüştürülecek dizisi sonunu ele alan giriş yineleyici.

*iosbase*<br/>
Kullanılmayan.

*durumu*<br/>
İşlem başarılı olup olmadığını göre akış durumu için uygun bir bit maskesi öğeleri ayarlar çıkış parametresi.

*ptm*<br/>
Ay bilgilerin depolanacağı olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesindeki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi dizideki ilk konumunda başlayan ardışık öğeleri eşleştirmeyi dener [ `first`, `last`) tam tanıdığını kadar alan boş bir ay giriş. Başarılı, bu alan eşdeğeri değer bileşeni olarak dönüştürür, **tm::tm\_Pzt**ve sonuçta depolar `ptm->tm_mon`. Ay giriş alanı ötesindeki ilk öğeyi gösteren bir yineleyici döndürür. Aksi halde, işlev ayarlar `ios_base::failbit` içinde *durumu*. Geçerli ay giriş alanının herhangi bir önek ötesinde ilk öğeyi gösteren bir yineleyici döndürür. Her iki durumda da dönüş değeri eşitse *son*, işlev kümeleri `ios_base::eofbit` içinde *durumu*.

Ay giriş alanı gibi Oca, Ocak, Şubat, Şubat, yerel ayara özgü dizileri ve benzeri bir dizi en uzun eşleşen bir dizidir. Dönüştürülen Ocak itibaren ay sayısını değerdir.

### <a name="example"></a>Örnek

Örneğin bakın [get_monthname](#get_monthname), çağıran `do_get_monthname`.

## <a name="do_get_time"></a>  time_get::do_get_time

Korumalı sanal üye işlevi tarafından üretilen tarih olarak bir dizeyi ayrıştırmak için çağrılan *X* tanımlayıcısı için `strftime`.

```cpp
virtual iter_type do_get_time(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Dönüştürülecek dizisi başına ele alan giriş yineleyici.

*Son*<br/>
Dönüştürülecek dizisi sonunu ele alan giriş yineleyici.

*iosbase*<br/>
Kullanılmayan.

*durumu*<br/>
İşlem başarılı olup olmadığını göre akış durumu için uygun bir bit maskesi öğeleri ayarlar.

*ptm*<br/>
Tarih bilgisi depolanacak olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesindeki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi dizideki ilk konumunda başlayan ardışık öğeleri eşleştirmeyi dener [ `first`, `last`) tam tanıdığını kadar alan boş saat girin. Başarılı olursa, bu alan eşdeğer değerine bileşenleri olarak dönüştürür, `tm::tm_hour`, `tm::tm_min`, ve `tm::tm_sec`ve sonuçları depolar `ptm->tm_hour`, `ptm->tm_min`, ve `ptm->tm_sec`sırasıyla. Zaman giriş alanı ötesindeki ilk öğeyi gösteren bir yineleyici döndürür. Aksi halde, işlev ayarlar `ios_base::failbit` içinde *durumu*. Geçerli zamanı giriş alanının herhangi bir önek ötesindeki ilk öğeyi gösteren bir yineleyici döndürür. Her iki durumda da dönüş değeri eşitse *son*, işlev kümeleri `ios_base::eofbit` içinde *durumu*.

Bu uygulama, zaman giriş alanı ss, formundadır burada:

- HH karşılık gelen sayısal değeri aralığında olması gerekir, ondalık basamak dizisi olduğundan [0, 24), günün saati verir.

- AA karşılık gelen sayısal değeri aralığında olması gerekir, ondalık basamak dizisi olduğundan [0, 60), saati aşan dakika verir.

- Karşılık gelen sayısal değeri aralığında olması gerekir, ondalık basamak dizisi SS ise [0, 60), dakikayı aşan saniye verir.

Değişmez değer iki nokta üst üste Giriş dizisindeki karşılık gelen öğelerle eşleşmesi gerekir.

### <a name="example"></a>Örnek

Örneğin bakın [get_time](#get_time), çağıran `do_get_time`.

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

*ilk*<br/>
Dönüştürülecek dizisi başına ele alan giriş yineleyici.

*Son*<br/>
Dönüştürülecek dizisi sonunu ele alan giriş yineleyici.

*iosbase*<br/>
Bir biçim, bayrak kümesi para birimi simgesi isteğe bağlı; olduğunu belirtiyorsa Aksi takdirde, gerekli değildir.

*durumu*<br/>
İşlem başarılı olup olmadığını göre akış durumu için uygun bir bit maskesi öğeleri ayarlar.

*ptm*<br/>
Hafta içi bilgilerin depolanacağı olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesindeki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi konumunda başlayan ardışık öğeleri eşleştirmeyi dener *ilk* dizideki [ `first`, `last`) tam tanıdığını kadar alan boş bir haftanın günü giriş. Başarılı, bu alan eşdeğeri değer bileşeni olarak dönüştürür, **tm::tm\_wday**ve sonuçta depolar `ptm->tm_wday`. Haftanın günü giriş alanı ötesinde ilk öğeyi gösteren bir yineleyici döndürür. Aksi halde, işlev ayarlar `ios_base::failbit` içinde *durumu*. Bu, geçerli hafta içi giriş alanının herhangi bir önek ötesinde ilk öğeyi gösteren bir yineleyici döndürür. Her iki durumda da dönüş değeri eşitse *son*, işlev kümeleri `ios_base::eofbit` içinde *durumu*.

Haftanın günü giriş alanı gibi Sun, Pazar, Pzt, Pazartesi, yerel ayara özgü dizileri ve benzeri bir dizi en uzun eşleşen bir dizidir. Dönüştürülen değer Pazar itibaren geçen gün sayısıdır.

### <a name="example"></a>Örnek

Örneğin bakın [get_weekday](#get_weekday), çağıran `do_get_weekday`.

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

*ilk*<br/>
Dönüştürülecek dizisi başına ele alan giriş yineleyici.

*Son*<br/>
Dönüştürülecek dizisi sonunu ele alan giriş yineleyici.

*iosbase*<br/>
Bir biçim, bayrak kümesi para birimi simgesi isteğe bağlı; olduğunu belirtiyorsa Aksi takdirde, gerekli değildir.

*durumu*<br/>
İşlem başarılı olup olmadığını göre akış durumu için uygun bir bit maskesi öğeleri ayarlar.

*ptm*<br/>
Yıl bilgileri depolanacak olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesindeki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi konumunda başlayan ardışık öğeleri eşleştirmeyi dener *ilk* dizideki [ `first`, `last`) tam tanıdığını kadar alan boş olmayan bir yıl girin. Başarılı, bu alan eşdeğeri değer bileşeni olarak dönüştürür, **tm::tm\_yıl**ve sonuçta depolar `ptm->tm_year`. Yıl giriş alanı ötesinde ilk öğeyi gösteren bir yineleyici döndürür. Aksi halde, işlev ayarlar `ios_base::failbit` içinde *durumu*. Geçerli yıl giriş alanının herhangi bir önek ötesinde ilk öğeyi gösteren bir yineleyici döndürür. Her iki durumda da dönüş değeri eşitse *son*, işlev kümeleri `ios_base::eofbit` içinde *durumu*.

Yıl giriş alanı karşılık gelen sayısal değeri aralığında olması gerekir, ondalık basamak dizisi olduğundan [1900, 2036). Depolanan değeri eksi 1900 değerdir. Bu uygulama, aralıktaki değerleri [69, 136) yıl aralığını temsil eden [1969, 2036). Aralığındaki değerleri [0, 69) ayrıca verilebilir, ancak her iki yıl aralığını gösterebilir [1900, 1969) veya [2000, 2069) belirli çeviri ortamına bağlı olarak.

### <a name="example"></a>Örnek

Örneğin bakın [get_year](#get_year), çağıran `do_get_year`.

## <a name="get"></a>  time_get::get

Karakter verilerinin bir kaynağından okur ve bu verileri saat yapı biriminde depolanan bir saate dönüştürür. İlk işlev bir dönüştürme belirleyicisine ve değiştiricisini kabul eder, ikinci birkaç kabul eder.

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

*ilk*<br/>
Dönüştürülecek dizisi başladığı gösteren giriş yineleyici.

*Son*<br/>
Dönüştürülecek dizinin sonuna belirten giriş yineleyici.

*iosbase*<br/>
Akış.

*durumu*<br/>
Uygun bir bit maskesi öğelerini, hataları göstermek akış durumu için ayarlanır.

*ptm*<br/>
Depolanacak süresinin olduğu zamanı yapısına yönelik işaretçi.

*FMT*<br/>
Bir dönüştürme tanımlayıcı karakteri.

*mod*<br/>
Bir isteğe bağlı bir değiştirici karakter.

*fmt_first*<br/>
Biçim yönergeleri başladığı için işaret eder.

*fmt_last*<br/>
Biçim yönergeleri sonuna işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Saat yapı atamak için kullanılan verileri sonra ilk karakter için bir yineleyici döndürür `*ptm`.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi döndürür `do_get(first, last, iosbase, state, ptm, fmt, mod)`.

İkinci üye işlev çağrıları `do_get` tarafından ayrılmış biçiminin denetiminde `[fmt_first, fmt_last)`. Her biri sıfır dönüşümü belirler bir dizi alanları biçimi işler veya daha fazla giriş tarafından sınırlanan öğelerin `[first, last)`. Dönüştürülmeyen ilk öğeyi gösteren bir yineleyici döndürür. Alanların üç türü vardır:

Bir yüzde (%) biçiminde isteğe bağlı bir değiştirici tarafından izlenen *mod* kümesinde [EOQ #], bir dönüştürme tanımlayıcı tarafından izlenen *fmt*, yerini alan *ilk* tarafından döndürülen değeri ile `do_get(first, last, iosbase, state, ptm, fmt, mod)`. Dönüştürme hatası ayarlar `ios_base::failbit` içinde *durumu* ve döndürür.

Bir boşluk öğesi biçimde sıfır atlar veya daha fazla boşluk öğeleri giriş.

Herhangi bir öğe biçimde atlandı sonraki giriş öğesinin eşleşmesi gerekir. Bir eşleşme hatası ayarlar `ios_base::failbit` içinde *durumu* ve döndürür.

## <a name="get_date"></a>  time_get::get_date

Tarafından üretilen tarih olarak bir dizeyi ayrıştırır *x* tanımlayıcısı için `strftime`.

```cpp
iter_type get_date(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Dönüştürülecek dizisi başına ele alan giriş yineleyici.

*Son*<br/>
Dönüştürülecek dizisi sonunu ele alan giriş yineleyici.

*iosbase*<br/>
Bir biçim, bayrak kümesi para birimi simgesi isteğe bağlı; olduğunu belirtiyorsa Aksi takdirde, gerekli değildir.

*durumu*<br/>
İşlem başarılı olup olmadığını göre akış durumu için uygun bir bit maskesi öğeleri ayarlar.

*ptm*<br/>
Tarih bilgisi depolanacak olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesindeki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_get_date](#do_get_date)(`first`, `last`, `iosbase`, `state`, `ptm`).

Aylar 0 ile 11'e sayıldığını unutmayın.

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

## <a name="get_monthname"></a>  time_get::get_monthname

Bir dizeyi ayın adı olarak ayrıştırır.

```cpp
iter_type get_monthname(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Dönüştürülecek dizisi başına ele alan giriş yineleyici.

*Son*<br/>
Dönüştürülecek dizisi sonunu ele alan giriş yineleyici.

*iosbase*<br/>
Kullanılmayan.

*durumu*<br/>
İşlem başarılı olup olmadığını göre akış durumu için uygun bir bit maskesi öğeleri ayarlar çıkış parametresi.

*ptm*<br/>
Ay bilgilerin depolanacağı olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesindeki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_get_monthname](#do_get_monthname)(`first`, `last`, `iosbase`, `state`, `ptm`).

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

## <a name="get_time"></a>  time_get::get_time

Tarafından üretilen tarih olarak bir dizeyi ayrıştırır *X* tanımlayıcısı için `strftime`.

```cpp
iter_type get_time(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Dönüştürülecek dizisi başına ele alan giriş yineleyici.

*Son*<br/>
Dönüştürülecek dizisi sonunu ele alan giriş yineleyici.

*iosbase*<br/>
Kullanılmayan.

*durumu*<br/>
İşlem başarılı olup olmadığını göre akış durumu için uygun bir bit maskesi öğeleri ayarlar.

*ptm*<br/>
Tarih bilgisi depolanacak olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesindeki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_get_time](#do_get_time)(`first`, `last`, `iosbase`, `state`, `ptm`).

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

## <a name="get_weekday"></a>  time_get::get_weekday

Bir dizeyi haftanın gününün adı olarak ayrıştırır.

```cpp
iter_type get_weekday(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Dönüştürülecek dizisi başına ele alan giriş yineleyici.

*Son*<br/>
Dönüştürülecek dizisi sonunu ele alan giriş yineleyici.

*iosbase*<br/>
Bir biçim, bayrak kümesi para birimi simgesi isteğe bağlı; olduğunu belirtiyorsa Aksi takdirde, gerekli değildir.

*durumu*<br/>
İşlem başarılı olup olmadığını göre akış durumu için uygun bir bit maskesi öğeleri ayarlar.

*ptm*<br/>
Hafta içi bilgilerin depolanacağı olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesindeki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_get_weekday](#do_get_weekday)(`first`, `last`, `iosbase`, `state`, `ptm`).

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

## <a name="get_year"></a>  time_get::get_year

Bir dizeyi yılın adı olarak ayrıştırır.

```cpp
iter_type get_year(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*ilk*<br/>
Dönüştürülecek dizisi başına ele alan giriş yineleyici.

*Son*<br/>
Dönüştürülecek dizisi sonunu ele alan giriş yineleyici.

*iosbase*<br/>
Bir biçim, bayrak kümesi para birimi simgesi isteğe bağlı; olduğunu belirtiyorsa Aksi takdirde, gerekli değildir.

*durumu*<br/>
İşlem başarılı olup olmadığını göre akış durumu için uygun bir bit maskesi öğeleri ayarlar.

*ptm*<br/>
Yıl bilgileri depolanacak olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesindeki ilk öğeyi ele alan bir giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_get_year](#do_get_year)(`first`, `last`, `iosbase`, `state`, `ptm`).

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

## <a name="iter_type"></a>  time_get::iter_type

Bir giriş yineleyiciyi açıklayan tür.

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür **Inputıterator**.

## <a name="time_get"></a>  time_get::time_get

Türündeki nesneler için oluşturucu `time_get`.

```cpp
explicit time_get(size_t refs = 0);
```

### <a name="parameters"></a>Parametreler

*refs*<br/>
Bellek yönetimi için nesne türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Olası değerler için *refs* parametresi ve bunların önemi:

- 0: nesne ömrü onu içeren yerel ayarlar tarafından yönetilir.

- 1: nesne ömrü el ile yönetilmesi gerekir.

- \> 1: Bu değerler tanımlanmadı.

Yok edici korumalı olduğundan doğrudan örnek mümkündür.

Oluşturucu, temel nesnesiyle başlatır **yerel::**[modeli](../standard-library/locale-class.md#facet_class)(`refs`).

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel ayar >](../standard-library/locale.md)<br/>
[time_base Sınıfı](../standard-library/time-base-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
