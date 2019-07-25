---
title: path Sınıfı
ms.date: 09/27/2018
f1_keywords:
- filesystem/std::experimental::filesystem::path
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
ms.openlocfilehash: 10c865aa2bc2431850c69e9dfedbef37414b2cb9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455092"
---
# <a name="path-class"></a>path Sınıfı

**Path** sınıfı, bir yol adı olarak kullanım `string_type`için uygun `myname` şekilde, burada çağrılan,,, bir nesne türü içerir. `string_type`, için `basic_string<value_type>`bir eş anlamlı ' `value_type` dir; burada, Windows üzerinde **wchar_t** veya POSIX üzerinde **char** .

Daha fazla bilgi ve kod örnekleri için bkz. [dosya sistemi Gezintisi (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class path;
```

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Yolu](#path)|Bir `path`oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[const_iterator](#const_iterator)|İçin `iterator`bir eş anlamlı.|
|[iden](#iterator)|`path`Bileşenleriniatayan çift yönlü bir sabit Yineleyici. `myname`|
|[string_type](#string_type)|Tür için `basic_string<value_type>`bir eş anlamlı.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[ýna](#append)|Gerektiğinde belirtilen diziyi `mypath`ekler, dönüştürülür ve preferred_separator eklemek.|
|[ata](#assign)|Gerektiğinde `mypath` , belirtilen sırayla değiştirilir.|
|[başladı](#begin)|Varsa, `path::iterator` PathName içindeki ilk yol öğesini bir belirleme döndürür.|
|[c_str](#c_str)|İçindeki `mypath`ilk karaktere bir işaretçi döndürür.|
|[lediğiniz](#clear)|Yürütülür `mypath.clear()`.|
|[Karşılaştır](#compare)|Karşılaştırma değerlerini döndürür.|
|[concat](#compare)|Gerektiğinde `mypath`, dönüştürülmüş (ayırıcı eklemek değil) belirtilen diziyi ekler.|
|[empty](#empty)|Döndürür `mypath.empty()`.|
|[erer](#end)|Türünde `iterator`bir dizi sonu yineleyiciyi döndürür.|
|[uzantının](#extension)|Sonekini `filename()`döndürür.|
|[kısaltın](#filename)|Özel olarak `empty() path() : *--end()`myname kök dizin bileşenini döndürür. Bileşen boş olabilir.|
|[generic_string](#generic_string)|İle `this->string<Elem, Traits, Alloc>(al)` (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.|
|[generic_u16string](#generic_u16string)|İle `u16string()` (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.|
|[generic_u32string](#generic_u32string)|İle `u32string()` (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.|
|[generic_u8string](#generic_u8string)|İle `u8string()` (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.|
|[generic_wstring](#generic_wstring)|İle `wstring()` (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.|
|[has_extension](#has_extension)|Döndürür `!extension().empty()`.|
|[has_filename](#has_filename)|Döndürür `!filename().empty()`.|
|[has_parent_path](#has_parent_path)|Döndürür `!parent_path().empty()`.|
|[has_relative_path](#has_relative_path)|Döndürür `!relative_path().empty()`.|
|[has_root_directory](#has_root_directory)|Döndürür `!root_directory().empty()`.|
|[has_root_name](#has_root_name)|Döndürür `!root_name().empty()`.|
|[has_root_path](#has_root_path)|Döndürür `!root_path().empty()`.|
|[has_stem](#has_stem)|Döndürür `!stem().empty()`.|
|[is_absolute](#is_absolute)|Windows için işlev döndürür `has_root_name() && has_root_directory()`. POSIX için, işlev döndürür `has_root_directory()`.|
|[is_relative](#is_relative)|Döndürür `!is_absolute()`.|
|[make_preferred](#make_preferred)|Her ayırıcıyı gerektiğinde bir preferred_separator dönüştürür.|
|[Yerel](#native)|Döndürür `myname`.|
|[parent_path](#parent_path)|Öğesinin `myname`üst yol bileşenini döndürür.|
|[preferred_separator](#preferred_separator)|Sabit nesne, ana bilgisayar işletim sistemine bağlı olarak yol bileşenlerini ayırmak için tercih edilen karakteri verir. |
|[relative_path](#relative_path)|Göreli yol bileşenini `myname`döndürür. |
|[remove_filename](#remove_filename)|Dosya adını kaldırır.|
|[replace_extension](#replace_extension)|Uzantısının yerini alır `myname`. |
|[replace_filename](#replace_filename)|RBu dosya adını alır.|
|[root_directory](#root_directory)|Kök dizin bileşenini `myname`döndürür. |
|[root_name](#root_name)|Kök adı bileşenini `myname`döndürür. |
|[root_path](#root_path)|Kök yolu bileşenini `myname`döndürür.|
|[stem](#stem)|`stem` Bileşenini`myname`döndürür.|
|[string](#string)|İçinde `mypath`depolanan sırayı dönüştürür.|
|[Kur](#swap)|Yürütülür `swap(mypath, right.mypath)`.|
|[u16string](#u16string)|İçinde `mypath` depolanan diziyi UTF-16 ' a dönüştürür ve türündeki `u16string`bir nesne içinde depolanmış şekilde döndürür.|
|[u32string](#u32string)|İçinde `mypath` depolanan diziyi UTF-32 ' a dönüştürür ve türündeki `u32string`bir nesne içinde depolanmış şekilde döndürür.|
|[u8string](#u8string)|İçinde `mypath` depolanan diziyi UTF-8 ' e dönüştürür ve türünde `u8string`bir nesne içinde depolanmış şekilde döndürür.|
|[value_type](#value_type)|Bu tür, ana bilgisayar işletim sistemi tarafından sık kırmızı yol öğelerini tanımlar.|
|[wstring](#wstring)|İçinde `mypath` depolanan sırayı, ana bilgisayar sistemi tarafından bir `wchar_t` sıra için sık kırmızı kodlamaya dönüştürür ve türündeki `wstring`bir nesneye depolanmış şekilde döndürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_as)|Yolun öğelerini başka bir yolun kopyasıyla değiştirir.|
|[operator+=](#op_add)|Çeşitli `concat` ifadeler.|
|[işleç/=](#op_divide)|Çeşitli `append` ifadeler.|
|[string_type işleci](#op_string)|Döndürür `myname`.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<dosya sistemi >

**Ad alanı:** std:: deneysel:: FileSystem

## <a name="append"></a>path:: Append

Belirtilen diziyi `mypath`, dönüştürülecek ve `preferred_separator` gereken şekilde sonuna ekler.

```cpp
template <class Source>
path& append(const Source& source);

template <class InIt>
path& append(InIt first, InIt last);
```

### <a name="parameters"></a>Parametreler

*kaynaktaki*\
Belirtilen sıra.

*adı*\
Belirtilen dizinin başlangıcı.

*soyadına*\
Belirtilen dizinin sonu.

## <a name="assign"></a>path:: Assign

Gerektiğinde `mypath` , belirtilen sırayla değiştirilir.

```cpp
template <class Source>
path& assign(const Source& source);

template <class InIt>
path& assign(InIt first, InIt last);
```

### <a name="parameters"></a>Parametreler

*kaynaktaki*\
Belirtilen sıra.

*adı*\
Belirtilen dizinin başlangıcı.

*soyadına*\
Belirtilen dizinin sonu.

## <a name="begin"></a>path:: Begin

Varsa, `path::iterator` PathName içindeki ilk yol öğesini bir belirleme döndürür.

```cpp
iterator begin() const;
```

## <a name="c_str"></a>yol:: c_str

İçindeki `mypath`ilk karaktere bir işaretçi döndürür.

```cpp
const value_type& *c_str() const noexcept;
```

## <a name="clear"></a>path:: Clear

Yürütülür `mypath.clear()`.

```cpp
void clear() noexcept;
```

## <a name="compare"></a>path:: Compare

İlk işlev döndürür `mypath.compare(pval.native())`. İkinci işlev döndürür `mypath.compare(str)`. Üçüncü işlev döndürür `mypath.compare(ptr)`.

```cpp
int compare(const path& pval) const noexcept;
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>Parametreler

*Pval*\
Karşılaştırılacak yol.

*üstbilgisine*\
Karşılaştırılacak dize.

*kaydetmeye*\
Karşılaştırılacak işaretçi.

## <a name="concat"></a>path:: Concat

Gerektiğinde `mypath`, dönüştürülmüş (ayırıcı eklemek değil) belirtilen diziyi ekler.

```cpp
template <class Source>
path& concat(const Source& source);

template <class InIt>
path& concat(InIt first, InIt last);
```

### <a name="parameters"></a>Parametreler

*kaynaktaki*\
Belirtilen sıra.

*adı*\
Belirtilen dizinin başlangıcı.

*soyadına*\
Belirtilen dizinin sonu.

## <a name="const_iterator"></a>yol:: const_iterator

İçin `iterator`bir eş anlamlı.

```cpp
typedef iterator const_iterator;
```

## <a name="empty"></a>path:: Empty

Döndürür `mypath.empty()`.

```cpp
bool empty() const noexcept;
```

## <a name="end"></a>path:: End

Türünde `iterator`bir dizi sonu yineleyiciyi döndürür.

```cpp
iterator end() const;
```

## <a name="extension"></a>path:: Extension

Sonekini `filename()`döndürür.

```cpp
path extension() const;
```

### <a name="remarks"></a>Açıklamalar

Şu şekilde sonek `filename() X` döndürür:

`X == path(".") || X == path("..")` Yadanokta`X` içermiyorsa, sonek boştur.

Aksi takdirde, sonek en sağdaki noktayı (ve içerir) ile başlar.

## <a name="filename"></a>yol:: filename

Özel olarak `empty() path() : *--end()`myname kök dizin bileşenini döndürür. Bileşen boş olabilir.

```cpp
path filename() const;
```

## <a name="generic_string"></a>yol:: generic_string

İle `this->string<Elem, Traits, Alloc>(al)` (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

## <a name="generic_u16string"></a>yol:: generic_u16string

İle `u16string()` (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.

```cpp
u16string generic_u16string() const;
```

## <a name="generic_u32string"></a>yol:: generic_u32string

İle `u32string()` (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.

```cpp
u32string generic_u32string() const;
```

## <a name="generic_u8string"></a>yol:: generic_u8string

İle `u8string()` (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.

```cpp
string generic_u8string() const;
```

## <a name="generic_wstring"></a>yol:: generic_wstring

İle `wstring()` (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.

```cpp
wstring generic_wstring() const;
```

## <a name="has_extension"></a>yol:: has_extension

Döndürür `!extension().empty()`.

```cpp
bool has_extension() const;
```

## <a name="has_filename"></a>yol:: has_filename

Döndürür `!filename().empty()`.

```cpp
bool has_filename() const;
```

## <a name="has_parent_path"></a>yol:: has_parent_path

Döndürür `!parent_path().empty()`.

```cpp
bool has_parent_path() const;
```

## <a name="has_relative_path"></a>yol:: has_relative_path

Döndürür `!relative_path().empty()`.

```cpp
bool has_relative_path() const;
```

## <a name="has_root_directory"></a>yol:: has_root_directory

Döndürür `!root_directory().empty()`.

```cpp
bool has_root_directory() const;
```

## <a name="has_root_name"></a>yol:: has_root_name

Döndürür `!root_name().empty()`.

```cpp
bool has_root_name() const;
```

## <a name="has_root_path"></a>yol:: has_root_path

Döndürür `!root_path().empty()`.

```cpp
bool has_root_path() const;
```

## <a name="has_stem"></a>yol:: has_stem

Döndürür `!stem().empty()`.

```cpp
bool has_stem() const;
```

## <a name="is_absolute"></a>yol:: is_absolute

Windows için işlev döndürür `has_root_name() && has_root_directory()`. POSIX için, işlev döndürür `has_root_directory()`.

```cpp
bool is_absolute() const;
```

## <a name="is_relative"></a>yol:: is_relative

Döndürür `!is_absolute()`.

```cpp
bool is_relative() const;
```

## <a name="iterator"></a>yol:: Yineleyici

Yol bileşenlerini `myname`atayan çift yönlü bir sabit Yineleyici.

```cpp
class iterator
   {
   // bidirectional iterator for path
   typedef bidirectional_iterator_tag iterator_category;
   typedef path_type value_type;
   typedef ptrdiff_t difference_type;
   typedef const value_type *pointer;
   typedef const value_type& reference;
   // ...
   };
```

### <a name="remarks"></a>Açıklamalar

Sınıfı, dizideki `path` `myname` bileşenleri atayan çift yönlü bir sabit yineleyiciyi açıklar:

1. varsa kök adı

1. varsa kök dizin

1. varsa, üst `path`öğenin kalan dizin öğeleri, varsa dosya adıyla biter

Şu `pval` türde`path`bir nesne için:

1. `path::iterator X = pval.begin()`varsa, PATHNAME `path` içindeki ilk öğeyi belirler.

1. `X == pval.end()`, bileşen dizisinin `X` sonundan hemen sonra işaret ettiği zaman geçerlidir.

3. `*X`geçerli bileşenle eşleşen bir dize döndürür

1. `++X`varsa dizideki sonraki bileşeni belirler.

1. `--X`varsa, dizideki önceki bileşeni belirler.

1. Değiştirme `myname` , içindeki `myname`öğeleri tanımlayarak tüm yineleyiciler geçersiz kılar.

## <a name="make_preferred"></a>yol:: make_preferred

Her ayırıcıyı gerektiğinde bir `preferred_separator` öğesine dönüştürür.

```cpp
path& make_preferred();
```

## <a name="native"></a>path:: Native

Döndürür `myname`.

```cpp
const string_type& native() const noexcept;
```

## <a name="op_as"></a>path:: operator =

Yolun öğelerini başka bir yolun kopyasıyla değiştirir.

```cpp
path& operator=(const path& right);
path& operator=(path&& right) noexcept;

template <class Source>
path& operator=(const Source& source);
```

### <a name="parameters"></a>Parametreler

*Right*\
İçine`path`Kopyalanmakta olan [yol](../standard-library/path-class.md) .

*kaynaktaki*\
Kaynak yolu.

### <a name="remarks"></a>Açıklamalar

İlk üye işleci öğesine `right.myname` `myname`kopyalar. İkinci üye işleci öğesine `right.myname` `myname`gider. Üçüncü üye işleci ile aynı şekilde `*this = path(source)`davranır.

## <a name="op_add"></a>path:: operator + =

Çeşitli `concat` ifadeler.

```cpp
path& operator+=(const path& right);
path& operator+=(const string_type& str);
path& operator+=(const value_type *ptr);
path& operator+=(value_type elem);

template <class Source>
path& operator+=(const Source& source);

template <class Elem>
path& operator+=(Elem elem);
```

### <a name="parameters"></a>Parametreler

*Right*\
Eklenen yol.

*üstbilgisine*\
Eklenen dize.

*kaydetmeye*\
Eklenen işaretçi.

*elem*\
Eklendi `value_type` veya .`Elem`

*kaynaktaki*\
Eklenen kaynak.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri aşağıdaki ilgili ifadelerle aynı şekilde davranır:

1. `concat(right);`

1. `concat(path(str));`

1. `concat(ptr);`

1. `concat(string_type(1, elem));`

1. `concat(source);`

1. `concat(path(basic_string<Elem>(1, elem)));`

## <a name="op_divide"></a>path:: operator/=

Çeşitli `append` ifadeler.

```cpp
path& operator/=(const path& right);

template <class Source>
path& operator/=(const Source& source);
```

### <a name="parameters"></a>Parametreler

*Right*\
Eklenen yol.

*kaynaktaki*\
Eklenen kaynak.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri aşağıdaki ilgili ifadelerle aynı şekilde davranır:

1. `append(right);`

1. `append(source);`

## <a name="op_string"></a>path:: operator string_type

Döndürür `myname`.

```cpp
operator string_type() const;
```

## <a name="parent_path"></a>yol::p arent_path

Öğesinin `myname`üst yol bileşenini döndürür.

```cpp
path parent_path() const;
```

### <a name="remarks"></a>Açıklamalar

Öğesinin `myname`üst yol bileşenini, özellikle `myname` kaldırıldıktan sonra `filename().native()` öneki ve hemen önceki Dizin ayırıcılarını döndürür. (Eşit olarak, `begin() != end()`ise, Aralık `[begin(), --end())` içindeki tüm öğelerin birleştirilme, büyük ölçüde uygulanmasıyla `operator/=`yapılır.) Bileşen boş olabilir.

## <a name="path"></a>yol::p m

`path` Çeşitli şekillerde oluşturur.

```cpp
path();

path(const path& right);
path(path&& right) noexcept;

template <class Source>
path(const Source& source);

template <class Source>
path(const Source& source, const locale& loc);

template <class InIt>
path(InIt first, InIt last);

template <class InIt>
path(InIt first, InIt last, const locale& loc);
```

### <a name="parameters"></a>Parametreler

*Right*\
Oluşturulan yolun bir kopya olduğu yol.

*kaynaktaki*\
Oluşturulan yolun bir kopya olduğu kaynak.

*çerçeve*\
Belirtilen yerel ayar.

*adı*\
Kopyalanacak ilk öğenin konumu.

*soyadına*\
Kopyalanacak son öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Her bir yapıyı `myname` çeşitli yollarla oluşturucular:

Bunun için `path()`. `myname()`

İçin `path(const path& right`) `myname(right.myname)`.

Bunun için `path(path&& right)`. `myname(right.myname)`

Bunun için `template<class Source> path(const Source& source)`. `myname(source)`

Bunun için `template<class Source> path(const Source& source, const locale& loc)` `loc`, ' den gereken codecvt modellerini elde edin. `myname(source)`

Bunun için `template<class InIt> path(InIt first, InIt last)`. `myname(first, last)`

Bunun için `template<class InIt> path(InIt first, InIt last, const locale& loc)` `loc`, ' den gereken codecvt modellerini elde edin. `myname(first, last)`

## <a name="preferred_separator"></a>yol::p referred_separator

Sabit nesne, ana bilgisayar işletim sistemine bağlı olarak yol bileşenlerini ayırmak için tercih edilen karakteri verir.

```cpp
#if _WIN32_C_LIB
static constexpr value_type preferred_separator == L'\\';
#else // assume Posix
static constexpr value_type preferred_separator == '/';
#endif // filesystem model now defined
```

### <a name="remarks"></a>Açıklamalar

Bunun yerine, Windows 'un altında L '/' kullanmak için çoğu bağlamda eşit olarak izin verildiğine unutmayın.

## <a name="relative_path"></a>yol:: relative_path

Göreli yol bileşenini `myname`döndürür.

```cpp
path relative_path() const;
```

### <a name="remarks"></a>Açıklamalar

Öğesinin `myname`göreli yol bileşenini, özellikle `myname` kaldırıldıktan sonra `root_path().native()` ve bundan sonraki tüm yedekli Dizin ayırıcıları döndürür. Bileşen boş olabilir.

## <a name="remove_filename"></a>yol:: remove_filename

Dosya adını kaldırır.

```cpp
path& remove_filename();
```

## <a name="replace_extension"></a>yol:: replace_extension

Uzantısının yerini alır `myname`.

```cpp
path& replace_extension(const path& newext = path());
```

### <a name="parameters"></a>Parametreler

*newext*\
Yeni uzantı.

### <a name="remarks"></a>Açıklamalar

Önce son eki `extension().native()` öğesinden `myname`kaldırır. Sonra ( `!newext.empty() && newext[0] != dot` `dot` neredeolursa`dot` ), öğesine`myname`eklenir. `*path(".").c_str()` Ardından *newext* öğesine `myname`eklenir.

## <a name="replace_filename"></a>yol:: replace_filename

Dosya adını değiştirir.

```cpp
path& replace_filename(const path& pval);
```

### <a name="parameters"></a>Parametreler

*Pval*\
Dosya adının yolu.

### <a name="remarks"></a>Açıklamalar

Üye işlevi çalıştırılır:

```cpp
remove_filename();

*this /= pval;
return (*this);
```

## <a name="root_directory"></a>yol:: root_directory

Kök dizin bileşenini `myname`döndürür.

```cpp
path root_directory() const;
```

### <a name="remarks"></a>Açıklamalar

Bileşen boş olabilir.

## <a name="root_name"></a>yol:: root_name

Kök adı bileşenini `myname`döndürür.

```cpp
path root_name() const;
```

### <a name="remarks"></a>Açıklamalar

Bileşen boş olabilir.

## <a name="root_path"></a>yol:: root_path

Kök yolu bileşenini `myname`döndürür.

```cpp
path root_path() const;
```

### <a name="remarks"></a>Açıklamalar

, `myname`Özel olarak `root_name()`  / öğesinin kök yolu bileşeninidöndürür.`root_directory` Bileşen boş olabilir.

## <a name="stem"></a>path:: stem

`stem` Bileşenini`myname`döndürür.

```cpp
path stem() const;
```

### <a name="remarks"></a>Açıklamalar

`myname`, Özellikle de`filename().native()` sondaki kaldırılmış`extension().native()` olan `stem` bileşenini döndürür. Bileşen boş olabilir.

## <a name="string"></a>path:: String

İçinde `mypath`depolanan sırayı dönüştürür.

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

### <a name="remarks"></a>Açıklamalar

İlk (Template) üye işlevi, depolanan `mypath` sırayı aynı şekilde dönüştürür:

1. `string()` için `string<char, Traits, Alloc>()`

1. `wstring()` için `string<wchar_t, Traits, Alloc>()`

1. `u16string()` için `string<char16_t, Traits, Alloc>()`

1. `u32string()` için `string<char32_t, Traits, Alloc>()`

İkinci üye işlevi, içinde `mypath` depolanan sırayı bir **karakter** sırası için ana bilgisayar sistemi tarafından sık kırmızı kodlamaya dönüştürür ve türündeki `string`bir nesne içinde depolanmış şekilde döndürür.

## <a name="string_type"></a>yol:: string_type

Tür için `basic_string<value_type>`bir eş anlamlı.

```cpp
typedef basic_string<value_type> string_type;
```

## <a name="swap"></a>path:: swap

Yürütülür `swap(mypath, right.mypath)`.

```cpp
void swap(path& right) noexcept;
```

## <a name="u16string"></a>yol:: u16string

İçinde `mypath` depolanan diziyi UTF-16 ' a dönüştürür ve türündeki `u16string`bir nesne içinde depolanmış şekilde döndürür.

```cpp
u16string u16string() const;
```

## <a name="u32string"></a>yol:: u32string

İçinde `mypath` depolanan diziyi UTF-32 ' a dönüştürür ve türündeki `u32string`bir nesne içinde depolanmış şekilde döndürür.

```cpp
u32string u32string() const;
```

## <a name="u8string"></a>yol:: u8string

İçinde `mypath` depolanan diziyi UTF-8 ' e dönüştürür ve türünde `u8string`bir nesne içinde depolanmış şekilde döndürür.

```cpp
string u8string() const;
```

## <a name="value_type"></a>yol:: value_type

Türü, ana bilgisayar `path` işletim sistemi tarafından sık kırmızı olan öğeleri tanımlar.

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume Posix
typedef char value_type;
#endif // filesystem model now defined
```

## <a name="wstring"></a>path:: wstring

İçinde `mypath` depolanan sırayı, bir **wchar_t** sırasının ana bilgisayar sistemi tarafından sık kırmızı kodlamaya dönüştürür ve türündeki `wstring`bir nesneye depolanmış şekilde döndürür.

```cpp
wstring wstring() const;
```

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
