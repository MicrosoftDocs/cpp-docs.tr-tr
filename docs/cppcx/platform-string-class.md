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
ms.openlocfilehash: 3c8c179c416ca744cace26cff3def0829f425664
ms.sourcegitcommit: 8178d22701047d24f69f10d01ba37490e3d67241
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72587907"
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

Dize sınıfının üyesi olmayan iki Yineleyici işlevi, bir dize nesnesindeki karakterleri numaralandırmak için `std::for_each` şablonu işleviyle birlikte kullanılabilir.

|Üye|Açıklama|
|------------|-----------------|
|`const char16* begin(String^ s)`|Belirtilen dize nesnesinin başlangıcına bir işaretçi döndürür.|
|`const char16* end(String^ s)`|Belirtilen dize nesnesinin sonundan geçmiş bir işaretçi döndürür.|

### <a name="members"></a>Üyeler

String sınıfı nesnesinden ve IDisposable, IEquatable ve ıyazdırılabilir arabirimlerinden devralır.

String sınıfı ayrıca aşağıdaki üye türlerine sahiptir.

**Oluşturucular**

|Üye|Açıklama|
|------------|-----------------|
|[String:: String](#ctor)|Dize sınıfının yeni bir örneğini başlatır.|

**Yöntemler**

String sınıfı, [Platform:: Object sınıfından](../cppcx/platform-object-class.md)Equals (), Finalize (), GetHashCode (), GetType (), MemberwiseClose () ve ToString () yöntemlerini devralır. Dize aşağıdaki yöntemlere de sahiptir.

|Yöntem|Açıklama|
|------------|-----------------|
|[String:: BEGIN](#begin)|Geçerli dizenin başlangıcına bir işaretçi döndürür.|
|[String:: CompareOrdinal](#compareordinal)|Nesneler tarafından temsil edilen iki dize değerlerinde karşılık gelen karakterlerin sayısal değerlerini değerlendirerek iki `String` nesnesini karşılaştırır.|
|[String:: Concat](#concat)|İki dize nesnesinin değerlerini birleştirir.|
|[Dize: ata:D](#data)|Geçerli dizenin başlangıcına bir işaretçi döndürür.|
|[Dize::D ispozu](#dispose)|Kaynakları serbest bırakır veya yayınlar.|
|[String:: End](#end)|Geçerli dizenin sonundan geçmiş bir işaretçi döndürür.|
|[Dize:: Equals](#equals)|Belirtilen nesnenin geçerli nesneye eşit olup olmadığını gösterir.|
|[String:: GetHashCode](#gethashcode)|Bu örneğin karma kodunu döndürür.|
|[String:: IsEmpty](#isempty)|Geçerli dize nesnesinin boş olup olmadığını gösterir.|
|[String:: ısfastpass](#isfastpass)|Geçerli dize nesnesinin *Hızlı geçiş* işlemine katılılıp katılmadığını gösterir. Hızlı geçiş işleminde başvuru sayımı askıya alınır.|
|[Dize:: length](#length)|Geçerli dize nesnesinin uzunluğunu alır.|
|[String:: ToString](#tostring)|Değeri geçerli dizeyle aynı olan bir String nesnesi döndürür.|

**işleçler**

Dize sınıfı aşağıdaki işleçlere sahiptir.

|Üye|Açıklama|
|------------|-----------------|
|[String:: operator = = Işleci](#operator-equality)|Belirtilen iki dize nesnesinin aynı değere sahip olup olmadığını gösterir.|
|[operator + Işleci](#operator-plus)|İki dize nesnesini yeni bir String nesnesine birleştirir.|
|[String:: operator > Işleci](#operator-greater-than)|Bir dize nesnesinin değerinin ikinci bir dize nesnesinin değerinden büyük olup olmadığını gösterir.|
|[String:: operator > = Işleci](#operator-greater-than-or-equals)|Bir dize nesnesinin değerinin ikinci bir dize nesnesinin değerinden büyük veya bu değere eşit olup olmadığını gösterir.|
|[String:: operator! = Işleci](#operator-inequality)|Belirtilen iki dize nesnesinin farklı değerlere sahip olup olmadığını gösterir.|
|[String:: operator < Işleci](#operator-less-than)|Bir dize nesnesinin değerinin ikinci bir dize nesnesinin değerinden küçük olup olmadığını gösterir.|

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Header** vccorlib. h (varsayılan olarak dahil)

## <a name="begin"></a>String:: Begin yöntemi

Geçerli dizenin başlangıcına bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
char16* Begin();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli dizenin başlangıcına yönelik bir işaretçi.

## <a name="compareordinal"></a>String:: CompareOrdinal yöntemi

Nesneler tarafından temsil edilen iki dize değerlerinde karşılık gelen karakterlerin sayısal değerlerini değerlendirerek iki `String` nesnesini karşılaştıran statik yöntem.

### <a name="syntax"></a>Sözdizimi

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
|-1|`str1` `str2` küçüktür.|
|0|`str1` eşittir `str2`.|
|1\.|`str1`, `str2` daha büyük.|

## <a name="concat"></a>String:: Concat yöntemi

İki dize nesnesinin değerlerini birleştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
String^ Concat( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk dize nesnesi veya `null`.

*str2*<br/>
İkinci dize nesnesi veya `null`.

### <a name="return-value"></a>Dönüş Değeri

Değeri `str1` ve `str2` değerlerinin bitiştirilmesi olan yeni bir dize ^ nesnesi.

@No__t_0 `null` ve `str2` yoksa, `str1` döndürülür. @No__t_0 `null` ve `str1` yoksa, `str2` döndürülür. @No__t_0 ve `str2` her ikisi de `null` ise boş dize (L "") döndürülür.

## <a name="data"></a>Dize::D ata yöntemi

Nesnenin veri arabelleğinin başlangıcına, `char16` (`wchar_t`) öğelerinin C stili dizisi olarak bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```
const char16* Data();
```

### <a name="return-value"></a>Dönüş Değeri

@No__t_0 bir Unicode karakter dizisinin başına işaretçisi (`char16` `wchar_t` için bir typedef 'dir).

### <a name="remarks"></a>Açıklamalar

@No__t_0 ' den `wchar_t*` dönüştürmek için bu yöntemi kullanın. @No__t_0 nesnesi kapsam dışına geçtiğinde, veri işaretçisinin artık geçerli olduğu garanti edilmez. Verileri özgün `String` nesnesinin yaşam süresinden daha fazla saklamak için, diziyi, kendi ayırmış olduğunuz belleğe kopyalamak için [wcscpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) kullanın.

## <a name="dispose"></a>Dize::D ispoz yöntemi

Kaynakları serbest bırakır veya yayınlar.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual override void Dispose();
```

## <a name="end"></a>String:: End yöntemi

Geçerli dizenin sonundan geçmiş bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
char16* End();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli dizenin sonunu geçen bir işaretçi.

### <a name="remarks"></a>Açıklamalar

End (), Begin () + uzunluğunu döndürür.

## <a name="equals"></a>String:: Equals yöntemi

Belirtilen dizenin geçerli nesneyle aynı değere sahip olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool String::Equals(Object^ str);
bool String::Equals(String^ str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*<br/>
Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

`str` geçerli nesneye eşitse **true** ; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, statik [dize:: CompareOrdinal](#compareordinal)değerine eşdeğerdir. İlk aşırı yüklemede, `str` parametresinin bir dize ^ nesnesine dönüştürülmesi beklenmektedir.

## <a name="gethashcode"></a>String:: GetHashCode yöntemi

Bu örneğin karma kodunu döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual override int GetHashCode();
```

### <a name="return-value"></a>Dönüş Değeri

Bu örneğin karma kodu.

## <a name="isempty"></a>String:: IsEmpty yöntemi

Geçerli dize nesnesinin boş olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool IsEmpty();
```

### <a name="return-value"></a>Dönüş Değeri

geçerli `String` nesnesi **null** ya da boş dize (L "") ise **true** ; Aksi takdirde, **false**.

## <a name="isfastpass"></a>String:: ısfastpass yöntemi

Geçerli dize nesnesinin *Hızlı geçiş* işlemine katılılıp katılmadığını gösterir. Hızlı geçiş işleminde başvuru sayımı askıya alınır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool IsFastPass();
```

### <a name="return-value"></a>Dönüş Değeri

geçerli `String` nesnesi hızlı bir şekilde geçse **doğru** ; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Başvuru sayılı bir nesnenin parametre olduğu ve çağrılan işlev yalnızca o nesneyi okuduğu bir işleve yapılan çağrıda, derleyici başvuru sayımını güvenli bir şekilde askıya alabilir ve arama performansını iyileştirebilir. Kodunuzun bu özellikle yapabilmesini hiçbir şey değildir. Sistem tüm ayrıntıları işler.

## <a name="length"></a>String:: length yöntemi

Geçerli `String` nesnesindeki karakterlerin sayısını alır.

### <a name="syntax"></a>Sözdizimi

```cpp
unsigned int Length();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli `String` nesnesindeki karakterlerin sayısı.

### <a name="remarks"></a>Açıklamalar

Karakter içermeyen bir dizenin uzunluğu sıfırdır. Aşağıdaki dizenin uzunluğu 5 ' tir:

```cpp
String^ str = "Hello";
int len = str->Length(); //len = 5
```

Dize tarafından döndürülen karakter dizisi [::D ata](#data) , Sonlandırıcı null veya ' \ 0 ' olan bir ek karakter içeriyor. Bu karakter aynı zamanda iki bayt uzunluğundadır.

## <a name="operator-plus"></a>String:: operator + Işleci

İki [dize](../cppcx/platform-string-class.md) nesnesini yeni bir [String](../cppcx/platform-string-class.md) nesnesine birleştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool String::operator+( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk `String` nesnesi.

*str2*<br/>
İçeriği `str1` eklenecek ikinci `String` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

*str1* eşitse **true** , *str2*; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Bu işleç, iki işlenenden verileri içeren bir `String^` nesnesi oluşturur. Olağanüstü performans önemli olmadığında kolaylık sağlaması için bunu kullanın. Bir işlevde "`+`" için birkaç çağrı büyük olasılıkla dikkat çekici olmaz, ancak büyük nesneleri veya metin verilerini sıkı bir döngüde işlemek istiyorsanız, standart C++ mekanizmaları ve türleri kullanın.

##  <a name="operator-equality"></a>String:: operator = = Işleci

Belirtilen iki dize nesnesinin aynı metin değerine sahip olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool String::operator==( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
Karşılaştırılacak ilk `String` nesnesi.

*str2*<br/>
Karşılaştırılacak ikinci `String` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`str1` içeriği `str2` eşitse **true** ; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Bu işleç [String:: CompareOrdinal](#compareordinal)değerine eşdeğerdir.

##  <a name="operator-greater-than"></a>String:: operator &gt;

Bir `String` nesnesinin değerinin ikinci bir `String` nesnesinin değerinden büyük olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool String::operator>( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk `String` nesnesi.

*str2*<br/>
İkinci `String` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`str1` değeri `str2` değerinden büyükse **true** ; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Bu işleç, açıkça [dize:: CompareOrdinal](#compareordinal) ' ı çağırarak ve sıfırdan büyük bir sonuç almak için eşdeğerdir.

## <a name="operator-greater-than-or-equals"></a>String:: operator &gt; =

Bir `String` nesnesinin değerinin ikinci bir `String` nesnesinin değerinden büyük veya bu değere eşit olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool String::operator>=( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk `String` nesnesi.

*str2*<br/>
İkinci `String` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`str1` değeri `str2` değerinden büyük veya bu değere eşitse **true** ; Aksi takdirde, **false**.

## <a name="operator-inequality"></a>String:: operator! =

Belirtilen iki `String` nesnesinin farklı değerlere sahip olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool String::operator!=( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
Karşılaştırılacak ilk `String` nesnesi.

*str2*<br/>
Karşılaştırılacak ikinci `String` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`str1` `str2` eşit değilse **true** ; Aksi takdirde, **false**.

## <a name="operator-less-than"></a>String:: operator &lt;

Bir `String` nesnesinin değerinin ikinci bir `String` nesnesinin değerinden küçük olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool String::operator<( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk `String` nesnesi.

*str2*<br/>
İkinci `String` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

*str1* değeri *str2*değerinden küçükse **true** değeri; Aksi takdirde, **false**.

## <a name="ctor"></a>String:: String Oluşturucusu

Giriş dizesi verilerinin kopyasıyla `String` sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

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

## <a name="tostring"></a>String:: ToString

Değeri geçerli dizeyle aynı olan bir `String` nesnesi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
String^ String::ToString();
```

### <a name="return-value"></a>Dönüş Değeri

Değeri geçerli dizeyle aynı olan `String` nesne.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
