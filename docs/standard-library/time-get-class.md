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
ms.openlocfilehash: 7c3db9edd974d111881b17b6f1a53c1b4ac3b336
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33862854"
---
# <a name="timeget-class"></a>time_get Sınıfı

Şablon sınıfı türü sıralarının denetim dönüştürmeleri için yerel ayar modeli olarak hizmet verebilir bir nesneyi tanımlayan `CharType` saat değerleri için.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType,
    class InputIterator = istreambuf_iterator<CharType>>
class time_get : public time_base;
```

### <a name="parameters"></a>Parametreler

`CharType` Bir program içinden karakterlerin kodlanması için kullanılan türü.

`InputIterator` Saat değerleri okunduğu yineleyici.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Benzersiz bir pozitif değer saklı değerini erişmek için ilk deneme depolar **kimliği.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[time_get](#time_get)|Nesne türü Oluşturucusu `time_get`.|

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
|[do_get_date](#do_get_date)|Bir korumalı bir dize tarafından üretilen tarih olarak ayrıştırılacak adlı sanal üye işlevi `x` tanımlayıcısı için `strftime`.|
|[do_get_monthname](#do_get_monthname)|Bir dizeyi ayın adı olarak ayrıştırmak için çağrılan korumalı sanal üye işlevi.|
|[do_get_time](#do_get_time)|Bir korumalı bir dize tarafından üretilen tarih olarak ayrıştırılacak adlı sanal üye işlevi `X` tanımlayıcısı için `strftime`.|
|[do_get_weekday](#do_get_weekday)|Bir dizeyi haftanın günü adı olarak ayrıştırmak için çağrılan korumalı sanal üye işlevi.|
|[do_get_year](#do_get_year)|Bir dizeyi yılın adı olarak ayrıştırmak için çağrılan korumalı sanal üye işlevi.|
|[get](#get)|Karakter verilerinin bir kaynağından okur ve bu verileri saat yapı biriminde depolanan bir saate dönüştürür.|
|[get_date](#get_date)|Tarafından üretilen tarih olarak bir dize ayrıştırır `x` tanımlayıcısı için `strftime`.|
|[get_monthname](#get_monthname)|Bir dizeyi ayın adı olarak ayrıştırır.|
|[get_time](#get_time)|Tarafından üretilen tarih olarak bir dize ayrıştırır `X` tanımlayıcısı için `strftime`.|
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

Şablon parametresi için bir eş anlamlı türüdür **CharType**.

## <a name="date_order"></a>  time_get::date_order

Bir model tarafından kullanılan tarih düzenini döndürür.

```cpp
dateorder date_order() const;
```

### <a name="return-value"></a>Dönüş Değeri

Modeli tarafından kullanılan tarih sırası.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [do_date_order](#do_date_order).

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

Modeli tarafından kullanılan tarih sırası.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye fonksiyonu türünde bir değer döndürür **time_base::dateorder**, hangi tarih bileşenleri tarafından eşleştirilir sipariş açıklayan [do_get_date](#do_get_date). Bu uygulama, değerdir **time_base::mdy**, 2 aralık 1979 tarihleri biçiminde ilişkili.

### <a name="example"></a>Örnek

Örneğin bkz [date_order](#date_order), çağıran `do_date_order`.

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

`first` Dönüştürme sırası başlangıcı gösteren giriş yineleyici.

`last` Dizinin sonuna gösteren bir giriş yineleyici.

`iosbase` Bir akış nesnesi.

`state` Uygun bir bit maskesi öğeleri hatalarını belirtmek için burada ayarlanan bir alana iosbase.

`ptm` Süre depolanması olduğu zaman yapısı için bir işaretçi.

`fmt` Bir dönüştürme belirleyici karakter.

`mod` Bir isteğe bağlı değiştiricisi karakter.

### <a name="return-value"></a>Dönüş Değeri

İlk Dönüştürülmeyen öğesi atayan bir yineleyici döndürür. Dönüştürme hatası ayarlar `ios_base::failbit` içinde `state` ve döndürür `first`.

### <a name="remarks"></a>Açıklamalar

Sanal üye işlevi dönüştürür ve atlayan bir veya daha fazla aralığında öğeleri giriş [`first`, `last`) bir veya daha fazla üyesi içinde depolanan değerleri belirlemek için `*pt`. Dönüştürme hatası ayarlar `ios_base::failbit` içinde `state` ve döndürür `first`. Aksi durumda, ilk Dönüştürülmeyen öğesi belirleme yineleyici işlevi döndürür.

Dönüştürme tanımlayıcıları şunlardır:

`'a'` veya `'A'` --aynı şekilde davranır [time_get::get_weekday](#get_weekday).

`'b'`, `'B'`, veya `'h'` --aynı şekilde davranır [time_get::get_monthname](#get_monthname).

`'c'` --aynı şekilde davranır `"%b %d %H : %M : %S %Y"`.

`'C'` --[0, 99] aralığında bir ondalık giriş alan değerine dönüştürür `val` ve depolar `val * 100 - 1900` içinde `pt-&tm_year`.

`'d'` veya `'e'` --[1, 31] aralığında bir ondalık giriş alanı dönüştürür ve değeriyle depolar `pt-&tm_mday`.

`'D'` --aynı şekilde davranır `"%m / %d / %y"`.

`'H'` --[0, 23] aralığında bir ondalık giriş alanı dönüştürür ve değeriyle depolar `pt-&tm_hour`.

`'I'` --[0, 11] aralığındaki bir ondalık giriş alanı dönüştürür ve değeriyle depolar `pt-&tm_hour`.

`'j'` --[1, 366] aralığında bir ondalık giriş alanı dönüştürür ve değeriyle depolar `pt-&tm_yday`.

`'m'` --[1, 12] aralığında bir ondalık giriş alan değerine dönüştürür `val` ve depolar `val - 1` içinde ve değeriyle depolar `pt-&tm_mon`.

`'M'` --[0, 59] aralığında bir ondalık giriş alanı dönüştürür ve değeriyle depolar `pt-&tm_min`.

`'n'` veya `'t'` --aynı şekilde davranır `" "`.

`'p'` --"AM" veya "am" sıfır ve "PM" veya "PM" 12 dönüştürür ve bu değer ekler `pt-&tm_hour`.

`'r'` --aynı şekilde davranır `"%I : %M : %S %p"`.

`'R'` --aynı şekilde davranır `"%H %M"`.

`'S'` --[0, 59] aralığında bir ondalık giriş alanı dönüştürür ve değeriyle depolar `pt-&tm_sec`.

`'T'` veya `'X'` --aynı şekilde davranır `"%H : %M : S"`.

`'U'` --[0, 53] aralığında bir ondalık giriş alanı dönüştürür ve değeriyle depolar `pt-&tm_yday`.

`'w'` --[0, 6] aralığında bir ondalık giriş alanı dönüştürür ve değeriyle depolar `pt-&tm_wday`.

`'W'` --[0, 53] aralığında bir ondalık giriş alanı dönüştürür ve değeriyle depolar `pt-&tm_yday`.

`'x'` --aynı şekilde davranır `"%d / %m / %y"`.

`'y'` --[0, 99] aralığında bir ondalık giriş alan değerine dönüştürür `val` ve depolar `val < 69  val + 100 : val` içinde `pt-&tm_year`.

`'Y'` --aynı şekilde davranır [time_get::get_year](#get_year).

Diğer bir dönüştürme belirleyici kümeleri `ios_base::failbit` içinde `state` ve döndürür. Bu uygulama, tüm değiştiricisi etkisi yoktur.

## <a name="do_get_date"></a>  time_get::do_get_date

Bir korumalı bir dize tarafından üretilen tarih olarak ayrıştırılacak adlı sanal üye işlevi *x* tanımlayıcısı için `strftime`.

```cpp
virtual iter_type do_get_date(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

`first` Dönüştürülecek dizisi başına adresleme yineleyici girin.

`last` Dönüştürülecek bitişinde adresleme yineleyici girin.

`iosbase` Bir biçim hangi bayrak kümesi para birimi simgesini isteğe bağlıdır; olduğunu gösterdiğinde Aksi takdirde, gereklidir.

`state` Olup işlemleri başarılı göre akış durumu için uygun bir bit maskesi öğelerini ayarlar.

`ptm` Tarih bilgisini depolanması olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesinde ilk öğe adresleme giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye fonksiyonu ilk sırada başlayarak sıralı öğeleri eşleştirmeyi dener [ `first`, `last`) bir tam tanıdığını kadar boş olmayan tarih alan giriş. Başarılı, bu alan eşdeğer değerine bileşenleri olarak dönüştürür, **tm::tm\_mon**, **tm::tm\_gün**, ve **tm::tm\_yıl** ve sonuçları depolar `ptm->tm_mon`, `ptm->tm_day`, ve `ptm->tm_year`sırasıyla. Yineleyici tarihi giriş alanı ötesinde ilk öğe belirleme döndürür. Aksi takdirde işlevi ayarlar `iosbase::failbit` içinde `state`. Herhangi bir geçerli tarih giriş alanı öneki ötesinde ilk öğe belirleme yineleyici döndürür. Dönüş değeri eşitse her iki durumda da `last`, işlev kümeleri `ios_base::eofbit` içinde `state`.

Yerel ayara bağımlı tarih giriş alanı için biçimidir. Varsayılan yerel ayar için tarih giriş alanı form AAA DD, YYYY, sahip olduğu:

- AAA çağırarak eşleşir [get_monthname](#get_monthname), ayı verir.

- DD ayın günü aralığında [1, 31], karşılık gelen sayısal değerini vermiş olmalıdır ondalık basamakların bir dizidir.

- YYYY çağırarak eşleşir [get_year](#get_year), yıl vermiş.

Değişmez değer boşluk ve virgül giriş sırası karşılık gelen öğe eşleşmesi gerekir.

### <a name="example"></a>Örnek

Örneğin bkz [get_date](#get_date), çağıran `do_get_date`.

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

`first` Dönüştürülecek dizisi başına adresleme yineleyici girin.

`last` Dönüştürülecek bitişinde adresleme yineleyici girin.

`iosbase` Kullanılmayan.

`state` Akış durumuna göre mi için uygun bir bit maskesi öğelerini ayarlar bir output parametresi işlemleri başarılı oldu.

`ptm` Ay bilgilerin depolanması olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesinde ilk öğe adresleme giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye fonksiyonu ilk sırada başlayarak sıralı öğeleri eşleştirmeyi dener [ `first`, `last`) bir tam tanıdığını kadar boş olmayan ay alan giriş. Başarılı, bu alan bileşeni eşdeğer değerine dönüştürür, **tm::tm\_mon**ve sonuçta depolar `ptm->tm_mon`. Yineleyici ay giriş alanı ötesinde ilk öğe belirleme döndürür. Aksi takdirde işlevi ayarlar `ios_base::failbit` içinde *durumu*. Herhangi bir geçerli ay giriş alanı öneki ötesinde ilk öğe belirleme yineleyici döndürür. Dönüş değeri eşitse her iki durumda da `last`, işlev kümeleri `ios_base::eofbit` içinde *durumu*.

Ay giriş alanı Oca, Ocak, Şub, Şubat gibi yerel ayarlara özgü sıraları ve benzeri bir dizi en uzun eşleşen bir dizidir. Dönüştürülen değer aydan Ocak beri sayısıdır.

### <a name="example"></a>Örnek

Örneğin bkz [get_monthname](#get_monthname), çağıran `do_get_monthname`.

## <a name="do_get_time"></a>  time_get::do_get_time

Bir korumalı bir dize tarafından üretilen tarih olarak ayrıştırılacak adlı sanal üye işlevi *X* tanımlayıcısı için `strftime`.

```cpp
virtual iter_type do_get_time(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

`first` Dönüştürülecek dizisi başına adresleme yineleyici girin.

`last` Dönüştürülecek bitişinde adresleme yineleyici girin.

`iosbase` Kullanılmayan.

`state` Olup işlemleri başarılı göre akış durumu için uygun bir bit maskesi öğelerini ayarlar.

`ptm` Tarih bilgisini depolanması olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesinde ilk öğe adresleme giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye fonksiyonu ilk sırada başlayarak sıralı öğeleri eşleştirmeyi dener [ `first`, `last`) bir tam tanıdığını kadar boş olmayan zaman alan giriş. Başarılı, bu alan eşdeğer değerine bileşenleri olarak dönüştürür, **tm::tm_hour**, **tm::tm_min**, ve **tm::tm_sec**ve sonuçlarındadepolar`ptm->tm_hour`, `ptm->tm_min`, ve `ptm->tm_sec`sırasıyla. Yineleyici zaman giriş alanını ötesinde ilk öğe belirleme döndürür. Aksi takdirde işlevi ayarlar `ios_base::failbit` içinde *durumu*. Herhangi bir geçerli saat giriş alanı öneki ötesinde ilk öğe belirleme yineleyici döndürür. Dönüş değeri eşitse her iki durumda da `last`, işlev kümeleri `ios_base::eofbit` içinde *durumu*.

Bu uygulama, süresi giriş alanını formun ss, sahip olduğu:

- HH olması gereken aralık karşılık gelen sayısal değerini ondalık basamak dizisi değil [0, 24) günün saati verir.

- AA olması gereken aralık karşılık gelen sayısal değerini ondalık basamakların bir dizidir [0, 60) saati aşan dakika vermiş.

- SS olması gereken aralık karşılık gelen sayısal değerini ondalık basamak dizisi değil [0, 60), dakikayı aşan saniye vermiş.

Değişmez değer iki nokta üst üste giriş sırası karşılık gelen öğe ile eşleşmesi gerekir.

### <a name="example"></a>Örnek

Örneğin bkz [get_time](#get_time), çağıran `do_get_time`.

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

`first` Dönüştürülecek dizisi başına adresleme yineleyici girin.

`last` Dönüştürülecek bitişinde adresleme yineleyici girin.

`iosbase` Bir biçim hangi bayrak kümesi para birimi simgesini isteğe bağlıdır; olduğunu gösterdiğinde Aksi takdirde, gereklidir.

`state` Olup işlemleri başarılı göre akış durumu için uygun bir bit maskesi öğelerini ayarlar.

`ptm` Haftanın günü bilgilerin depolanması olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesinde ilk öğe adresleme giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye fonksiyonu başlangıç sıralı öğeleri eşleştirmeyi dener `first` sırada [ `first`, `last`) bir tam tanıdığını kadar boş olmayan bir hafta içi günü alan giriş. Başarılı, bu alan bileşeni eşdeğer değerine dönüştürür, **tm::tm\_wday**ve sonuçta depolar `ptm->tm_wday`. Haftanın günü giriş alanını ötesinde ilk öğe belirleme yineleyici döndürür. Aksi takdirde işlevi ayarlar `ios_base::failbit` içinde *durumu*. Herhangi bir geçerli hafta içi günü giriş alanı öneki ötesinde ilk öğe belirleme yineleyici döndürür. Dönüş değeri eşitse her iki durumda da `last`, işlev kümeleri `ios_base::eofbit` içinde *durumu*.

Haftanın günü giriş alanını Sun, Pazar, Mon, Pazartesi, gibi yerel ayarlara özgü sıraları ve benzeri bir dizi en uzun eşleşen bir dizidir. Dönüştürülen değer Pazar bu yana gün sayısıdır.

### <a name="example"></a>Örnek

Örneğin bkz [get_weekday](#get_weekday), çağıran `do_get_weekday`.

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

`first` Dönüştürülecek dizisi başına adresleme yineleyici girin.

`last` Dönüştürülecek bitişinde adresleme yineleyici girin.

`iosbase` Bir biçim hangi bayrak kümesi para birimi simgesini isteğe bağlıdır; olduğunu gösterdiğinde Aksi takdirde, gereklidir.

`state` Olup işlemleri başarılı göre akış durumu için uygun bir bit maskesi öğelerini ayarlar.

`ptm` Yıl bilgilerin depolanması olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesinde ilk öğe adresleme giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Sanal korumalı üye fonksiyonu başlangıç sıralı öğeleri eşleştirmeyi dener `first` sırada [ `first`, `last`) bir tam tanıdığını kadar boş olmayan yıl alan giriş. Başarılı, bu alan bileşeni eşdeğer değerine dönüştürür, **tm::tm\_yıl**ve sonuçta depolar `ptm->tm_year`. Yineleyici yıl giriş alanını ötesinde ilk öğe belirleme döndürür. Aksi takdirde işlevi ayarlar `ios_base::failbit` içinde *durumu*. Herhangi bir geçerli yıl giriş alanı öneki ötesinde ilk öğe belirleme yineleyici döndürür. Dönüş değeri eşitse her iki durumda da `last`, işlev kümeleri `ios_base::eofbit` içinde *durumu*.

Yıl giriş alanı olması gereken aralık karşılık gelen sayısal değerini ondalık basamak dizisidir [1900, 2036). Bu değer 1900 eksi saklı değeridir. Bu uygulama, aralığında değerleri [69, 136) yıl aralığı temsil eden [1969, 2036). Aralık değerleri [0, 69) de verilebilir, ancak her iki yıl aralığı gösterebilir [1900, 1969) veya [2000, 2069) belirli çeviri ortamına bağlı olarak.

### <a name="example"></a>Örnek

Örneğin bkz [get_year](#get_year), çağıran `do_get_year`.

## <a name="get"></a>  time_get::get

Karakter verilerinin bir kaynağından okur ve bu verileri saat yapı biriminde depolanan bir saate dönüştürür. Bir dönüştürme belirticisi ve değiştirici ilk işlev kabul eder, ikinci birkaç kabul eder.

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

`first` Dönüştürülecek dizisi başladığı gösterir yineleyici girin.

`last` Dönüştürülecek bitişinde gösterir yineleyici girin.

`iosbase` Akış.

`state` Uygun bir bit maskesi öğeleri akış durumu hatalarını belirtmek ayarlanır.

`ptm` Süre depolanması olduğu zaman yapısına yönelik işaretçinin.

`fmt` Bir dönüştürme belirleyici karakter.

`mod` Bir isteğe bağlı değiştiricisi karakter.

`fmt_first` Burada biçimi yönergeleri Başlat noktaları.

`fmt_last` Biçim yönergeleri uç noktalarına.

### <a name="return-value"></a>Dönüş Değeri

Yineleyici zaman yapısı atamak için kullanılan veri sonra ilk karakter döndürür `*ptm`.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevinin döndürdüğü `do_get(first, last, iosbase, state, ptm, fmt, mod)`.

İkinci üye işlev çağrılarını `do_get` tarafından ayrılmış biçimde denetiminde `[fmt_first, fmt_last)`. Biçim her biri sıfır dönüştürülmesi belirler bir dizi alanları davranır veya daha fazla virgülle ayrılan öğeleri giriş `[first, last)`. Yineleyici ilk Dönüştürülmeyen öğesi belirleme döndürür. Üç türde alanlar şunlardır:

Bir yüzde (%) biçiminde bir isteğe bağlı değiştiricisi tarafından izlenen `mod` kümesinde [EOQ #], ardından dönüştürme tanımlayıcısı tarafından `fmt`, değiştirir `first` tarafından döndürülen değer ile `do_get(first, last, iosbase, state, ptm, fmt, mod)`. Dönüştürme hatası ayarlar `ios_base::failbit` içinde `state` ve döndürür.

Sıfır bir boşluk öğesi biçimde atlar veya daha fazla boşluk öğeleri giriş.

Başka bir öğenin biçimde atlanır sonraki input öğesi eşleşmesi gerekir. Bir eşleşme hatası ayarlar `ios_base::failbit` içinde `state` ve döndürür.

## <a name="get_date"></a>  time_get::get_date

Tarafından üretilen tarih olarak bir dize ayrıştırır *x* tanımlayıcısı için `strftime`.

```cpp
iter_type get_date(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

`first` Dönüştürülecek dizisi başına adresleme yineleyici girin.

`last` Dönüştürülecek bitişinde adresleme yineleyici girin.

`iosbase` Bir biçim hangi bayrak kümesi para birimi simgesini isteğe bağlıdır; olduğunu gösterdiğinde Aksi takdirde, gereklidir.

`state` Olup işlemleri başarılı göre akış durumu için uygun bir bit maskesi öğelerini ayarlar.

`ptm` Tarih bilgisini depolanması olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesinde ilk öğe adresleme giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [do_get_date](#do_get_date)( `first`, `last`, `iosbase`, `state`, `ptm`).

Ay 11'den 0'dan sayıldığını unutmayın.

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

`first` Dönüştürülecek dizisi başına adresleme yineleyici girin.

`last` Dönüştürülecek bitişinde adresleme yineleyici girin.

`iosbase` Kullanılmayan.

`state` Akış durumuna göre mi için uygun bir bit maskesi öğelerini ayarlar bir output parametresi işlemleri başarılı oldu.

`ptm` Ay bilgilerin depolanması olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesinde ilk öğe adresleme giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [do_get_monthname](#do_get_monthname)( `first`, `last`, `iosbase`, `state`, `ptm`).

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

Tarafından üretilen tarih olarak bir dize ayrıştırır *X* tanımlayıcısı için `strftime`.

```cpp
iter_type get_time(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

`first` Dönüştürülecek dizisi başına adresleme yineleyici girin.

`last` Dönüştürülecek bitişinde adresleme yineleyici girin.

`iosbase` Kullanılmayan.

`state` Olup işlemleri başarılı göre akış durumu için uygun bir bit maskesi öğelerini ayarlar.

`ptm` Tarih bilgisini depolanması olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesinde ilk öğe adresleme giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [do_get_time](#do_get_time)( `first`, `last`, `iosbase`, `state`, `ptm`).

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

`first` Dönüştürülecek dizisi başına adresleme yineleyici girin.

`last` Dönüştürülecek bitişinde adresleme yineleyici girin.

`iosbase` Bir biçim hangi bayrak kümesi para birimi simgesini isteğe bağlıdır; olduğunu gösterdiğinde Aksi takdirde, gereklidir.

`state` Olup işlemleri başarılı göre akış durumu için uygun bir bit maskesi öğelerini ayarlar.

`ptm` Haftanın günü bilgilerin depolanması olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesinde ilk öğe adresleme giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [do_get_weekday](#do_get_weekday)( `first`, `last`, `iosbase`, `state`, `ptm`).

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

`first` Dönüştürülecek dizisi başına adresleme yineleyici girin.

`last` Dönüştürülecek bitişinde adresleme yineleyici girin.

`iosbase` Bir biçim hangi bayrak kümesi para birimi simgesini isteğe bağlıdır; olduğunu gösterdiğinde Aksi takdirde, gereklidir.

`state` Olup işlemleri başarılı göre akış durumu için uygun bir bit maskesi öğelerini ayarlar.

`ptm` Yıl bilgilerin depolanması olduğu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Giriş alanını ötesinde ilk öğe adresleme giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [do_get_year](#do_get_year)( `first`, `last`, `iosbase`, `state`, `ptm`).

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

Şablon parametresi için bir eş anlamlı türüdür **InputIterator**.

## <a name="time_get"></a>  time_get::time_get

Nesne türü Oluşturucusu `time_get`.

```cpp
explicit time_get(size_t refs = 0);
```

### <a name="parameters"></a>Parametreler

`refs` Bellek yönetimi nesnesinin türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Olası değerler için `refs` parametre ve bunların anlamlı:

- 0: nesne ömrü onu içeren yerel ayarları tarafından yönetilir.

- 1: nesne ömrü el ile yönetilmesi gerekir.

- \> 1: Bu değerleri tanımlanmamış.

Yok Edicisi korunduğu için hiçbir doğrudan örnekler mümkündür.

Oluşturucu temel nesnesiyle başlatır **locale::**[modeli](../standard-library/locale-class.md#facet_class)( `refs`).

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel ayar >](../standard-library/locale.md)<br/>
[time_base Sınıfı](../standard-library/time-base-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
