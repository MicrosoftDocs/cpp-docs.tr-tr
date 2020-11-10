---
title: '`codecvt` Sınıfı'
description: Microsoft C çalışma zamanı `codecvt` sınıfı API 'sini açıklar
ms.date: 11/09/2020
f1_keywords:
- xlocale/std::codecvt
- xlocale/std::codecvt::extern_type
- xlocale/std::codecvt::intern_type
- xlocale/std::codecvt::state_type
- xlocale/std::codecvt::always_noconv
- xlocale/std::codecvt::do_always_noconv
- xlocale/std::codecvt::do_encoding
- xlocale/std::codecvt::do_in
- xlocale/std::codecvt::do_length
- xlocale/std::codecvt::do_max_length
- xlocale/std::codecvt::do_out
- xlocale/std::codecvt::do_unshift
- xlocale/std::codecvt::encoding
- xlocale/std::codecvt::in
- xlocale/std::codecvt::length
- xlocale/std::codecvt::max_length
- xlocale/std::codecvt::out
- xlocale/std::codecvt::unshift
helpviewer_keywords:
- std::codecvt [C++]
- std::codecvt [C++], extern_type
- std::codecvt [C++], intern_type
- std::codecvt [C++], state_type
- std::codecvt [C++], always_noconv
- std::codecvt [C++], do_always_noconv
- std::codecvt [C++], do_encoding
- std::codecvt [C++], do_in
- std::codecvt [C++], do_length
- std::codecvt [C++], do_max_length
- std::codecvt [C++], do_out
- std::codecvt [C++], do_unshift
- std::codecvt [C++], encoding
- std::codecvt [C++], in
- std::codecvt [C++], length
- std::codecvt [C++], max_length
- std::codecvt [C++], out
- std::codecvt [C++], unshift
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
ms.openlocfilehash: 8d2970297cca199c70c101dca93f453c512317c4
ms.sourcegitcommit: b38485bb3a9d479e0c5d64ffc3d841fa2c2b366f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94441287"
---
# <a name="codecvt-class"></a>`codecvt` Sınıfı

Bir yerel ayar modeli olarak kullanılabilecek bir nesneyi açıklayan bir sınıf şablonu. Program içindeki karakterleri kodlamak için kullanılan bir değer dizisi ve program dışındaki karakterleri kodlamak için kullanılan değerler dizisi arasındaki dönüştürmeleri denetleyebilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class Byte, class StateType>
class codecvt : public locale::facet, codecvt_base;
```

### <a name="parameters"></a>Parametreler

*`CharType`*\
Bir program içindeki karakterleri kodlamak için kullanılan tür.

*`Byte`*\
Bir program dışındaki karakterleri kodlamak için kullanılan bir tür.

*`StateType`*\
Karakter temsillerinin iç ve dış türleri arasındaki bir dönüştürmenin ara durumlarını temsil etmek için kullanılan bir tür.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, türü bir değer dizisi ve türünde bir değer dizisi arasındaki dönüşümleri denetlemek için bir [yerel ayar modeli](../standard-library/locale-class.md#facet_class)olarak kullanılabilecek bir nesneyi tanımlar *`CharType`* *`Byte`* . Sınıf, *`StateType`* dönüştürme sırasında, ve sınıfının bir nesnesi *`StateType`* tüm gerekli durum bilgilerini depolar.

İç kodlama, genellikle tür veya tür olarak karakter başına sabit sayıda bayt içeren bir temsili kullanır **`char`** **`wchar_t`** .

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne, `id` ilk depolanan bir sıfır değeri içerir. Depolanan değerine erişmek için yapılan ilk girişim, içinde benzersiz bir pozitif değer depolar `id` .

Uygulamasının şablon sürümleri [`do_in`](#do_in) ve [`do_out`](#do_out) her zaman döndürülür `codecvt_base::noconv` .

C++ standart kitaplığı, çeşitli açık uzmanlık tanımlar:

```cpp
template<>
codecvt<wchar_t, char, mbstate_t>
```

**`wchar_t`** ve dizilerini dönüştürür **`char`** .

```cpp
template<>
codecvt<char16_t, char, mbstate_t>
```

**`char16_t`** UTF-16 olarak kodlanan diziler ve **`char`** UTF-8 olarak kodlanmış diziler arasında dönüştürür.

```cpp
template<>
codecvt<char32_t, char, mbstate_t>
```

UTF- **`char32_t`** 32 (UCS-4) olarak kodlanmış sıralar ve **`char`** UTF-8 olarak kodlanmış diziler arasında dönüştürür.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[`codecvt`](#codecvt)|`codecvt`Dönüştürmeleri işlemek için bir yerel ayar modeli olarak hizmet veren sınıfının nesneleri için Oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[`extern_type`](#extern_type)|Dış temsiller için kullanılan karakter türü.|
|[`intern_type`](#intern_type)|İç temsiller için kullanılan karakter türü.|
|[`state_type`](#state_type)|İç ve dış temsiller arasındaki dönüştürmeler sırasında ara durumları temsil etmek için kullanılan bir karakter türü.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[`always_noconv`](#always_noconv)|Bir dönüştürme yapılıp yapılmayacağını sınar.|
|[`do_always_noconv`](#do_always_noconv)|Hiçbir dönüştürme yapılması gerekip gerekmediğini sınamak için çağrılan bir sanal işlev.|
|[`do_encoding`](#do_encoding)|Akışın kodlanması durum bağımlıysa test eden sanal bir işlev `Byte` , `Byte` kullanılan değerler ve `CharType` üretilen değerler arasındaki oran sabittir ve bu oran değeri belirler.|
|[`do_in`](#do_in)|İç `Byte` değer dizisini dış değerler dizisine dönüştürmek için çağrılan bir sanal işlev `CharType` .|
|[`do_length`](#do_length)|`Byte`Belirli bir dış değer dizisinin kaç değerin `Byte` verilen sayıda iç değerden daha fazla olmadığını belirleyen `CharType` ve bu değer sayısını döndüren bir sanal işlev `Byte` .|
|[`do_max_length`](#do_max_length)|Bir iç oluşturmak için gereken en fazla dış bayt sayısını döndüren bir sanal işlev `CharType` .|
|[`do_out`](#do_out)|Bir iç `CharType` değer dizisini dış bayt dizisine dönüştürmek için çağrılan bir sanal işlev.|
|[`do_unshift`](#do_unshift)|Bir `Byte` değer dizisindeki son karakteri tamamlamaya yönelik duruma bağlı bir dönüşümde gereken değerleri sağlamak için adlı bir sanal işlev `Byte` .|
|[`encoding`](#encoding)|`Byte`Akış kodlamasının durum bağımlı olup olmadığını test eder, `Byte` kullanılan değerler ve `CharType` üretilen değerler arasındaki oran sabittir ve bu oran değerini belirler.|
|[`in`](#in)|Bir değer dizisinin dış temsilini `Byte` bir değer dizisinin iç gösterimine dönüştürür `CharType` .|
|[`length`](#length)|`Byte`Belirli bir dış değer dizisinin kaç değerin `Byte` verilen sayıda iç `CharType` değer olmadığını ve bu değer sayısını döndürdüğünü belirler `Byte` .|
|[`max_length`](#max_length)|`Byte`Bir iç oluşturmak için gereken en fazla dış değer sayısını döndürür `CharType` .|
|[`out`](#out)|İç `CharType` değer dizisini dış değerler dizisine dönüştürür `Byte` .|
|[`unshift`](#unshift)|`Byte`Değer dizisindeki son karakteri tamamlamaya yönelik duruma bağlı bir dönüşümde gereken dış değerleri sağlar `Byte` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**`<locale>`

**Ad alanı:**`std`

## <a name="codecvtalways_noconv"></a><a name="always_noconv"></a> `codecvt::always_noconv`

Hiçbir dönüştürmenin gerçekleştirilip oluşturulmayacağını sınar.

```cpp
bool always_noconv() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** Hiçbir dönüştürmenin yapılması gerekmiyorsa bir Boole değeri; **`false`** en az bir tane yapılması gerekir.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [`do_always_noconv`](#do_always_noconv) .

### <a name="example"></a>Örnek

```cpp
// codecvt_always_noconv.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = use_facet<codecvt<char, char, mbstate_t>>
      ( loc ).always_noconv( );

   if ( result1 )
      cout << "No conversion is needed." << '\n';
   else
      cout << "At least one conversion is required." << '\n';

   bool result2 = use_facet<codecvt<wchar_t, char, mbstate_t>>
      ( loc ).always_noconv( );

   if ( result2 )
      cout << "No conversion is needed." << '\n';
   else
      cout << "At least one conversion is required." << '\n';
}
```

```Output
No conversion is needed.
At least one conversion is required.
```

## <a name="codecvtcodecvt"></a><a name="codecvt"></a> `codecvt::codecvt`

Dönüştürmeleri işlemek için bir yerel ayar modeli olarak hizmet veren codecvt sınıfının nesneleri için Oluşturucu.

```cpp
explicit codecvt(size_t refs = 0);
```

### <a name="parameters"></a>Parametreler

*`refs`*\
Nesnenin bellek yönetimi türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Parametresi için olası değerler *`refs`* ve bunların önemi şunlardır:

- 0: nesnenin ömrü, kendisini içeren yerel ayarlara göre yönetilir.

- 1: nesnenin ömrü el ile yönetilmelidir.


- 2: Bu değerler tanımlı değil.

Oluşturucu, `locale::facet` temel nesnesini ile başlatır [`locale::facet`](../standard-library/locale-class.md#facet_class) `(refs)` .

## <a name="codecvtdo_always_noconv"></a><a name="do_always_noconv"></a> `codecvt::do_always_noconv`

Hiçbir dönüştürmenin gerçekleştirilip oluşturulmayacağını test etmek için çağrılan bir sanal işlev.

```cpp
virtual bool do_always_noconv() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Korumalı sanal üye işlevi **`true`** yalnızca, veya döndüren her çağrının sonucunu [`do_in`](#do_in) döndürür [`do_out`](#do_out) `noconv` .

Şablon sürümü her zaman döndürülür **`true`** .

### <a name="example"></a>Örnek

İçin örneğe bakın [`always_noconv`](#always_noconv) `do_always_noconv` .

## <a name="codecvtdo_encoding"></a><a name="do_encoding"></a> `codecvt::do_encoding`

Akış kodlamasının durum bağımlı olup olmadığını test eden sanal bir işlev `Byte` , `Byte` kullanılan değerler ve `CharType` üretilen değerler arasındaki oran sabittir ve ise bu oranın değerini belirler.

```cpp
virtual int do_encoding() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Korumalı sanal üye işlevi şunu döndürür:

- -1, tür dizilerinin kodlaması `extern_type` durum bağımlıdır.

- 0, kodlama değişen uzunluklardan oluşan dizileri içeriyorsa.

- *`N`* , kodlama yalnızca uzunluk dizilerini içeriyorsa *`N`*

### <a name="example"></a>Örnek

Çağıran [kodlamaya](#encoding)yönelik örneğe bakın `do_encoding` .

## <a name="codecvtdo_in"></a><a name="do_in"></a> codecvt::d o_in

Bir dış `Byte` değer dizisini iç değerler dizisine dönüştürmek için çağrılan bir sanal işlev `CharType` .

```cpp
virtual result do_in(
    StateType& state,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>Parametreler

*`state`*\
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*`first1`*\
Dönüştürülecek dizinin başlangıcına yönelik işaretçi.

*`last1`*\
Dönüştürülecek dizinin sonuna yönelik işaretçi.

*`next1`*\
Dönüştürülmüş sıranın sonunun ötesinde, ilk Dönüştürülmeyen karaktere kadar olan işaretçi.

*`first2`*\
Dönüştürülen sıranın başlangıcına yönelik işaretçi.

*`last2`*\
Dönüştürülmüş sıranın sonuna yönelik işaretçi.

*`next2`*\
`CharType`Son dönüştürüldükten sonra gelen işaretçisi, `CharType` hedef dizideki ilk değiştirilmemiş karaktere.

### <a name="return-value"></a>Dönüş Değeri

İşlemin başarısını, kısmen başarısını veya başarısızlığını gösteren bir dönüş. İşlevi şunu döndürür:

- `codecvt_base::error` kaynak sırası hatalı biçimlendirilmişse.

- `codecvt_base::noconv` işlev dönüştürme işlemi gerçekleştirmeyebilir.

- `codecvt_base::ok` dönüştürme başarılı olursa.

- `codecvt_base::partial` Kaynak yetersizse veya hedef yeterince büyük değilse dönüştürmenin başarılı olması için.

### <a name="remarks"></a>Açıklamalar

*`state`* Yeni bir kaynak dizisinin başlangıcında ilk dönüştürme durumunu temsil etmelidir. İşlevi, başarılı bir dönüştürmenin geçerli durumunu yansıtmak için, saklı değerini gereken şekilde değiştirir. Depolanan değeri aksi durumda belirtilmemiş olur.

### <a name="example"></a>Örnek

İçin örneğe bakın [`in`](#in) `do_in` .

## <a name="codecvtdo_length"></a><a name="do_length"></a> `codecvt::do_length`

`Byte`Belirli bir dış değer dizisinin kaç değerin `Byte` verilen sayıda iç değerden daha fazla olmadığını belirleyen `CharType` ve bu değer sayısını döndüren bir sanal işlev `Byte` .

```cpp
virtual int do_length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>Parametreler

*`state`*\
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*`first1`*\
Dış dizinin başlangıcına yönelik işaretçi.

*`last1`*\
Dış dizinin sonuna yönelik işaretçi.

*`len2`*\
`Byte`Üye işlevi tarafından döndürülebilecek maksimum değer sayısı.

### <a name="return-value"></a>Dönüş Değeri

[,) Konumundaki dış kaynak sırası tarafından tanımlanan, en fazla dönüştürme sayısını temsil eden, *len2* değerinden büyük bir tamsayı `first1` `last1` .

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi `do_in( state, first1, last1, next1, buf, buf + len2, next2)` , *durum* (durum kopyası), bazı arabellek ve işaretçiler için etkin bir şekilde çağırır `buf` `next1` `next2` .

Ardından döndürür `next2`  -  `buf` . Bu, [,) adresindeki kaynak sırası tarafından tanımlanan en fazla dönüştürme sayısını ( *len2* ' dan büyük değil `first1` `last1` ) sayar.

Şablon sürümü her zaman *`last1`*  -  *`first1`* ve ' nin küçük değerini döndürür *`len2`* .

### <a name="example"></a>Örnek

İçin örneğe bakın [`length`](#length) `do_length` .

## <a name="codecvtdo_max_length"></a><a name="do_max_length"></a> `codecvt::do_max_length`

`Byte`Bir iç oluşturmak için gereken en fazla dış değer sayısını döndüren bir sanal işlev `CharType` .

```cpp
virtual int do_max_length() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`Byte`Bir tane oluşturmak için gereken maksimum değer sayısı `CharType` .

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, [`do_length`](#do_length) `( first1, last1, 1)` ve ' nin rastgele geçerli değerleri için tarafından döndürülebilecek en büyük izin verilen değeri *`first1`* döndürür *`last1`* .

### <a name="example"></a>Örnek

İçin örneğe bakın [`max_length`](#max_length) `do_max_length` .

## <a name="codecvtdo_out"></a><a name="do_out"></a> `codecvt::do_out`

İç `CharType` değer dizisini dış değerler dizisine dönüştürmek için çağrılan bir sanal işlev `Byte` .

```cpp
virtual result do_out(
    StateType& state,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parametreler

*`state`*\
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*`first1`*\
Dönüştürülecek dizinin başlangıcına yönelik işaretçi.

*`last1`*\
Dönüştürülecek dizinin sonuna yönelik işaretçi.

*`next1`*\
`CharType`Son dönüştürüldükten sonra, ilk Dönüştürülmeyen bir işaretçiye yönelik başvuru `CharType` .

*`first2`*\
Dönüştürülen sıranın başlangıcına yönelik işaretçi.

*`last2`*\
Dönüştürülmüş sıranın sonuna yönelik işaretçi.

*`next2`*\
`Byte`Son dönüştürüldükten sonra, ilk Dönüştürülmeyen bir işaretçiye yönelik başvuru `Byte` .

### <a name="return-value"></a>Dönüş Değeri

İşlevi şunu döndürür:

- `codecvt_base::error` kaynak sırası hatalı biçimlendirilmişse.

- `codecvt_base::noconv` işlev dönüştürme işlemi gerçekleştirmeyebilir.

- `codecvt_base::ok` dönüştürme başarılı olursa.

- `codecvt_base::partial` Kaynak yetersizse veya hedef dönüştürmenin başarılı olması için yeterince büyük değilse.

### <a name="remarks"></a>Açıklamalar

*`state`* Yeni bir kaynak dizisinin başlangıcında ilk dönüştürme durumunu temsil etmelidir. İşlevi, başarılı bir dönüştürmenin geçerli durumunu yansıtmak için, saklı değerini gereken şekilde değiştirir. Depolanan değeri aksi durumda belirtilmemiş olur.

### <a name="example"></a>Örnek

[İçin örneğe](#out)bakın ve çağırır `do_out` .

## <a name="codecvtdo_unshift"></a><a name="do_unshift"></a> `codecvt::do_unshift`

Bir `Byte` değer dizisindeki son karakteri tamamlamaya yönelik duruma bağlı bir dönüşümde gereken değerleri sağlamak için adlı bir sanal işlev `Byte` .

```cpp
virtual result do_unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parametreler

*`state`*\
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*`first2`*\
Hedef aralıktaki ilk konuma yönelik işaretçi.

*`last2`*\
Hedef aralıktaki son konuma yönelik işaretçi.

*`next2`*\
Hedef dizideki ilk değiştirilmemiş öğenin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İşlevi şunu döndürür:

- `codecvt_base::error`*durum* , geçersiz bir durumu temsil ediyorsa

- `codecvt_base::noconv` işlev dönüştürme işlemi gerçekleştirmeyebilir

- `codecvt_base::ok` dönüştürme başarılı olursa

- `codecvt_base::partial` hedef dönüştürmenin başarılı olması için yeterince büyük değilse

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, `CharType` `first2` `last2` sonlandırma öğesi (0) dışında, kaynak öğeyi (0), [,) içinde depoladığı bir hedef diziye dönüştürmeye çalışır `Byte` . Her zaman *`next2`* hedef dizideki ilk değiştirilmemiş öğenin bir işaretçisine depolar.

*`State`* Yeni bir kaynak dizisinin başlangıcında ilk dönüştürme durumunu temsil etmelidir. İşlevi, başarılı bir dönüştürmenin geçerli durumunu yansıtmak için, saklı değerini gereken şekilde değiştirir. Genellikle, kaynak öğeyi `CharType` (0) dönüştürmek, ilk dönüştürme durumunda geçerli durumu bırakır.

### <a name="example"></a>Örnek

İçin örneğe bakın [`unshift`](#unshift) `do_unshift` .

## <a name="codecvtencoding"></a><a name="encoding"></a> `codecvt::encoding`

`Byte`Akış kodlamasının durum bağımlı olup olmadığını test eder, `Byte` kullanılan değerler ve `CharType` üretilen değerler arasındaki oran sabittir ve bu oran değerini belirler.

```cpp
int encoding() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri pozitif ise, bu değer `Byte` karakter üretmek için gereken sabit karakter sayısıdır `CharType` .

Korumalı sanal üye işlevi şunu döndürür:

- -1, tür dizilerinin kodlaması `extern_type` durum bağımlıdır.

- 0, kodlama değişen uzunluklardan oluşan dizileri içeriyorsa.

- *`N`* , kodlama yalnızca uzunluk dizilerini içeriyorsa *`N`* .

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_encoding](#do_encoding)döndürür.

### <a name="example"></a>Örnek

```cpp
// codecvt_encoding.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   int result1 = use_facet<codecvt<char, char, mbstate_t>> ( loc ).encoding ( );
   cout << result1 << '\n';
   result1 = use_facet<codecvt<wchar_t, char, mbstate_t>> ( loc ).encoding( );
   cout << result1 << '\n';
   result1 = use_facet<codecvt<char, wchar_t, mbstate_t>> ( loc ).encoding( );
   cout << result1 << '\n';
}
```

```Output
1
1
1
```

## <a name="codecvtextern_type"></a><a name="extern_type"></a> `codecvt::extern_type`

Dış temsiller için kullanılan karakter türü.

```cpp
typedef Byte extern_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `Byte` .

## <a name="codecvtin"></a><a name="in"></a> codecvt:: ın

Bir değer dizisinin dış temsilini `Byte` bir değer dizisinin iç gösterimine dönüştürür `CharType` .

```cpp
result in(
    StateType& state,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>Parametreler

*`state`*\
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*`first1`*\
Dönüştürülecek dizinin başlangıcına yönelik işaretçi.

*`last1`*\
Dönüştürülecek dizinin sonuna yönelik işaretçi.

*`next1`*\
Dönüştürülmüş sıranın sonundaki işaretçiyi, ilk Dönüştürülmeyen karaktere kadar olan işaretçi.

*`first2`*\
Dönüştürülen sıranın başlangıcına yönelik işaretçi.

*`last2`*\
Dönüştürülmüş sıranın sonuna yönelik işaretçi.

*`next2`*\
`CharType` `Chartype` Hedef dizideki ilk değiştirilmemiş karaktere son dönüştürüldükten sonra gelen işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İşlemin başarısını, kısmen başarısını veya başarısızlığını gösteren bir dönüş. İşlevi şunu döndürür:

- `codecvt_base::error` kaynak sırası hatalı biçimlendirilmişse.

- `codecvt_base::noconv` işlev dönüştürme işlemi gerçekleştirmeyebilir.

- `codecvt_base::ok` dönüştürme başarılı olursa.

- `codecvt_base::partial` Kaynak yetersizse veya hedef dönüştürmenin başarılı olması için yeterince büyük değilse.

### <a name="remarks"></a>Açıklamalar

*`state`* Yeni bir kaynak dizisinin başlangıcında ilk dönüştürme durumunu temsil etmelidir. İşlevi, başarılı bir dönüştürmenin geçerli durumunu yansıtmak için, gerektiği gibi saklı değerini değiştirir. Kısmi dönüştürmeden sonra, *`state`* yeni karakterler geldiğinde dönüştürmenin sürdürülmesine izin vermek için, bu şekilde ayarlanmalıdır.

Üye işlevi döndürür [`do_in`](#do_in) `( state, first1,  last1,  next1, first2, last2,  next2)` .

### <a name="example"></a>Örnek

```cpp
// codecvt_in.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   const char* pszExt = "This is the string to be converted!";
   wchar_t pwszInt [LEN+1];
   memset(&pwszInt[0], 0, (sizeof(wchar_t))*(LEN+1));
   const char* pszNext;
   wchar_t* pwszNext;
   mbstate_t state = {0}; // zero-initialization represents the initial conversion state for mbstate_t
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t>>
     ( loc ).in( state,
          pszExt, &pszExt[strlen(pszExt)], pszNext,
          pwszInt, &pwszInt[strlen(pszExt)], pwszNext );
   pwszInt[strlen(pszExt)] = 0;
   wcout << ( res!=codecvt_base::error ?  L"It worked! " : L"It didn't work! " )
       << L"The converted string is:\n ["
       << &pwszInt[0]
       << L"]" << '\n';
   exit(-1);
}
```

```Output
It worked! The converted string is:
[This is the string to be converted!]
```

## <a name="codecvtintern_type"></a><a name="intern_type"></a> `codecvt::intern_type`

İç temsiller için kullanılan karakter türü.

```cpp
typedef CharType intern_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `CharType` .

## <a name="codecvtlength"></a><a name="length"></a> codecvt:: length

`Byte`Belirli bir dış değer dizisinin kaç değerin `Byte` verilen sayıda iç `CharType` değer olmadığını ve bu değer sayısını döndürdüğünü belirler `Byte` .

```cpp
int length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>Parametreler

*`state`*\
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*`first1`*\
Dış dizinin başlangıcına yönelik işaretçi.

*`last1`*\
Dış dizinin sonuna yönelik işaretçi.

*`len2`*\
Üye işlevi tarafından döndürülebilecek en fazla bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

*`len2`* [,) Konumundaki dış kaynak sırası tarafından tanımlanan en fazla dönüştürme sayısının sayısını temsil eden bir tamsayı `first1` `last1` .

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [`do_length`](#do_length) `( state, first1, last1, len2)` .

### <a name="example"></a>Örnek

```cpp
// codecvt_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   const char* pszExt = "This is the string whose length is to be measured!";
   mbstate_t state = {0}; // zero-initialization represents the initial conversion state for mbstate_t
   locale loc("C"); // English_Britain"); //German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t>>
     ( loc ).length( state,
          pszExt, &pszExt[strlen(pszExt)], LEN );
   cout << "The length of the string is: ";
   wcout << res;
   cout << "." << '\n';
   exit(-1);
}
```

```Output
The length of the string is: 50.
```

## <a name="codecvtmax_length"></a><a name="max_length"></a> `codecvt::max_length`

`Byte`Bir iç oluşturmak için gereken en fazla dış değer sayısını döndürür `CharType` .

```cpp
int max_length() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`Byte`Bir tane oluşturmak için gereken maksimum değer sayısı `CharType` .

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [`do_max_length`](#do_max_length) .

### <a name="example"></a>Örnek

```cpp
// codecvt_max_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc( "C");//English_Britain" );//German_Germany
   int res = use_facet<codecvt<char, char, mbstate_t>>
     ( loc ).max_length( );
   wcout << res << '\n';
}
```

```Output
1
```

## <a name="codecvtout"></a><a name="out"></a> `codecvt::out`

İç `CharType` değer dizisini dış değerler dizisine dönüştürür `Byte` .

```cpp
result out(
    StateType& state,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parametreler

*`state`*\
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*`first1`*\
Dönüştürülecek dizinin başlangıcına yönelik işaretçi.

*`last1`*\
Dönüştürülecek dizinin sonuna yönelik işaretçi.

*`next1`*\
Son dönüştürüldükten sonra ilk Dönüştürülmeyen işaretçiye olan başvuru `CharType` `CharType` .

*`first2`*\
Dönüştürülen sıranın başlangıcına yönelik işaretçi.

*`last2`*\
Dönüştürülmüş sıranın sonuna yönelik işaretçi.

*`next2`*\
Son dönüştürüldükten sonra ilk Dönüştürülmeyen işaretçiye olan başvuru `Byte` `Byte` .

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi döndürür [`do_out`](#do_out) `( state, first1, last1, next1, first2, last2, next2)` .

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [`codecvt::do_out`](#do_out).

### <a name="example"></a>Örnek

```cpp
// codecvt_out.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
#include <wchar.h>
using namespace std;
#define LEN 90
int main( )
{
    char pszExt[LEN + 1];
    const wchar_t* pwszInt = L"This is the wchar_t string to be converted.";
    memset(&pszExt[0], 0, (sizeof(char)) * (LEN + 1));
    char* pszNext;
    const wchar_t* pwszNext;
    mbstate_t state;
    locale loc("C");//English_Britain");//German_Germany
    int res = use_facet<codecvt<wchar_t, char, mbstate_t>>
        (loc).out(state,
            pwszInt, &pwszInt[wcslen(pwszInt)], pwszNext,
            pszExt, &pszExt[wcslen(pwszInt)], pszNext);
    pszExt[wcslen(pwszInt)] = 0;
    cout << (res != codecvt_base::error ? "It worked: " : "It didn't work: ")
        << "The converted string is:\n ["
        << &pszExt[0]
        << "]" << '\n';

}
```

```Output
It worked: The converted string is:
[This is the wchar_t string to be converted.]
```

## <a name="codecvtstate_type"></a><a name="state_type"></a> `codecvt::state_type`

İç ve dış temsiller arasındaki dönüştürmeler sırasında ara durumları temsil etmek için kullanılan bir karakter türü.

```cpp
typedef StateType state_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `StateType` .

## <a name="codecvtunshift"></a><a name="unshift"></a> codecvt:: unshift

`Byte`Bir değer dizisindeki son karakteri tamamlamaya yönelik duruma bağlı bir dönüşümde gereken değerleri sağlar `Byte` .

```cpp
result unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Parametreler

*`state`*\
Üye işlevine yapılan çağrılar arasında tutulan dönüştürme durumu.

*`first2`*\
Hedef aralıktaki ilk konuma yönelik işaretçi.

*`last2`*\
Hedef aralıktaki son konuma yönelik işaretçi.

*`next2`*\
Hedef dizideki ilk değiştirilmemiş öğenin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İşlevi şunu döndürür:

- `codecvt_base::error` durum, geçersiz bir durumu temsil ediyorsa.

- `codecvt_base::noconv` işlev dönüştürme işlemi gerçekleştirmeyebilir.

- `codecvt_base::ok` dönüştürme başarılı olursa.

- `codecvt_base::partial` hedef dönüştürmenin başarılı olması için yeterince büyük değilse.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, `CharType` `first2` `last2` sonlandırma öğesi (0) dışında, kaynak öğeyi (0), [,) içinde depoladığı bir hedef diziye dönüştürmeye çalışır `Byte` . Her zaman *`next2`* hedef dizideki ilk değiştirilmemiş öğenin bir işaretçisine depolar.

*`state`* Yeni bir kaynak dizisinin başlangıcında ilk dönüştürme durumunu temsil etmelidir. İşlevi, başarılı bir dönüştürmenin geçerli durumunu yansıtmak için, gerektiği gibi saklı değerini değiştirir. Genellikle, kaynak öğeyi `CharType` (0) dönüştürmek, ilk dönüştürme durumunda geçerli durumu bırakır.

Üye işlevi döndürür [`do_unshift`](#do_unshift) `( state, first2, last2, next2 )` .

## <a name="see-also"></a>Ayrıca bkz.

[`<locale>`](../standard-library/locale.md)\
[Kod sayfaları](../c-runtime-library/code-pages.md)\
[Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
