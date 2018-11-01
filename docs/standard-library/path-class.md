---
title: path Sınıfı
ms.date: 09/27/2018
f1_keywords:
- filesystem/std::experimental::filesystem::path
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
ms.openlocfilehash: 486245df3433f552c289786a0b20deb33c8fb6c0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618224"
---
# <a name="path-class"></a>path Sınıfı

**Yolu** sınıf türünde bir nesne depolar `string_type`adlı `myname` doğrultusunda exposition, uygun bir yol adı olarak kullanmak için burada. `string_type` eşanlamlıdır `basic_string<value_type>`burada `value_type` eşanlamlıdır **wchar_t** Windows üzerinde veya **char** üzerinde POSIX.

Daha fazla bilgi ve kod örnekleri için bkz. [dosya sistemi gezintisi (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class path;
```

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Yolu](#path)|Oluşturur bir `path`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[const_iterator](#const_iterator)|İçin bir eşanlamlı `iterator`.|
|[Yineleyici](#iterator)|Atayan bir çift yönlü sabit yineleyici `path` bileşenlerinin `myname`.|
|[string_type](#string_type)|Türü eşanlamlıdır `basic_string<value_type>`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Ekleme](#append)|Belirtilen dizinin ekler `mypath`dönüştürülür ve bir preferred_separator gerektiği gibi ekleme.|
|[Ata](#assign)|Değiştirir `mypath` belirtilen dizisiyle gerektiği şekilde dönüştürülür.|
|[başlayın](#begin)|Döndürür bir `path::iterator` ilk yol, yol öğesinde varsa belirleme.|
|[c_str](#c_str)|İlk karakter, bir işaretçi döndürür `mypath`.|
|[Temizle](#clear)|Yürütür `mypath.clear()`.|
|[Karşılaştırma](#compare)|Karşılaştırma değerlerini döndürür.|
|[concat](#compare)|Belirtilen dizinin ekler `mypath`, dönüştürülen (ancak bir ayırıcı ekleme değil) gerektiği gibi.|
|[boş](#empty)|Döndürür `mypath.empty()`.|
|[Son](#end)|Türü bir dizisi end yineleyici döndürür `iterator`.|
|[Uzantı](#extension)|Sonekini döndürür `filename()`.|
|[Dosya adı](#filename)|Kök dizin bileşeni myname, özellikle döndürür `empty() path() : *--end()`. Bileşen boş olabilir.|
|[generic_string](#generic_string)|Döndürür `this->string<Elem, Traits, Alloc>(al)` ile (Windows altında) tüm ters eğik çizgi, eğik çizgi için dönüştürülür.|
|[generic_u16string](#generic_u16string)|Döndürür `u16string()` ile (Windows altında) tüm ters eğik çizgi, eğik çizgi için dönüştürülür.|
|[generic_u32string](#generic_u32string)|Döndürür `u32string()` ile (Windows altında) tüm ters eğik çizgi, eğik çizgi için dönüştürülür.|
|[generic_u8string](#generic_u8string)|Döndürür `u8string()` ile (Windows altında) tüm ters eğik çizgi, eğik çizgi için dönüştürülür.|
|[generic_wstring](#generic_wstring)|Döndürür `wstring()` ile (Windows altında) tüm ters eğik çizgi, eğik çizgi için dönüştürülür.|
|[has_extension](#has_extension)|Döndürür `!extension().empty()`.|
|[has_filename](#has_filename)|Döndürür `!filename().empty()`.|
|[has_parent_path](#has_parent_path)|Döndürür `!parent_path().empty()`.|
|[has_relative_path](#has_relative_path)|Döndürür `!relative_path().empty()`.|
|[has_root_directory](#has_root_directory)|Döndürür `!root_directory().empty()`.|
|[has_root_name](#has_root_name)|Döndürür `!root_name().empty()`.|
|[has_root_path](#has_root_path)|Döndürür `!root_path().empty()`.|
|[has_stem](#has_stem)|Döndürür `!stem().empty()`.|
|[is_absolute](#is_absolute)|Windows için işlevi döndürür `has_root_name() && has_root_directory()`. İşlev, POSIX döndürür `has_root_directory()`.|
|[is_relative](#is_relative)|Döndürür `!is_absolute()`.|
|[make_preferred](#make_preferred)|Her ayırıcı bir preferred_separator için gerektiği şekilde dönüştürür.|
|[Yerel](#native)|Döndürür `myname`.|
|[parent_path](#parent_path)|Üst'ın yol bileşenini döndürür `myname`.|
|[preferred_separator](#preferred_separator)|Sabit nesne yolu bileşenleri, konak işletim sistemine bağlı olarak ayırmak için tercih edilen karakter sağlar. |
|[relatıve_path](#relative_path)|Göreli yol bileşenini döndürür `myname`. |
|[remove_filename](#remove_filename)|Dosya adını kaldırır.|
|[replace_extension](#replace_extension)|Uzantısını değiştirir `myname`. |
|[replace_filename](#replace_filename)|RReplaces dosya adı.|
|[root_directory](#root_directory)|Kök dizin bileşenini döndürür `myname`. |
|[kök_adı](#root_name)|Kök adı bileşenini döndürür `myname`. |
|[root_path](#root_path)|Kök yolu bileşenini döndürür `myname`.|
|[fetemm](#stem)|Döndürür `stem` bileşeninin `myname`.|
|[string](#string)|Depolanan dizisi dönüştürür `mypath`.|
|[değiştirme](#swap)|Yürütür `swap(mypath, right.mypath)`.|
|[u16string](#u16string)|Depolanan dizisi dönüştürür `mypath` UTF-16 ve türünün nesnesinde depolanan döndürür `u16string`.|
|[u32string](#u32string)|Depolanan dizisi dönüştürür `mypath` UTF-32 ve türünün nesnesinde depolanan döndürür `u32string`.|
|[u8string](#u8string)|Depolanan dizisi dönüştürür `mypath` UTF-8 ve türünün nesnesinde depolanan döndürür `u8string`.|
|[value_type](#value_type)|Türü konak işletim sistemi tarafından stadyumlarda yolu öğeleri açıklar.|
|[wstring](#wstring)|Depolanan dizisi dönüştürür `mypath` için ana bilgisayar sistemi tarafından stadyumlarda kodlama için bir `wchar_t` dizisi ve türünün nesnesinde depolanan döndürür `wstring`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_as)|Yolun öğelerini başka bir yol kopyasıyla değiştirir.|
|[operator+=](#op_add)|Çeşitli `concat` ifadeler.|
|[/ = işleci](#op_divide)|Çeşitli `append` ifadeler.|
|[string_type işleci](#op_string)|Döndürür `myname`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<filesystem >

**Namespace:** std::experimental::filesystem

## <a name="append"></a> PATH::Append

Belirtilen dizinin ekler `mypath`dönüştürülmüş ve ekleme bir `preferred_separator` gerektiğinde.

```cpp
template <class Source>
path& append(const Source& source);

template <class InIt>
path& append(InIt first, InIt last);
```

### <a name="parameters"></a>Parametreler

*source*<br/>
Belirtilen sıra.

*ilk*<br/>
Belirtilen sıra başlangıcı.

*Son*<br/>
Belirtilen sıra sonu.

## <a name="assign"></a> PATH::Assign

Değiştirir `mypath` belirtilen dizisiyle gerektiği şekilde dönüştürülür.

```cpp
template <class Source>
path& assign(const Source& source);

template <class InIt>
path& assign(InIt first, InIt last);
```

### <a name="parameters"></a>Parametreler

*source*<br/>
Belirtilen sıra.

*ilk*<br/>
Belirtilen sıra başlangıcı.

*Son*<br/>
Belirtilen sıra sonu.

## <a name="begin"></a> PATH::Begin

Döndürür bir `path::iterator` ilk yol, yol öğesinde varsa belirleme.

```cpp
iterator begin() const;
```

## <a name="c_str"></a> PATH::c_str

İlk karakter, bir işaretçi döndürür `mypath`.

```cpp
const value_type& *c_str() const noexcept;
```

## <a name="clear"></a> PATH::Clear

Yürütür `mypath.clear()`.

```cpp
void clear() noexcept;
```

## <a name="compare"></a> PATH::COMPARE

İşlev `mypath.compare(pval.native())`. İkinci işlevi döndürür `mypath.compare(str)`. Üçüncü işlevi döndürür `mypath.compare(ptr)`.

```cpp
int compare(const path& pval) const noexcept;
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>Parametreler

*pval*<br/>
Karşılaştırılacak yolu.

*str*<br/>
Karşılaştırılacak dize.

*ptr*<br/>
Karşılaştırmak için işaretçi.

## <a name="concat"></a> PATH::concat

Belirtilen dizinin ekler `mypath`, dönüştürülen (ancak bir ayırıcı ekleme değil) gerektiği gibi.

```cpp
template <class Source>
path& concat(const Source& source);

template <class InIt>
path& concat(InIt first, InIt last);
```

### <a name="parameters"></a>Parametreler

*source*<br/>
Belirtilen sıra.

*ilk*<br/>
Belirtilen sıra başlangıcı.

*Son*<br/>
Belirtilen sıra sonu.

## <a name="const_iterator"></a> PATH::const_iterator

İçin bir eşanlamlı `iterator`.

```cpp
typedef iterator const_iterator;
```

## <a name="empty"></a> PATH::empty

Döndürür `mypath.empty()`.

```cpp
bool empty() const noexcept;
```

## <a name="end"></a> PATH::End

Türü bir dizisi end yineleyici döndürür `iterator`.

```cpp
iterator end() const;
```

## <a name="extension"></a> PATH::Extension

Sonekini döndürür `filename()`.

```cpp
path extension() const;
```

### <a name="remarks"></a>Açıklamalar

Sonekini döndürür `filename() X` gibi:

Varsa `X == path(".") || X == path("..")` veya `X` hiçbir nokta içeren soneki boştur.

Aksi takdirde son eki ile başlar (ve içerir) en sağdaki nokta.

## <a name="filename"></a> PATH::filename

Kök dizin bileşeni myname, özellikle döndürür `empty() path() : *--end()`. Bileşen boş olabilir.

```cpp
path filename() const;
```

## <a name="generic_string"></a> PATH::generic_string

Döndürür `this->string<Elem, Traits, Alloc>(al)` ile (Windows altında) tüm ters eğik çizgi, eğik çizgi için dönüştürülür.

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

## <a name="generic_u16string"></a> PATH::generic_u16string

Döndürür `u16string()` ile (Windows altında) tüm ters eğik çizgi, eğik çizgi için dönüştürülür.

```cpp
u16string generic_u16string() const;
```

## <a name="generic_u32string"></a> PATH::generic_u32string

Döndürür `u32string()` ile (Windows altında) tüm ters eğik çizgi, eğik çizgi için dönüştürülür.

```cpp
u32string generic_u32string() const;
```

## <a name="generic_u8string"></a> PATH::generic_u8string

Döndürür `u8string()` ile (Windows altında) tüm ters eğik çizgi, eğik çizgi için dönüştürülür.

```cpp
string generic_u8string() const;
```

## <a name="generic_wstring"></a> PATH::generic_wstring

Döndürür `wstring()` ile (Windows altında) tüm ters eğik çizgi, eğik çizgi için dönüştürülür.

```cpp
wstring generic_wstring() const;
```

## <a name="has_extension"></a> PATH::has_extension

Döndürür `!extension().empty()`.

```cpp
bool has_extension() const;
```

## <a name="has_filename"></a> PATH::has_filename

Döndürür `!filename().empty()`.

```cpp
bool has_filename() const;
```

## <a name="has_parent_path"></a> PATH::has_parent_path

Döndürür `!parent_path().empty()`.

```cpp
bool has_parent_path() const;
```

## <a name="has_relative_path"></a> PATH::has_relative_path

Döndürür `!relative_path().empty()`.

```cpp
bool has_relative_path() const;
```

## <a name="has_root_directory"></a> PATH::has_root_directory

Döndürür `!root_directory().empty()`.

```cpp
bool has_root_directory() const;
```

## <a name="has_root_name"></a> PATH::has_root_name

Döndürür `!root_name().empty()`.

```cpp
bool has_root_name() const;
```

## <a name="has_root_path"></a> PATH::has_root_path

Döndürür `!root_path().empty()`.

```cpp
bool has_root_path() const;
```

## <a name="has_stem"></a> PATH::has_stem

Döndürür `!stem().empty()`.

```cpp
bool has_stem() const;
```

## <a name="is_absolute"></a> PATH::is_absolute

Windows için işlevi döndürür `has_root_name() && has_root_directory()`. İşlev, POSIX döndürür `has_root_directory()`.

```cpp
bool is_absolute() const;
```

## <a name="is_relative"></a> PATH::is_relative

Döndürür `!is_absolute()`.

```cpp
bool is_relative() const;
```

## <a name="iterator"></a> PATH::iterator

Yol bileşenlerini belirten çift yönlü bir sabit yineleyici `myname`.

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

Sınıfı, atayan bir çift yönlü sabit yineleyiciyi açıklayan `path` bileşenlerinin `myname` dizideki:

1. kök adı, mevcutsa

1. varsa, kök dizini

1. Kalan directory öğeleri üst `path`, varsa, varsa dosya ile biten

İçin `pval` türünde bir nesne `path`:

1. `path::iterator X = pval.begin()` ilk atayan `path` yol varsa öğe.

1. `X == pval.end()` true olduğunda `X` bileşenlerinin yalnızca dizinin bitişini geçen noktaları.

3. `*X` Geçerli bileşenin eşleşen bir dize döndürür

1. `++X` Dizideki sonraki bileşen varsa belirler.

1. `--X` varsa sıradaki önceki bileşenin belirler.

1. Değiştirme `myname` öğeleri tanımlayarak tüm yineleyiciyi geçersiz kılmaz `myname`.

## <a name="make_preferred"></a> PATH::make_preferred

Her ayırıcısı dönüştürür bir `preferred_separator` gerektiğinde.

```cpp
path& make_preferred();
```

## <a name="native"></a> PATH::Native

Döndürür `myname`.

```cpp
const string_type& native() const noexcept;
```

## <a name="op_as"></a> PATH::operator =

Yolun öğelerini başka bir yol kopyasıyla değiştirir.

```cpp
path& operator=(const path& right);
path& operator=(path&& right) noexcept;

template <class Source>
path& operator=(const Source& source);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
[Yolu](../standard-library/path-class.md) içine kopyalanan `path`.

*source*<br/>
Kaynak yolu.

### <a name="remarks"></a>Açıklamalar

İlk üye işleci kopyaları `right.myname` için `myname`. İkinci üye işleci taşır `right.myname` için `myname`. Üçüncü üye işleci gibi davranır `*this = path(source)`.

## <a name="op_add"></a> PATH::operator +=

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

*sağ*<br/>
Eklenen yolu.

*str*<br/>
Eklenen dize.

*ptr*<br/>
Eklenen işaretçisi.

*Elem*<br/>
Eklenen `value_type` veya `Elem`.

*source*<br/>
Eklenen kaynağı.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri aşağıdaki karşılık gelen ifadeler aynı şekilde davranır:

1. `concat(right);`

1. `concat(path(str));`

1. `concat(ptr);`

1. `concat(string_type(1, elem));`

1. `concat(source);`

1. `concat(path(basic_string<Elem>(1, elem)));`

## <a name="op_divide"></a> PATH::operator / =

Çeşitli `append` ifadeler.

```cpp
path& operator/=(const path& right);

template <class Source>
path& operator/=(const Source& source);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Eklenen yolu.

*source*<br/>
Eklenen kaynağı.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri aşağıdaki karşılık gelen ifadeler aynı şekilde davranır:

1. `append(right);`

1. `append(source);`

## <a name="op_string"></a> PATH::operator string_type

Döndürür `myname`.

```cpp
operator string_type() const;
```

## <a name="parent_path"></a> PATH::parent_path

Üst'ın yol bileşenini döndürür `myname`.

```cpp
path parent_path() const;
```

### <a name="remarks"></a>Açıklamalar

Üst'ın yol bileşenini döndürür `myname`, özellikle öneki `myname` kaldırdıktan sonra `filename().native()` ve hemen önceki dizin ayırıcı. (Durumunda, eşit şekilde, `begin() != end()`, aralıktaki tüm öğelerin birleştirme olan `[begin(), --end())` sırayla uygulayarak `operator/=`.) Bileşen boş olabilir.

## <a name="path"></a> PATH::PATH

Oluşturur bir `path` çeşitli şekillerde.

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

*sağ*<br/>
Oluşturulan yol kopyası olacak olduğu yolu.

*source*<br/>
Oluşturulan yol kopyası olacak olduğu kaynak.

*LOC*<br/>
Belirtilen yerel ayar.

*ilk*<br/>
Kopyalanacak ilk öğenin konumu.

*Son*<br/>
Kopyalanacak son öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Tüm oluşturmak oluşturucular `myname` çeşitli şekillerde:

İçin `path()` olduğu `myname()`.

İçin `path(const path& right`) bu `myname(right.myname)`.

İçin `path(path&& right)` olduğu `myname(right.myname)`.

İçin `template<class Source> path(const Source& source)` olduğu `myname(source)`.

İçin `template<class Source> path(const Source& source, const locale& loc)` olduğu `myname(source)`, gerekli gelen codecvt modelleri herhangi alma `loc`.

İçin `template<class InIt> path(InIt first, InIt last)` olduğu `myname(first, last)`.

İçin `template<class InIt> path(InIt first, InIt last, const locale& loc)` olduğu `myname(first, last)`, gerekli gelen codecvt modelleri herhangi alma `loc`.

## <a name="preferred_separator"></a> PATH::preferred_separator

Sabit nesne yolu bileşenleri, konak işletim sistemine bağlı olarak ayırmak için tercih edilen karakter sağlar.

```cpp
#if _WIN32_C_LIB
static constexpr value_type preferred_separator == L'\\';
#else // assume Posix
static constexpr value_type preferred_separator == '/';
#endif // filesystem model now defined
```

### <a name="remarks"></a>Açıklamalar

Bunun yerine '/' L'ı kullanmak için Windows altında çoğu bağlamlarda eşit bulunmadığı olduğunu unutmayın.

## <a name="relative_path"></a> PATH::relative_path

Göreli yol bileşenini döndürür `myname`.

```cpp
path relative_path() const;
```

### <a name="remarks"></a>Açıklamalar

Göreli yol bileşenini döndürür `myname`, özellikle sonekini `myname` kaldırdıktan sonra `root_path().native()` ve hemen sonraki yedekli dizin ayırıcı. Bileşen boş olabilir.

## <a name="remove_filename"></a> PATH::remove_filename

Dosya adını kaldırır.

```cpp
path& remove_filename();
```

## <a name="replace_extension"></a> PATH::replace_extension

Uzantısını değiştirir `myname`.

```cpp
path& replace_extension(const path& newext = path());
```

### <a name="parameters"></a>Parametreler

*newext*<br/>
Yeni uzantı.

### <a name="remarks"></a>Açıklamalar

İlk soneki kaldırır `extension().native()` gelen `myname`. Sonra eğer `!newext.empty() && newext[0] != dot` (burada `dot` olduğu `*path(".").c_str()`), ardından `dot` eklenir `myname`. Ardından *newext* eklenir `myname`.

## <a name="replace_filename"></a> PATH::replace_filename

Dosya adını değiştirir.

```cpp
path& replace_filename(const path& pval);
```

### <a name="parameters"></a>Parametreler

*pval*<br/>
Dosya yolu.

### <a name="remarks"></a>Açıklamalar

Üye işlevi yürütür:

```cpp
remove_filename();

*this /= pval;
return (*this);
```

## <a name="root_directory"></a> PATH::root_directory

Kök dizin bileşenini döndürür `myname`.

```cpp
path root_directory() const;
```

### <a name="remarks"></a>Açıklamalar

Bileşen boş olabilir.

## <a name="root_name"></a> PATH::root_name

Kök adı bileşenini döndürür `myname`.

```cpp
path root_name() const;
```

### <a name="remarks"></a>Açıklamalar

Bileşen boş olabilir.

## <a name="root_path"></a> PATH::root_path

Kök yolu bileşenini döndürür `myname`.

```cpp
path root_path() const;
```

### <a name="remarks"></a>Açıklamalar

Kök yolu bileşenini döndürür `myname`, özellikle `root_name()`  /  `root_directory`. Bileşen boş olabilir.

## <a name="stem"></a> PATH::stem

Döndürür `stem` bileşeninin `myname`.

```cpp
path stem() const;
```

### <a name="remarks"></a>Açıklamalar

Döndürür `stem` bileşeninin `myname`, özellikle `filename().native()` herhangi sondaki ile `extension().native()` kaldırıldı. Bileşen boş olabilir.

## <a name="string"></a> PATH::String

Depolanan dizisi dönüştürür `mypath`.

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

### <a name="remarks"></a>Açıklamalar

Depolanan dizisi ilk (şablon) üye işlevi dönüştürür `mypath` aynı şekilde çalışır:

1. `string()` için `string<char, Traits, Alloc>()`

1. `wstring()` için `string<wchar_t, Traits, Alloc>()`

1. `u16string()` için `string<char16_t, Traits, Alloc>()`

1. `u32string()` için `string<char32_t, Traits, Alloc>()`

İkinci üye işlevi, depolanan dizisi dönüştürür `mypath` için ana bilgisayar sistemi tarafından stadyumlarda kodlama için bir **char** dizisi ve türünün nesnesinde depolanan döndürür `string`.

## <a name="string_type"></a> PATH::string_type

Türü eşanlamlıdır `basic_string<value_type>`.

```cpp
typedef basic_string<value_type> string_type;
```

## <a name="swap"></a> PATH::Swap

Yürütür `swap(mypath, right.mypath)`.

```cpp
void swap(path& right) noexcept;
```

## <a name="u16string"></a> PATH::u16string

Depolanan dizisi dönüştürür `mypath` UTF-16 ve türünün nesnesinde depolanan döndürür `u16string`.

```cpp
u16string u16string() const;
```

## <a name="u32string"></a> PATH::u32string

Depolanan dizisi dönüştürür `mypath` UTF-32 ve türünün nesnesinde depolanan döndürür `u32string`.

```cpp
u32string u32string() const;
```

## <a name="u8string"></a> PATH::u8string

Depolanan dizisi dönüştürür `mypath` UTF-8 ve türünün nesnesinde depolanan döndürür `u8string`.

```cpp
string u8string() const;
```

## <a name="value_type"></a> PATH::value_type

Türü tanımlayan `path` konak işletim sistemi tarafından stadyumlarda öğeleri.

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume Posix
typedef char value_type;
#endif // filesystem model now defined
```

## <a name="wstring"></a> PATH::wstring

Depolanan dizisi dönüştürür `mypath` için ana bilgisayar sistemi tarafından stadyumlarda kodlama için bir **wchar_t** dizisi ve türünün nesnesinde depolanan döndürür `wstring`.

```cpp
wstring wstring() const;
```

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
