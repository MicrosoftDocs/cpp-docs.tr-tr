---
title: 'Platform:: String sınıfı'
ms.date: 10/16/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::String::String
- VCCORLIB/Platform::String::Begin
- VCCORLIB/Platform::String::CompareOrdinal
- VCCORLIB/Platform::String::Concat
- VCCORLIB/Platform::String::Data
- VCCORLIB/Platform::String::Dispose
- VCCORLIB/Platform::String::End
- VCCORLIB/Platform::String::Equals
- VCCORLIB/Platform::String::GetHashCode
- VCCORLIB/Platform::String::IsEmpty
- VCCORLIB/Platform::String::IsFastPass
- VCCORLIB/Platform::String::Length
- VCCORLIB/Platform::String::ToString
helpviewer_keywords:
- Platform::String
ms.assetid: 72dd04a4-a694-40d3-b899-eaa0b503eab8
ms.openlocfilehash: f8b5888ee2d28a3d870b5f0eeab143b189c88180
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87185261"
---
# <a name="platformstring-class"></a>Platform:: String sınıfı

Metni göstermek için kullanılan bir dizi Unicode karakteri temsil eder. Daha fazla bilgi ve örnek için bkz. [dizeler](../cppcx/strings-c-cx.md).

## <a name="syntax"></a>Sözdizimi

```cpp
public ref class String sealed : Object,
    IDisposable,
    IEquatable,
    IPrintable
```

## <a name="iterators"></a>Yineleyiciler

Dize sınıfının üyesi olmayan iki Yineleyici işlevi, `std::for_each` bir dize nesnesindeki karakterleri numaralandırmak için şablon işleviyle birlikte kullanılabilir.

|Üye|Açıklama|
|------------|-----------------|
|`const char16* begin(String^ s)`|Belirtilen dize nesnesinin başlangıcına bir işaretçi döndürür.|
|`const char16* end(String^ s)`|Belirtilen dize nesnesinin sonundan geçmiş bir işaretçi döndürür.|

## <a name="members"></a>Üyeler

String sınıfı nesnesinden ve IDisposable, IEquatable ve ıyazdırılabilir arabirimlerinden devralır.

String sınıfı ayrıca aşağıdaki üye türlerine sahiptir.

### <a name="constructors"></a>Oluşturucular

|Üye|Açıklama|
|------------|-----------------|
|[String:: String](#ctor)|Dize sınıfının yeni bir örneğini başlatır.|

### <a name="methods"></a>Yöntemler

String sınıfı, [Platform:: Object sınıfından](../cppcx/platform-object-class.md)Equals (), Finalize (), GetHashCode (), GetType (), MemberwiseClose () ve ToString () yöntemlerini devralır. Dize aşağıdaki yöntemlere de sahiptir.

|Yöntem|Açıklama|
|------------|-----------------|
|[String:: BEGIN](#begin)|Geçerli dizenin başlangıcına bir işaretçi döndürür.|
|[String:: CompareOrdinal](#compareordinal)|`String`Nesneleri temsil eden iki dize değerlerinde karşılık gelen karakterlerin sayısal değerlerini değerlendirerek iki nesneyi karşılaştırır.|
|[String:: Concat](#concat)|İki dize nesnesinin değerlerini birleştirir.|
|[Dize: ata:D](#data)|Geçerli dizenin başlangıcına bir işaretçi döndürür.|
|[Dize::D ispozu](#dispose)|Kaynakları serbest bırakır veya yayınlar.|
|[String:: End](#end)|Geçerli dizenin sonundan geçmiş bir işaretçi döndürür.|
|[Dize:: Equals](#equals)|Belirtilen nesnenin geçerli nesneye eşit olup olmadığını gösterir.|
|[String:: GetHashCode](#gethashcode)|Bu örneğe ilişkin karma kodu döndürür.|
|[String:: IsEmpty](#isempty)|Geçerli dize nesnesinin boş olup olmadığını gösterir.|
|[String:: ısfastpass](#isfastpass)|Geçerli dize nesnesinin *Hızlı geçiş* işlemine katılılıp katılmadığını gösterir. Hızlı geçiş işleminde başvuru sayımı askıya alınır.|
|[Dize:: length](#length)|Geçerli dize nesnesinin uzunluğunu alır.|
|[String:: ToString](#tostring)|Değeri geçerli dizeyle aynı olan bir String nesnesi döndürür.|

### <a name="operators"></a>İşleçler

Dize sınıfı aşağıdaki işleçlere sahiptir.

|Üye|Açıklama|
|------------|-----------------|
|[String:: operator = = Işleci](#operator-equality)|Belirtilen iki dize nesnesinin aynı değere sahip olup olmadığını gösterir.|
|[operator + Işleci](#operator-plus)|İki dize nesnesini yeni bir String nesnesine birleştirir.|
|[String:: operator> Işleci](#operator-greater-than)|Bir dize nesnesinin değerinin ikinci bir dize nesnesinin değerinden büyük olup olmadığını gösterir.|
|[String:: operator>= Işleci](#operator-greater-than-or-equals)|Bir dize nesnesinin değerinin ikinci bir dize nesnesinin değerinden büyük veya bu değere eşit olup olmadığını gösterir.|
|[String:: operator! = Işleci](#operator-inequality)|Belirtilen iki dize nesnesinin farklı değerlere sahip olup olmadığını gösterir.|
|[String:: operator< Işleci](#operator-less-than)|Bir dize nesnesinin değerinin ikinci bir dize nesnesinin değerinden küçük olup olmadığını gösterir.|

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Header** vccorlib. h (varsayılan olarak dahil)

## <a name="stringbegin-method"></a><a name="begin"></a>String:: Begin yöntemi

Geçerli dizenin başlangıcına bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
char16* Begin();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli dizenin başlangıcına yönelik bir işaretçi.

## <a name="stringcompareordinal-method"></a><a name="compareordinal"></a>String:: CompareOrdinal yöntemi

`String`Nesneleri temsil eden iki dize değerlerinde karşılık gelen karakterlerin sayısal değerlerini değerlendirerek iki nesneyi karşılaştıran statik yöntem.

### <a name="syntax"></a>Söz dizimi

```cpp
static int CompareOrdinal( String^ str1, String^ str2 );
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk dize nesnesi.

*str2*<br/>
İkinci dize nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İki karşılaştırılan arasındaki sözcük ilişkisini gösteren bir tamsayı. Aşağıdaki tabloda olası dönüş değerleri listelenmektedir.

|Değer|Koşul|
|-----------|---------------|
|-1|`str1`küçüktür `str2` .|
|0|`str1`eşittir `str2` .|
|1|`str1`Şundan büyüktür `str2` .|

## <a name="stringconcat-method"></a><a name="concat"></a>String:: Concat yöntemi

İki dize nesnesinin değerlerini birleştirir.

### <a name="syntax"></a>Söz dizimi

```cpp
String^ Concat( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk dize nesnesi veya `null` .

*str2*<br/>
İkinci dize nesnesi veya `null` .

### <a name="return-value"></a>Dönüş Değeri

Değeri ve değerlerinin bitiştirilmesi olan yeni bir dize ^ nesnesi `str1` `str2` .

İse `str1` `null` ve ise `str2` , `str1` döndürülür. İse `str2` `null` ve ise `str1` , `str2` döndürülür. `str1` `str2` Her ikisi de varsa `null` , boş dize (L "") döndürülür.

## <a name="stringdata-method"></a><a name="data"></a>Dize::D ata yöntemi

Nesnenin veri arabelleğinin başlangıcına, C stili dizi `char16` () öğelerinden oluşan bir işaretçi döndürür **`wchar_t`** .

### <a name="syntax"></a>Sözdizimi

```cpp
const char16* Data();
```

### <a name="return-value"></a>Dönüş Değeri

Bir Unicode karakter dizisinin başlangıcına yönelik bir işaretçi `const char16` ( `char16` için bir typedef **`wchar_t`** ).

### <a name="remarks"></a>Açıklamalar

' Dan ' a dönüştürmek için bu yöntemi kullanın `Platform::String^` `wchar_t*` . `String`Nesne kapsam dışına geçtiğinde, veri işaretçisinin artık geçerli olduğu garanti edilmez. Verileri özgün nesnenin yaşam süresinden sonra depolamak için `String` , diziyi ayırmış olduğunuz belleğe kopyalamak için [wcscpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) kullanın.

## <a name="stringdispose-method"></a><a name="dispose"></a>Dize::D ispoz yöntemi

Kaynakları serbest bırakır veya yayınlar.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual override void Dispose();
```

## <a name="stringend-method"></a><a name="end"></a>String:: End yöntemi

Geçerli dizenin sonundan geçmiş bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
char16* End();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli dizenin sonunu geçen bir işaretçi.

### <a name="remarks"></a>Açıklamalar

End (), Begin () + uzunluğunu döndürür.

## <a name="stringequals-method"></a><a name="equals"></a>String:: Equals yöntemi

Belirtilen dizenin geçerli nesneyle aynı değere sahip olup olmadığını gösterir.

### <a name="syntax"></a>Söz dizimi

```cpp
bool String::Equals(Object^ str);
bool String::Equals(String^ str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*<br/>
Karşılaştırma yapılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`**`str`geçerli nesneye eşitse; Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, statik [dize:: CompareOrdinal](#compareordinal)değerine eşdeğerdir. İlk aşırı yüklemede, `str` parametrenin bir dize ^ nesnesine dönüştürülmesi beklenmektedir.

## <a name="stringgethashcode-method"></a><a name="gethashcode"></a>String:: GetHashCode yöntemi

Bu örneğe ilişkin karma kodu döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual override int GetHashCode();
```

### <a name="return-value"></a>Dönüş Değeri

Bu örneğin karma kodu.

## <a name="stringisempty-method"></a><a name="isempty"></a>String:: IsEmpty yöntemi

Geçerli dize nesnesinin boş olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool IsEmpty();
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** geçerli `String` nesne **null** veya boş dize (L "") ise; Aksi durumda, **`false`** .

## <a name="stringisfastpass-method"></a><a name="isfastpass"></a>String:: ısfastpass yöntemi

Geçerli dize nesnesinin *Hızlı geçiş* işlemine katılılıp katılmadığını gösterir. Hızlı geçiş işleminde başvuru sayımı askıya alınır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool IsFastPass();
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** geçerli `String` nesne hızlı geçse, aksi durumda, **`false`** .

### <a name="remarks"></a>Açıklamalar

Başvuru sayılı bir nesnenin parametre olduğu ve çağrılan işlev yalnızca o nesneyi okuduğu bir işleve yapılan çağrıda, derleyici başvuru sayımını güvenli bir şekilde askıya alabilir ve arama performansını iyileştirebilir. Kodunuzun bu özellikle yapabilmesini hiçbir şey değildir. Sistem tüm ayrıntıları işler.

## <a name="stringlength-method"></a><a name="length"></a>String:: length yöntemi

Geçerli nesnedeki karakterlerin sayısını alır `String` .

### <a name="syntax"></a>Sözdizimi

```cpp
unsigned int Length();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli nesnedeki karakterlerin sayısı `String` .

### <a name="remarks"></a>Açıklamalar

Karakter içermeyen bir dizenin uzunluğu sıfırdır. Aşağıdaki dizenin uzunluğu 5 ' tir:

```cpp
String^ str = "Hello";
int len = str->Length(); //len = 5
```

Dize tarafından döndürülen karakter dizisi [::D ata](#data) , Sonlandırıcı null veya ' \ 0 ' olan bir ek karakter içeriyor. Bu karakter aynı zamanda iki bayt uzunluğundadır.

## <a name="stringoperator-operator"></a><a name="operator-plus"></a>String:: operator + Işleci

İki [dize](../cppcx/platform-string-class.md) nesnesini yeni bir [String](../cppcx/platform-string-class.md) nesnesine birleştirir.

### <a name="syntax"></a>Söz dizimi

```cpp
bool String::operator+( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk `String` nesne.

*str2*<br/>
İçeriği eklenecek ikinci `String` nesne `str1` .

### <a name="return-value"></a>Dönüş Değeri

**`true`***str1* eşitse *str2*; Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu işleç `String^` , iki işlenenden verileri içeren bir nesne oluşturur. Olağanüstü performans önemli olmadığında kolaylık sağlaması için bunu kullanın. Bir işlevde "" için birkaç çağrı `+` büyük olasılıkla dikkat çekici olmaz, ancak büyük nesneleri veya metin verilerini sıkı bir döngüde işlemek istiyorsanız, standart C++ mekanizmalarını ve türlerini kullanın.

## <a name="stringoperator-operator"></a><a name="operator-equality"></a>String:: operator = = Işleci

Belirtilen iki dize nesnesinin aynı metin değerine sahip olup olmadığını gösterir.

### <a name="syntax"></a>Söz dizimi

```cpp
bool String::operator==( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
Karşılaştırılacak ilk `String` nesne.

*str2*<br/>
Karşılaştırılacak ikinci `String` nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`** içeriği `str1` öğesine eşitse `str2` ; Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu işleç [String:: CompareOrdinal](#compareordinal)değerine eşdeğerdir.

## <a name="stringoperatorgt"></a><a name="operator-greater-than"></a>String:: işleci&gt;

Bir `String` nesnenin değerinin ikinci bir nesnenin değerinden büyük olup olmadığını gösterir `String` .

### <a name="syntax"></a>Söz dizimi

```cpp
bool String::operator>( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk `String` nesne.

*str2*<br/>
İkinci `String` nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`** değeri değerinden `str1` büyükse `str2` ; Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu işleç, açıkça [dize:: CompareOrdinal](#compareordinal) ' ı çağırarak ve sıfırdan büyük bir sonuç almak için eşdeğerdir.

## <a name="stringoperatorgt"></a><a name="operator-greater-than-or-equals"></a>String:: işleci&gt;=

Bir `String` nesnenin değerinin ikinci bir nesnenin değerinden büyük veya bu değere eşit olup olmadığını gösterir `String` .

### <a name="syntax"></a>Söz dizimi

```cpp
bool String::operator>=( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk `String` nesne.

*str2*<br/>
İkinci `String` nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`** değeri `str1` değerinden büyükse veya değerine eşitse `str2` ; Aksi takdirde, **`false`** .

## <a name="stringoperator"></a><a name="operator-inequality"></a>String:: operator! =

Belirtilen iki `String` nesnenin farklı değerlere sahip olup olmadığını gösterir.

### <a name="syntax"></a>Söz dizimi

```cpp
bool String::operator!=( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
Karşılaştırılacak ilk `String` nesne.

*str2*<br/>
Karşılaştırılacak ikinci `String` nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`**`str1`değerine eşit değilse `str2` ; Aksi takdirde, **`false`** .

## <a name="stringoperatorlt"></a><a name="operator-less-than"></a>String:: işleci&lt;

Bir `String` nesnenin değerinin ikinci bir nesne değerinden küçük olup olmadığını gösterir `String` .

### <a name="syntax"></a>Söz dizimi

```cpp
bool String::operator<( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk `String` nesne.

*str2*<br/>
İkinci `String` nesne.

### <a name="return-value"></a>Dönüş Değeri

**`true`** Eğer *str1* değeri *str2*değerinden küçükse; Aksi takdirde, **`false`** .

## <a name="stringstring-constructor"></a><a name="ctor"></a>String:: String Oluşturucusu

`String`Giriş dizesi verilerinin bir kopyasıyla sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Söz dizimi

```cpp
String();
String(char16* s);
String(char16* s, unsigned int n);
```

### <a name="parameters"></a>Parametreler

*malar*<br/>
Dizeyi başlatacak bir dizi geniş karakter. Char16

*No*<br/>
Dizenin uzunluğunu belirten bir sayı.

### <a name="remarks"></a>Açıklamalar

Performans kritiktir ve kaynak dizenin ömrünü denetediyorsanız, dize yerine [Platform:: StringReference](../cppcx/platform-stringreference-class.md) kullanabilirsiniz.

### <a name="example"></a>Örnek

```cpp
String^ s = L"Hello!";
```

## <a name="stringtostring"></a><a name="tostring"></a>String:: ToString

`String`Değeri geçerli dizeyle aynı olan bir nesne döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
String^ String::ToString();
```

### <a name="return-value"></a>Dönüş Değeri

`String`Değeri geçerli dizeyle aynı olan bir nesne.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
