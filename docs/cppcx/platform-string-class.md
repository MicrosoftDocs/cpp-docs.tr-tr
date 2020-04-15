---
title: Platform::String Sınıfı
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
ms.openlocfilehash: 3f29c60d0d6a4618d97d8f750a048fcc18f976b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322121"
---
# <a name="platformstring-class"></a>Platform::String Sınıfı

Metni temsil etmek için kullanılan Sıralı Unicode karakter koleksiyonunu temsil eder. Daha fazla bilgi ve örnekler için [Strings'e](../cppcx/strings-c-cx.md)bakın.

## <a name="syntax"></a>Sözdizimi

```cpp
public ref class String sealed : Object,
    IDisposable,
    IEquatable,
    IPrintable
```

## <a name="iterators"></a>Yineleyiciler

String sınıfının üyesi olmayan iki yineleyici işlevi, String nesnesindeki `std::for_each` karakterleri numaralandırmak için şablon işleviyle birlikte kullanılabilir.

|Üye|Açıklama|
|------------|-----------------|
|`const char16* begin(String^ s)`|İşaretçiyi belirtilen String nesnesinin başına döndürür.|
|`const char16* end(String^ s)`|Belirtilen String nesnesinin sonundan geçen bir işaretçi döndürür.|

## <a name="members"></a>Üyeler

String sınıfı Object'ten ve IDisposable, IEquatable ve IPrintable arabirimlerinden devralır.

String sınıfı da aşağıdaki üye türleri vardır.

### <a name="constructors"></a>Oluşturucular

|Üye|Açıklama|
|------------|-----------------|
|[String::String](#ctor)|String sınıfının yeni bir örneğini başolarak algılar.|

### <a name="methods"></a>Yöntemler

String sınıfı Eşittir(), Finale(), GetHashCode(), GetType(), MemberwiseClose() ve ToString() yöntemlerini [Platformdan devralır::Object Class](../cppcx/platform-object-class.md). String de aşağıdaki yöntemleri vardır.

|Yöntem|Açıklama|
|------------|-----------------|
|[String::Başla](#begin)|Geçerli dize başına bir işaretçi döndürür.|
|[String::CompareOrdinal](#compareordinal)|Nesneler tarafından `String` temsil edilen iki dize değerlerinde karşılık gelen karakterlerin sayısal değerlerini değerlendirerek iki nesneyi karşılaştırır.|
|[String::Concat](#concat)|İki String nesnesinin değerlerini birleştirir.|
|[String::Data](#data)|Geçerli dize başına bir işaretçi döndürür.|
|[String::Dispose](#dispose)|Kaynakları boşaltıyor veya serbest bırakır.|
|[String::Bitiş](#end)|Geçerli dize sonundan geçen bir işaretçi döndürür.|
|[String::Eşittir](#equals)|Belirtilen nesnenin geçerli nesneye eşit olup olmadığını gösterir.|
|[String::GetHashCode](#gethashcode)|Bu örneğe ilişkin karma kodu döndürür.|
|[String::Boş](#isempty)|Geçerli String nesnesinin boş olup olmadığını gösterir.|
|[String::IsFastPass](#isfastpass)|Geçerli String nesnesinin *hızlı geçiş* işlemine katılıp katılmadığını gösterir. Hızlı geçiş işleminde, başvuru sayımı askıya alınır.|
|[String::Uzunluk](#length)|Geçerli String nesnesinin uzunluğunu alır.|
|[String::ToString](#tostring)|Değeri geçerli dizeyle aynı olan bir String nesnesini döndürür.|

### <a name="operators"></a>İşleçler

String sınıfı aşağıdaki işleçleri vardır.

|Üye|Açıklama|
|------------|-----------------|
|[String::operator== Operatör](#operator-equality)|Belirtilen iki String nesnesinin aynı değere sahip olup olmadığını gösterir.|
|[operatör+ Operatör](#operator-plus)|İki String nesnesi yeni bir String nesnesine concatenates.|
|[String::işleç> Operatörü](#operator-greater-than)|Bir String nesnesinin değerinin ikinci bir String nesnesinin değerinden büyük olup olmadığını gösterir.|
|[String::operator>= Operatör](#operator-greater-than-or-equals)|Bir String nesnesinin değerinin ikinci bir String nesnesinin değerinden büyük mü yoksa eşit mi olduğunu gösterir.|
|[String::operator!= Operatör](#operator-inequality)|Belirtilen iki String nesnenin farklı değerlere sahip olup olmadığını gösterir.|
|[String::işleç< Operatörü](#operator-less-than)|Bir String nesnesinin değerinin ikinci bir String nesnesinin değerinden küçük olup olmadığını gösterir.|

### <a name="requirements"></a>Gereksinimler

**Minimum desteklenen istemci:** Windows 8

**Minimum desteklenen sunucu:** Windows Server 2012

**Ad alanı:** Platform

**Üstbilgi** vccorlib.h (varsayılan olarak dahil)

## <a name="stringbegin-method"></a><a name="begin"></a>String::Başlat Yöntemi

Geçerli dize başına bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
char16* Begin();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli dize başına bir işaretçi.

## <a name="stringcompareordinal-method"></a><a name="compareordinal"></a>String::CompareOrdinal Yöntemi

Nesneler tarafından temsil `String` edilen iki dize değerlerinde karşılık gelen karakterlerin sayısal değerlerini değerlendirerek iki nesneyi karşılaştıran statik yöntem.

### <a name="syntax"></a>Sözdizimi

```cpp
static int CompareOrdinal( String^ str1, String^ str2 );
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk String nesnesi.

*str2*<br/>
İkinci String nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İki karşılaştırıcı arasındaki sözlü ilişkiyi gösteren bir karşısayı. Aşağıdaki tabloda olası iade değerleri listelenilmektedir.

|Değer|Koşul|
|-----------|---------------|
|-1|`str1`'den `str2`daha azdır.|
|0|`str1``str2`eşittir.|
|1|`str1`'den `str2`büyüktür.|

## <a name="stringconcat-method"></a><a name="concat"></a>String::Concat Yöntemi

İki String nesnesinin değerlerini birleştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
String^ Concat( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk String nesnesi veya `null`.

*str2*<br/>
İkinci String nesnesi veya. `null`

### <a name="return-value"></a>Dönüş Değeri

Değeri ve `str1` `str2`değerlerinin biraraya getirinimi olan yeni bir String^ nesnesi

Ise `str1` `null` ve `str2` değilse, `str1` döndürülür. Ise `str2` `null` ve `str1` değilse, `str2` döndürülür. Her `str1` `str2` ikisi `null`de varsa, boş dize (L") döndürülür.

## <a name="stringdata-method"></a><a name="data"></a>String::Data Yöntemi

( ) `char16` `wchar_t`öğelerin C stili dizi olarak nesnenin veri arabelleği başına bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
const char16* Data();
```

### <a name="return-value"></a>Dönüş Değeri

Unicode karakter `const char16` dizisinin başına bir işaretçi`char16` (için `wchar_t`bir typedef olduğunu).

### <a name="remarks"></a>Açıklamalar

'den'e `Platform::String^` dönüştürmek `wchar_t*`için bu yöntemi kullanın `String` Nesne kapsam dışına çıktığında, Veri işaretçisinin artık geçerli olacağı garanti edilemez. Verileri özgün `String` nesnenin ömrü dışında depolamak [için,](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) wcscpy_s kullanarak diziyi kendi ayırdığınız belleğe kopyalayın.

## <a name="stringdispose-method"></a><a name="dispose"></a>String::Dispose Yöntemi

Kaynakları boşaltıyor veya serbest bırakır.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual override void Dispose();
```

## <a name="stringend-method"></a><a name="end"></a>String::Bitiş Yöntemi

Geçerli dize sonundan geçen bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
char16* End();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli dize sonuna geçmek için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

End() Begin() + Uzunluk döndürür.

## <a name="stringequals-method"></a><a name="equals"></a>String::Eşittir Yöntemi

Belirtilen Dize'nin geçerli nesneyle aynı değere sahip olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool String::Equals(Object^ str);
bool String::Equals(String^ str);
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Karşılaştırma yapılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

geçerli `str` nesneye eşitse **doğru;** aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu yöntem statik [String eşdeğerdir::CompareOrdinal](#compareordinal). İlk aşırı yüklemede parametrenin `str` String^ nesnesine atılması beklenmektedir.

## <a name="stringgethashcode-method"></a><a name="gethashcode"></a>String::GetHashCode Yöntemi

Bu örneğe ilişkin karma kodu döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual override int GetHashCode();
```

### <a name="return-value"></a>Dönüş Değeri

Bu örneğin karma kodu.

## <a name="stringisempty-method"></a><a name="isempty"></a>String::Boş Yöntem

Geçerli String nesnesinin boş olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool IsEmpty();
```

### <a name="return-value"></a>Dönüş Değeri

geçerli `String` nesne **null** veya boş dize (L"") ise **doğru);** aksi takdirde, **yanlış**.

## <a name="stringisfastpass-method"></a><a name="isfastpass"></a>String::IsfastPass Yöntemi

Geçerli String nesnesinin *hızlı geçiş* işlemine katılıp katılmadığını gösterir. Hızlı geçiş işleminde, başvuru sayımı askıya alınır.

### <a name="syntax"></a>Sözdizimi

```cpp
bool IsFastPass();
```

### <a name="return-value"></a>Dönüş Değeri

geçerli `String` nesne hızlı geçmişise **doğru;** aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Başvuru sayılan nesnenin bir parametre olduğu ve çağrılan işlevin yalnızca bu nesneyi okuduğu bir işleve yapılan çağrıda derleyici, başvuru sayma performansını güvenli bir şekilde askıya alabilir ve arama performansını artırabilir. Kodunuzu bu özellik ile yapabileceği yararlı bir şey yoktur. Sistem tüm detayları işler.

## <a name="stringlength-method"></a><a name="length"></a>String::Uzunluk Yöntemi

Geçerli `String` nesnedeki karakter sayısını alır.

### <a name="syntax"></a>Sözdizimi

```cpp
unsigned int Length();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli `String` nesnedeki karakter sayısı.

### <a name="remarks"></a>Açıklamalar

Karaktersiz bir Dize'nin uzunluğu sıfırdır. Aşağıdaki dize uzunluğu 5'tir:

```cpp
String^ str = "Hello";
int len = str->Length(); //len = 5
```

[String::Data](#data) tarafından döndürülen karakter dizisi, NULL veya '\0' sonlandırma olan ek bir karaktere sahiptir. Bu karakter de iki bayt uzunluğundadır.

## <a name="stringoperator-operator"></a><a name="operator-plus"></a>String::operator+ Operatör

İki [String](../cppcx/platform-string-class.md) nesnesi yeni bir [String](../cppcx/platform-string-class.md) nesnesine concatenates.

### <a name="syntax"></a>Sözdizimi

```cpp
bool String::operator+( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk `String` nesne.

*str2*<br/>
İçeriği `String` ne eklenir `str1`ikinci nesne.

### <a name="return-value"></a>Dönüş Değeri

*str1* *str2*eşitse **doğrudur** ; aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu işleç, `String^` iki operands verileri içeren bir nesne oluşturur. Aşırı performans kritik olmadığında kolaylık sağlamak için kullanın. Bir işlevde`+`" " " için birkaç çağrı büyük olasılıkla fark edilmez, ancak büyük nesneleri veya metin verilerini sıkı bir döngü içinde manipüle ediyorsanız, standart C++ mekanizmalarını ve türlerini kullanın.

## <a name="stringoperator-operator"></a><a name="operator-equality"></a>String::operator== Operatör

Belirtilen iki String nesnesinin aynı metin değerine sahip olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool String::operator==( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
Karşılaştırılacak `String` ilk nesne.

*str2*<br/>
Karşılaştırılacak `String` ikinci nesne.

### <a name="return-value"></a>Dönüş Değeri

içeriği `str1` eşitse `str2` **doğrudur;** aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu işleç [String eşdeğerdir::CompareOrdinal](#compareordinal).

## <a name="stringoperatorgt"></a><a name="operator-greater-than"></a>String::işleç&gt;

Bir `String` nesnenin değerinin ikinci `String` bir nesnenin değerinden büyük olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool String::operator>( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk `String` nesne.

*str2*<br/>
İkinci `String` nesne.

### <a name="return-value"></a>Dönüş Değeri

değeri değerinden `str1` büyükse `str2` **doğrudur;** aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu işleç string açıkça arama [eşdeğerdir::CompareOrdinal](#compareordinal) ve sıfırdan büyük bir sonuç elde.

## <a name="stringoperatorgt"></a><a name="operator-greater-than-or-equals"></a>String::işleç&gt;=

Bir `String` nesnenin değerinin ikinci `String` bir nesnenin değerinden büyük mü yoksa eşit mi olduğunu gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool String::operator>=( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk `String` nesne.

*str2*<br/>
İkinci `String` nesne.

### <a name="return-value"></a>Dönüş Değeri

değeri daha büyük `str1` veya değerine eşit ise `str2` **doğrudur;** aksi takdirde, **yanlış**.

## <a name="stringoperator"></a><a name="operator-inequality"></a>String::operator!=

Belirtilen iki `String` nesnenin farklı değerlere sahip olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool String::operator!=( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
Karşılaştırılacak `String` ilk nesne.

*str2*<br/>
Karşılaştırılacak `String` ikinci nesne.

### <a name="return-value"></a>Dönüş Değeri

**true** eşit `str1` değilse doğru `str2`; aksi takdirde, **yanlış**.

## <a name="stringoperatorlt"></a><a name="operator-less-than"></a>String::işleç&lt;

Bir `String` nesnenin değerinin ikinci `String` bir nesnenin değerinden küçük olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool String::operator<( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk `String` nesne.

*str2*<br/>
İkinci `String` nesne.

### <a name="return-value"></a>Dönüş Değeri

*str1* değeri *str2*değerinden daha az ise **doğrudur** ; aksi takdirde, **yanlış**.

## <a name="stringstring-constructor"></a><a name="ctor"></a>String::String Constructor

Giriş dize verilerinin `String` bir kopyasıyla sınıfın yeni bir örneğini başolarak algılar.

### <a name="syntax"></a>Sözdizimi

```cpp
String();
String(char16* s);
String(char16* s, unsigned int n);
```

### <a name="parameters"></a>Parametreler

*S*<br/>
Dizeyi başharfe alan bir dizi geniş karakter. char16

*n*<br/>
Dize uzunluğunu belirten bir sayı.

### <a name="remarks"></a>Açıklamalar

Performans kritikse ve kaynak dizesinin ömrünü denetlerseniz, String yerine [Platform:StringReference'ı](../cppcx/platform-stringreference-class.md) kullanabilirsiniz.

### <a name="example"></a>Örnek

```cpp
String^ s = L"Hello!";
```

## <a name="stringtostring"></a><a name="tostring"></a>String::ToString

Değeri `String` geçerli dizeyle aynı olan bir nesneyi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
String^ String::ToString();
```

### <a name="return-value"></a>Dönüş Değeri

Değeri `String` geçerli dizeyle aynı olan bir nesne.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
