---
title: Platform::String sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- Platform::String
ms.assetid: 72dd04a4-a694-40d3-b899-eaa0b503eab8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d9c68bde9fdd49e4007b8b6e1d92899d71dde4e
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162548"
---
# <a name="platformstring-class"></a>Platform::String sınıfı

Metin temsil etmek için kullanılan bir sıralı Unicode karakterler koleksiyonunu temsil eder. Daha fazla bilgi ve örnekler için bkz. [dizeleri](../cppcx/strings-c-cx.md).

## <a name="syntax"></a>Sözdizimi

```cpp
public ref class String sealed : Object,
    IDisposable,
    IEquatable,
    IPrintable
```

## <a name="iterators"></a>Yineleyiciler

Dize sınıfı üyesi olmayan iki yineleyici işlevleri ile kullanılabilir `std::for_each` şablon işlevi bir dize nesnesi karakterleri numaralandırılamadı.

|Üye|Açıklama|
|------------|-----------------|
|`const char16* begin(String^ s)`|Belirtilen dize nesnesi başlangıcına bir işaretçi döndürür.|
|`const char16* end(String^ s)`|Belirtilen dize nesnesi sonunu geçen bir işaretçi döndürür.|

### <a name="members"></a>Üyeler

Dize sınıfı, nesne ve IDisposable IEquatable ve IPrintable arabirimleri devralır.

Dize sınıfı, ayrıca aşağıdaki üye türlerinden sahiptir.

**Oluşturucular**

|Üye|Açıklama|
|------------|-----------------|
|[String::String](#ctor)|Dize sınıfının yeni bir örneğini başlatır.|

**Yöntemler**

Dize sınıfı ' lerin üzerine yaz, Finalize() ifadesini, GetHashCode(), GetType(), MemberwiseClose() ve ToString() yöntemler öğesinden devralan [Platform::Object sınıfı](../cppcx/platform-object-class.md). Dize, aşağıdaki yöntemleri de vardır.

|Yöntem|Açıklama|
|------------|-----------------|
|[String::Begin](#begin)|Geçerli dizenin başlangıcına bir işaretçi döndürür.|
|[String::CompareOrdinal](#compareordinal)|İki karşılaştırır `String` karşılık gelen karakterler nesneleri tarafından temsil edilen iki dize değerleri, sayısal değerler değerlendirme nesneleri.|
|[String::concat](#concat)|İki dize nesnelerinin değerleri birleştirir.|
|[String::Data](#data)|Geçerli dizenin başlangıcına bir işaretçi döndürür.|
|[String::Dispose](#dispose)|Serbest bırakma veya kaynakları serbest bırakır.|
|[String::End](#end)|Geçerli dizenin sonunu geçen bir işaretçi döndürür.|
|[String::Equals](#equals)|Belirtilen nesne geçerli nesneye eşit olup olmadığını gösterir.|
|[String::GetHashCode](#gethashcode)|Bu örneğin karma kodunu döndürür.|
|[String::IsEmpty](#isempty)|Geçerli bir dize nesnesi boş olup olmadığını belirtir.|
|[String::IsFastPass](#isfastpass)|Geçerli dize nesnenin katıldığı olup olmadığını gösteren bir *hızlı geçişi* işlemi. İşlem hızlı geçmek için başvuru sayımı askıya alındı.|
|[String::length](#length)|Geçerli nesnenin dize uzunluğunu alır.|
|[String::toString](#tostring)|Geçerli dize ile aynı değeri olan bir dize nesnesi döndürür.|

**İşleçler**

Dize sınıfı, aşağıdaki işleçleri sahiptir.

|Üye|Açıklama|
|------------|-----------------|
|[String::operator == işleci](#operator-equality)|İki belirtilen dize nesnesinin aynı değere sahip olup olmadığını gösterir.|
|[operator + işleci](#operator-plus)|İki dize nesnesi yeni bir dize nesnesi art arda ekler.|
|[String::operator > işleci](#operator-greater-than)|Değer bir dize nesnesinin ikinci bir değerden büyük olup olmadığını belirtir dize nesnesi.|
|[String::operator > = işleci](#operator-greater-than-or-equals)|Bir dize nesnesi değerini saniyenin değerine eşit veya daha büyük olup olmadığını belirten dize nesnesi.|
|[String::operator! = işleci](#operator-inequality)|Belirtilen dize nesnelerinin iki farklı değerlere sahip olup olmadığını gösterir.|
|[String::operator < işleci](#operator-less-than)|Bir dize nesnesi değerini saniyenin değerinden daha küçük olup olmadığını belirten dize nesnesi.|

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Sunucu desteklenen en düşük:** Windows Server 2012

**Namespace:** platformu

**Üst bilgi** vccorlib.h (varsayılan olarak dahil)

## <a name="begin"></a>  String::Begin yöntemi

Geçerli dizenin başlangıcına bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
char16* Begin();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli dizenin başlangıç işaretçisi.

## <a name="compareordinal"></a>  String::CompareOrdinal yöntemi

İki karşılaştırır `String` karşılık gelen karakterler nesneleri tarafından temsil edilen iki dize değerleri, sayısal değerler değerlendirme nesneleri.

### <a name="syntax"></a>Sözdizimi

```cpp
int CompareOrdinal( String^ str1, String^ str2 );
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk dize nesnesi.

*str2*<br/>
İkinci dize nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan iki öğe arasındaki sözlü ilişkiyi gösteren bir tamsayı. Aşağıdaki tabloda olası dönüş değerleri listelenmektedir.

|Değer|Koşul|
|-----------|---------------|
|-1|`str1` olan küçüktür `str2`.|
|0|`str1` eşittir `str2`.|
|1.|`str1` büyüktür `str2`.|

## <a name="concat"></a>  String::concat yöntemi

İki dize nesnelerinin değerleri birleştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
String^ Concat( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk dize nesnesinin veya `null`.

*str2*<br/>
İkinci dize nesnesi veya `null`.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir dize ^ nesne değeri olan değerleri birleşimi, `str1` ve `str2`.

Varsa `str1` olduğu `null` ve `str2` değil, `str1` döndürülür. Varsa `str2` olduğu `null` ve `str1` değil, `str2` döndürülür. Varsa `str1` ve `str2` her ikisi de `null`, boş bir dize ("M") döndürülür.

## <a name="data"></a>  String::Data yöntemi

Nesnenin veri arabelleği başlangıcına bir C tarzı dizi olarak bir işaretçi döndürür `char16` (`wchar_t`) öğeleri.

### <a name="syntax"></a>Sözdizimi

```
const char16* Data();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi başlangıcına bir `const char16` Unicode karakterler dizisi (`char16` için bir TypeDef `wchar_t`).

### <a name="remarks"></a>Açıklamalar

Dönüştürmek için bu yöntemi kullanmak `Platform::String^` için `wchar_t*`. Zaman `String` nesne kapsam dışına gider, veri işaretçisine artık geçerli olması sağlanır. Özgün ömrünü aşan veri depolamak için `String` nesnesi [wcscpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) kendiniz ayrılan belleğe dizisine kopyalamak için.

## <a name="dispose"></a>  String::Dispose yöntemi

Serbest bırakma veya kaynakları serbest bırakır.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual override void Dispose();
```

## <a name="end"></a>  String::End yöntemi

Geçerli dizenin sonunu geçen bir işaretçi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
char16* End();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli dizenin sonunu geçen bir işaretçi.

### <a name="remarks"></a>Açıklamalar

End() Begin() + uzunluğunu döndürür.

## <a name="equals"></a>  String::Equals yöntemi

Belirtilen dize geçerli nesnenin aynı değere sahip olup olmadığını belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool String::Equals(Object^ str);
bool String::Equals(String^ str);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Karşılaştırma yapılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `str` geçerli nesneye eşitse; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Bu yöntem eşdeğerdir [String::CompareOrdinal](#compareordinal). İlk aşırı yükleme bekleniyor `str` parametreyi bir dizeye dönüştürülür ^ nesne.

## <a name="gethashcode"></a>  String::GetHashCode Yöntemi

Bu örneğin karma kodunu döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual override int GetHashCode();
```

### <a name="return-value"></a>Dönüş Değeri

Bu örneğin karma kodu.

## <a name="isempty"></a>  String::IsEmpty yöntemi

Geçerli bir dize nesnesi boş olup olmadığını belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool IsEmpty();
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa geçerli `String` nesnedir **null** ya da boş dize (L""); Aksi takdirde **false**.

## <a name="isfastpass"></a>  String::IsFastPass yöntemi

Geçerli dize nesnenin katıldığı olup olmadığını gösteren bir *hızlı geçişi* işlemi. İşlem hızlı geçmek için başvuru sayımı askıya alındı.

### <a name="syntax"></a>Sözdizimi

```cpp
bool IsFastPass();
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa geçerli `String` nesnedir hızlı geçmiş; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Burada bir başvurusu sayılan nesne bir parametredir ve çağrılan işlev bu nesne yalnızca okur. bir işlev çağrısı içinde derleyicinin güvenli bir şekilde başvuru sayımı askıya alıp Arama performansını. Kodunuzu bu özellik ile yapmak için faydalı bir şey yoktur. Sistem, tüm ayrıntılarını işler.

## <a name="length"></a>  String::length yöntemi

Geçerli karakter sayısını alır. `String` nesne.

### <a name="syntax"></a>Sözdizimi

```cpp
unsigned int Length();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli karakter sayısı `String` nesne.

### <a name="remarks"></a>Açıklamalar

Hiçbir karakter içeren bir dize uzunluğu sıfır olur. Aşağıdaki dizenin uzunluğu 5 şöyledir:

```cpp
String^ str = "Hello";
int len = str->Length(); //len = 5
```

Tarafından döndürülen karakter dizisi [String::Data](#data) Sonlandırıcı NULL ya da '\0' bir ek karakter içeriyor. Bu da iki bayt uzunluğundadır karakterdir.

## <a name="operator-plus"></a>  String::operator + işleci

İki art arda ekler [dize](../cppcx/platform-string-class.md) yeni nesneleri [dize](../cppcx/platform-string-class.md) nesne.

### <a name="syntax"></a>Sözdizimi

```cpp
bool String::operator+( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk `String` nesne.

*str2*<br/>
İkinci `String` nesnenin içeriği için eklenir, `str1`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *str1* eşittir *str2*; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Bu işleç oluşturur bir `String^` iki işlenen verileri içeren nesne. Yüksek performans kritik olmadığı durumlarda kolaylık olması için kullanın. Birkaç çağrısına "`+`" bir işlevde belirgin olur olmayabilir ancak sıkı bir döngüde metin verilerini veya büyük nesneler düzenleme, standart C++ mekanizmalar ve türleri kullanın.

##  <a name="operator-equality"></a> String::operator == işleci

Belirtilen iki dize nesnesi aynı değeri içerip içermediğini belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool String::operator==( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk `String` Karşılaştırılacak nesne.

*str2*<br/>
İkinci `String` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** , içeriğini `str1` eşit olan `str2`; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Bu işleç eşdeğerdir [String::CompareOrdinal](#compareordinal).

##  <a name="operator-greater-than"></a>  String::operator&gt;

Belirtir olup olmadığını bir değeri `String` nesnedir ikinci değerinden `String` nesne.

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

**doğru** varsa değerini `str1` değerinden büyükse `str2`; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Bu işleç, açıkça çağırmak için eşdeğerdir [String::CompareOrdinal](#compareordinal) ve bir sonuç sıfırdan büyük alma.

## <a name="operator-greater-than-or-equals"></a> String::operator&gt;=

Belirtir olup olmadığını bir değeri `String` nesnedir büyüktür veya eşittir ikinci değerine `String` nesne.

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

**doğru** varsa değerini `str1` değerine eşit veya değerinden `str2`; Aksi takdirde **false**.

## <a name="operator-inequality"></a> String::operator! =

Gösteren iki olup belirtilen `String` nesneleri farklı değerlere sahip.

### <a name="syntax"></a>Sözdizimi

```cpp
bool String::operator!=( String^ str1, String^ str2);
```

### <a name="parameters"></a>Parametreler

*str1*<br/>
İlk `String` Karşılaştırılacak nesne.

*str2*<br/>
İkinci `String` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa `str1` eşit değildir `str2`; Aksi takdirde **false**.

## <a name="operator-less-than"></a> String::operator&lt;

Belirtir olup olmadığını bir değeri `String` nesnesinin ikinci bir değeri azdır `String` nesne.

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

**doğru** varsa değerini *str1* değerini'dan küçük *str2*; Aksi takdirde **false**.

## <a name="ctor"></a> String::String Oluşturucusu

Yeni bir örneğini başlatır `String` kopyasını sınıfıyla giriş dizesi verileri.

### <a name="syntax"></a>Sözdizimi

```cpp
String();
String(char16* s);
String(char16* s, unsigned int n);
```

### <a name="parameters"></a>Parametreler

*s*<br/>
Bir dizeyi başlatmak geniş karakter dizisi. char16

*n*<br/>
Dizenin uzunluğunu belirten bir sayı.

### <a name="remarks"></a>Açıklamalar

Performans kritik ise ve kaynak dizesi ömrünü denetlemek, kullanabileceğiniz [Platform::StringReference](../cppcx/platform-stringreference-class.md) yerine dize.
### <a name="example"></a>Örnek

```cpp
String^ s = L"Hello!";
```

## <a name="tostring"></a> String::toString

Döndürür bir `String` değeri geçerli bir dize ile aynı olan nesne.

### <a name="syntax"></a>Sözdizimi

```cpp
String^ String::ToString();
```

### <a name="return-value"></a>Dönüş Değeri

A `String` değeri geçerli bir dize ile aynı olan nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)