---
title: path Sınıfı
ms.date: 09/27/2018
f1_keywords:
- filesystem/std::experimental::filesystem::path
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
ms.openlocfilehash: 0bc26bb04464c52ed08d46e6a12c12cae6909d6f
ms.sourcegitcommit: 6ddfb8be5e5923a4d90a2c0f93f76a27ce7ac299
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2019
ms.locfileid: "74898802"
---
# <a name="path-class"></a>path Sınıfı

**Yol** sınıfı, bir yol adı olarak kullanılmak üzere uygun şekilde, `myname` olarak adlandırılan `string_type`türünde bir nesne depolar. `string_type`, `value_type` Windows üzerinde **wchar_t** veya POSIX üzerinde **char** için bir eş anlamlı olan `basic_string<value_type>`.

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
|[const_iterator](#const_iterator)|`iterator` ile eşanlamlıdır.|
|[iden](#iterator)|`myname``path` bileşenlerini atayan çift yönlü bir sabit Yineleyici.|
|[string_type](#string_type)|Tür `basic_string<value_type>`için bir eş anlamlı.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[ýna](#append)|`mypath`, dönüştürülüp preferred_separator eklemek için belirtilen diziyi ekler.|
|[ata](#assign)|`mypath`, belirtilen sırayla değiştirir ve gerektiği şekilde dönüştürülür.|
|[başladı](#begin)|Varsa, yol adındaki ilk yol öğesini tanımlayarak bir `path::iterator` döndürür.|
|[c_str](#c_str)|`mypath`ilk karaktere bir işaretçi döndürür.|
|[lediğiniz](#clear)|`mypath.clear()`yürütür.|
|[Karşılaştır](#compare)|Karşılaştırma değerlerini döndürür.|
|[concat](#compare)|Gerektiğinde `mypath`, dönüştürülmüş (ayırıcı yerleştirmeyen), belirtilen diziyi ekler.|
|[empty](#empty)|`mypath.empty()` döndürür.|
|[erer](#end)|`iterator`türünde bir dizi sonu yineleyiciyi döndürür.|
|[uzantının](#extension)|`filename()`sonekini döndürür.|
|[filename](#filename)|Myname 'ın kök dizin bileşenini döndürür, özellikle `empty() path() : *--end()`. Bileşen boş olabilir.|
|[generic_string](#generic_string)|(Windows altında) ile `this->string<Elem, Traits, Alloc>(al)` döndürür ve eğik çizgi eğik çizgiye dönüştürülür.|
|[generic_u16string](#generic_u16string)|(Windows altında) ile `u16string()` döndürür ve eğik çizgi eğik çizgiye dönüştürülür.|
|[generic_u32string](#generic_u32string)|(Windows altında) ile `u32string()` döndürür ve eğik çizgi eğik çizgiye dönüştürülür.|
|[generic_u8string](#generic_u8string)|(Windows altında) ile `u8string()` döndürür ve eğik çizgi eğik çizgiye dönüştürülür.|
|[generic_wstring](#generic_wstring)|(Windows altında) ile `wstring()` döndürür ve eğik çizgi eğik çizgiye dönüştürülür.|
|[has_extension](#has_extension)|`!extension().empty()` döndürür.|
|[has_filename](#has_filename)|`!filename().empty()` döndürür.|
|[has_parent_path](#has_parent_path)|`!parent_path().empty()` döndürür.|
|[has_relative_path](#has_relative_path)|`!relative_path().empty()` döndürür.|
|[has_root_directory](#has_root_directory)|`!root_directory().empty()` döndürür.|
|[has_root_name](#has_root_name)|`!root_name().empty()` döndürür.|
|[has_root_path](#has_root_path)|`!root_path().empty()` döndürür.|
|[has_stem](#has_stem)|`!stem().empty()` döndürür.|
|[is_absolute](#is_absolute)|Windows için işlev `has_root_name() && has_root_directory()`döndürür. POSIX için işlev `has_root_directory()`döndürür.|
|[is_relative](#is_relative)|`!is_absolute()` döndürür.|
|[make_preferred](#make_preferred)|Her ayırıcıyı gerektiğinde preferred_separator dönüştürür.|
|[Yerel](#native)|`myname` döndürür.|
|[parent_path](#parent_path)|`myname`üst yol bileşenini döndürür.|
|[preferred_separator](#preferred_separator)|Sabit nesne, ana bilgisayar işletim sistemine bağlı olarak yol bileşenlerini ayırmak için tercih edilen karakteri verir. |
|[relative_path](#relative_path)|`myname`göreli yol bileşenini döndürür. |
|[remove_filename](#remove_filename)|Dosya adını kaldırır.|
|[replace_extension](#replace_extension)|`myname`uzantısını değiştirir. |
|[replace_filename](#replace_filename)|RBu dosya adını alır.|
|[root_directory](#root_directory)|`myname`kök dizin bileşenini döndürür. |
|[root_name](#root_name)|`myname`kök adı bileşenini döndürür. |
|[root_path](#root_path)|`myname`kök yolu bileşenini döndürür.|
|[stem](#stem)|`myname``stem` bileşenini döndürür.|
|[string](#string)|`mypath`depolanan sırayı dönüştürür.|
|[Kur](#swap)|`swap(mypath, right.mypath)`yürütür.|
|[u16string](#u16string)|`mypath` depolanan diziyi UTF-16 ' a dönüştürür ve `u16string`türünde bir nesne içinde depolanmış şekilde döndürür.|
|[u32string](#u32string)|`mypath` depolanan sırayı UTF-32 ' a dönüştürür ve `u32string`türünde bir nesne içinde depolanmış şekilde döndürür.|
|[u8string](#u8string)|`mypath` depolanan sırayı UTF-8 ' e dönüştürür ve `u8string`türünde bir nesne içinde depolanmış şekilde döndürür.|
|[value_type](#value_type)|Bu tür, ana bilgisayar işletim sistemi tarafından sık kırmızı yol öğelerini tanımlar.|
|[wstring](#wstring)|`mypath` depolanan sırayı, bir `wchar_t` sırası için ana bilgisayar sistemi tarafından sık kırmızı kodlamaya dönüştürür ve `wstring`türünde bir nesnede depolanan döndürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_as)|Yolun öğelerini başka bir yolun kopyasıyla değiştirir.|
|[operator+=](#op_add)|Çeşitli `concat` ifadeleri.|
|[işleç/=](#op_divide)|Çeşitli `append` ifadeleri.|
|[işleç string_type](#op_string)|`myname` döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<FileSystem >

**Ad alanı:** std:: deneysel:: FileSystem

## <a name="append"></a>path:: Append

`mypath`, dönüştürülüp `preferred_separator` eklemek için belirtilen diziyi ekler.

```cpp
template <class Source>
path& append(const Source& source);

template <class InIt>
path& append(InIt first, InIt last);
```

### <a name="parameters"></a>Parametreler

*kaynak*\
Belirtilen sıra.

*ilk*\
Belirtilen dizinin başlangıcı.

*son*\
Belirtilen dizinin sonu.

## <a name="assign"></a>path:: Assign

`mypath`, belirtilen sırayla değiştirir ve gerektiği şekilde dönüştürülür.

```cpp
template <class Source>
path& assign(const Source& source);

template <class InIt>
path& assign(InIt first, InIt last);
```

### <a name="parameters"></a>Parametreler

*kaynak*\
Belirtilen sıra.

*ilk*\
Belirtilen dizinin başlangıcı.

*son*\
Belirtilen dizinin sonu.

## <a name="begin"></a>path:: Begin

Varsa, yol adındaki ilk yol öğesini tanımlayarak bir `path::iterator` döndürür.

```cpp
iterator begin() const;
```

## <a name="c_str"></a>yol:: c_str

`mypath`ilk karaktere bir işaretçi döndürür.

```cpp
const value_type& *c_str() const noexcept;
```

## <a name="clear"></a>path:: Clear

`mypath.clear()`yürütür.

```cpp
void clear() noexcept;
```

## <a name="compare"></a>path:: Compare

İlk işlev `mypath.compare(pval.native())`döndürür. İkinci işlev `mypath.compare(str)`döndürür. Üçüncü işlev `mypath.compare(ptr)`döndürür.

```cpp
int compare(const path& pval) const noexcept;
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>Parametreler

*Pval*\
Karşılaştırılacak yol.

*str*\
Karşılaştırılacak dize.

*ptr*\
Karşılaştırılacak işaretçi.

## <a name="concat"></a>path:: Concat

Gerektiğinde `mypath`, dönüştürülmüş (ayırıcı yerleştirmeyen), belirtilen diziyi ekler.

```cpp
template <class Source>
path& concat(const Source& source);

template <class InIt>
path& concat(InIt first, InIt last);
```

### <a name="parameters"></a>Parametreler

*kaynak*\
Belirtilen sıra.

*ilk*\
Belirtilen dizinin başlangıcı.

*son*\
Belirtilen dizinin sonu.

## <a name="const_iterator"></a>yol:: const_iterator

`iterator` ile eşanlamlıdır.

```cpp
typedef iterator const_iterator;
```

## <a name="empty"></a>path:: Empty

`mypath.empty()` döndürür.

```cpp
bool empty() const noexcept;
```

## <a name="end"></a>path:: End

`iterator`türünde bir dizi sonu yineleyiciyi döndürür.

```cpp
iterator end() const;
```

## <a name="extension"></a>path:: Extension

`filename()`sonekini döndürür.

```cpp
path extension() const;
```

### <a name="remarks"></a>Açıklamalar

`filename() X` sonekini döndürür, örneğin:

`X == path(".") || X == path("..")` veya `X` nokta içermiyorsa, son ek boştur.

Aksi takdirde, sonek en sağdaki noktayı (ve içerir) ile başlar.

## <a name="filename"></a>yol:: filename

Myname 'ın kök dizin bileşenini döndürür, özellikle `empty() path() : *--end()`. Bileşen boş olabilir.

```cpp
path filename() const;
```

## <a name="generic_string"></a>yol:: generic_string

(Windows altında) ile `this->string<Elem, Traits, Alloc>(al)` döndürür ve eğik çizgi eğik çizgiye dönüştürülür.

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

## <a name="generic_u16string"></a>yol:: generic_u16string

(Windows altında) ile `u16string()` döndürür ve eğik çizgi eğik çizgiye dönüştürülür.

```cpp
u16string generic_u16string() const;
```

## <a name="generic_u32string"></a>yol:: generic_u32string

(Windows altında) ile `u32string()` döndürür ve eğik çizgi eğik çizgiye dönüştürülür.

```cpp
u32string generic_u32string() const;
```

## <a name="generic_u8string"></a>yol:: generic_u8string

(Windows altında) ile `u8string()` döndürür ve eğik çizgi eğik çizgiye dönüştürülür.

```cpp
string generic_u8string() const;
```

## <a name="generic_wstring"></a>yol:: generic_wstring

(Windows altında) ile `wstring()` döndürür ve eğik çizgi eğik çizgiye dönüştürülür.

```cpp
wstring generic_wstring() const;
```

## <a name="has_extension"></a>yol:: has_extension

`!extension().empty()` döndürür.

```cpp
bool has_extension() const;
```

## <a name="has_filename"></a>yol:: has_filename

`!filename().empty()` döndürür.

```cpp
bool has_filename() const;
```

## <a name="has_parent_path"></a>yol:: has_parent_path

`!parent_path().empty()` döndürür.

```cpp
bool has_parent_path() const;
```

## <a name="has_relative_path"></a>yol:: has_relative_path

`!relative_path().empty()` döndürür.

```cpp
bool has_relative_path() const;
```

## <a name="has_root_directory"></a>yol:: has_root_directory

`!root_directory().empty()` döndürür.

```cpp
bool has_root_directory() const;
```

## <a name="has_root_name"></a>yol:: has_root_name

`!root_name().empty()` döndürür.

```cpp
bool has_root_name() const;
```

## <a name="has_root_path"></a>yol:: has_root_path

`!root_path().empty()` döndürür.

```cpp
bool has_root_path() const;
```

## <a name="has_stem"></a>yol:: has_stem

`!stem().empty()` döndürür.

```cpp
bool has_stem() const;
```

## <a name="is_absolute"></a>yol:: is_absolute

Windows için işlev `has_root_name() && has_root_directory()`döndürür. POSIX için işlev `has_root_directory()`döndürür.

```cpp
bool is_absolute() const;
```

## <a name="is_relative"></a>yol:: is_relative

`!is_absolute()` döndürür.

```cpp
bool is_relative() const;
```

## <a name="iterator"></a>yol:: Yineleyici

`myname`yol bileşenlerini atayan çift yönlü bir sabit Yineleyici.

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

Sınıfı, dizideki `myname` `path` bileşenlerini atayan çift yönlü sabit bir yineleyiciyi açıklar:

1. varsa kök adı

1. varsa kök dizin

1. varsa üst `path`kalan dizin öğeleri, varsa dosya adıyla biter

`path`türünde bir nesne `pval` için:

1. `path::iterator X = pval.begin()`, varsa, PATHNAME içindeki ilk `path` öğeyi belirler.

1. `X == pval.end()`, `X` yalnızca bileşenlerin dizisinin sonunu aşıp geçmiş olduğunda doğrudur.

3. `*X` geçerli bileşenle eşleşen bir dize döndürür

1. `++X`, varsa dizideki sonraki bileşeni belirler.

1. `--X`, varsa önceki bileşeni dizide belirler.

1. `myname` değiştirme, tüm yineleyiciler `myname`öğeleri belirterek geçersiz kılar.

## <a name="make_preferred"></a>yol:: make_preferred

Her ayırıcıyı gerektiğinde `preferred_separator` dönüştürür.

```cpp
path& make_preferred();
```

## <a name="native"></a>path:: Native

`myname` döndürür.

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

*sağ*\
`path`kopyalandığı [yol](../standard-library/path-class.md) .

*kaynak*\
Kaynak yolu.

### <a name="remarks"></a>Açıklamalar

İlk üye işleci `right.myname` `myname`kopyalar. İkinci üye işleci `right.myname` `myname`gider. Üçüncü üye işleci `*this = path(source)`ile aynı şekilde davranır.

## <a name="op_add"></a>path:: operator + =

Çeşitli `concat` ifadeleri.

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

*sağ*\
Eklenen yol.

*str*\
Eklenen dize.

*ptr*\
Eklenen işaretçi.

*eled*\
Eklenen `value_type` veya `Elem`.

*kaynak*\
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

Çeşitli `append` ifadeleri.

```cpp
path& operator/=(const path& right);

template <class Source>
path& operator/=(const Source& source);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Eklenen yol.

*kaynak*\
Eklenen kaynak.

### <a name="remarks"></a>Açıklamalar

Üye işlevleri aşağıdaki ilgili ifadelerle aynı şekilde davranır:

1. `append(right);`

1. `append(source);`

## <a name="op_string"></a>path:: operator string_type

`myname` döndürür.

```cpp
operator string_type() const;
```

## <a name="parent_path"></a>yol::p arent_path

`myname`üst yol bileşenini döndürür.

```cpp
path parent_path() const;
```

### <a name="remarks"></a>Açıklamalar

`filename().native()` ve hemen önceki Dizin ayırıcılarını kaldırdıktan sonra `myname` ön eki olan `myname`üst yol bileşenini döndürür. (Eşit olarak, `begin() != end()`, Aralık içindeki tüm öğelerin birleştirilmesiyle `[begin(), --end())`, `operator/=`yüksek bir şekilde uygulanıyor.) Bileşen boş olabilir.

## <a name="path"></a>yol::p m

Çeşitli yollarla bir `path` oluşturur.

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

*sağ*\
Oluşturulan yolun bir kopya olduğu yol.

*kaynak*\
Oluşturulan yolun bir kopya olduğu kaynak.

*loc*\
Belirtilen yerel ayar.

*ilk*\
Kopyalanacak ilk öğenin konumu.

*son*\
Kopyalanacak son öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Kurucuların hepsi çeşitli yollarla `myname` oluşturun:

`path()` için `myname()`.

`path(const path& right`için) `myname(right.myname)`.

`path(path&& right)` için `myname(right.myname)`.

`template<class Source> path(const Source& source)` için `myname(source)`.

`template<class Source> path(const Source& source, const locale& loc)` için `myname(source)`, `loc`gereken tüm codecvt modellerini elde edin.

`template<class InIt> path(InIt first, InIt last)` için `myname(first, last)`.

`template<class InIt> path(InIt first, InIt last, const locale& loc)` için `myname(first, last)`, `loc`gereken tüm codecvt modellerini elde edin.

## <a name="preferred_separator"></a>yol::p referred_separator

Sabit nesne, ana bilgisayar işletim sistemine bağlı olarak yol bileşenlerini ayırmak için tercih edilen karakteri verir.

```cpp
#if _WIN32_C_LIB
static constexpr value_type preferred_separator == L'\\';
#else // assume POSIX
static constexpr value_type preferred_separator == '/';
#endif // filesystem model now defined
```

### <a name="remarks"></a>Açıklamalar

Bunun yerine, Windows 'un altında L '/' kullanmak için çoğu bağlamda eşit olarak izin verildiğine unutmayın.

## <a name="relative_path"></a>yol:: relative_path

`myname`göreli yol bileşenini döndürür.

```cpp
path relative_path() const;
```

### <a name="remarks"></a>Açıklamalar

`myname`göreli yol bileşenini döndürür, özellikle, `root_path().native()` kaldırıldıktan sonra `myname` son eki ve bundan sonraki yedekli Dizin ayırıcıları. Bileşen boş olabilir.

## <a name="remove_filename"></a>yol:: remove_filename

Dosya adını kaldırır.

```cpp
path& remove_filename();
```

## <a name="replace_extension"></a>yol:: replace_extension

`myname`uzantısını değiştirir.

```cpp
path& replace_extension(const path& newext = path());
```

### <a name="parameters"></a>Parametreler

*newext*\
Yeni uzantı.

### <a name="remarks"></a>Açıklamalar

Önce `myname``extension().native()` son eki kaldırır. `!newext.empty() && newext[0] != dot` (`dot` `*path(".").c_str()`) ise, `dot` `myname`eklenir. Ardından *newext* `myname`eklenir.

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

`myname`kök dizin bileşenini döndürür.

```cpp
path root_directory() const;
```

### <a name="remarks"></a>Açıklamalar

Bileşen boş olabilir.

## <a name="root_name"></a>yol:: root_name

`myname`kök adı bileşenini döndürür.

```cpp
path root_name() const;
```

### <a name="remarks"></a>Açıklamalar

Bileşen boş olabilir.

## <a name="root_path"></a>yol:: root_path

`myname`kök yolu bileşenini döndürür.

```cpp
path root_path() const;
```

### <a name="remarks"></a>Açıklamalar

`myname`, özel olarak  / `root_directory``root_name()`kök yolu bileşenini döndürür. Bileşen boş olabilir.

## <a name="stem"></a>path:: stem

`myname``stem` bileşenini döndürür.

```cpp
path stem() const;
```

### <a name="remarks"></a>Açıklamalar

`myname``stem` bileşenini, özellikle de herhangi bir sondaki `extension().native()` kaldırılan `filename().native()` döndürür. Bileşen boş olabilir.

## <a name="string"></a>path:: String

`mypath`depolanan sırayı dönüştürür.

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

### <a name="remarks"></a>Açıklamalar

İlk (Template) üye işlevi, `mypath` depolanan sırayı aynı şekilde dönüştürür:

1. `string()` için `string<char, Traits, Alloc>()`

1. `wstring()` için `string<wchar_t, Traits, Alloc>()`

1. `u16string()` için `string<char16_t, Traits, Alloc>()`

1. `u32string()` için `string<char32_t, Traits, Alloc>()`

İkinci üye işlevi, `mypath` depolanan sırayı, bir **karakter** sırası için ana bilgisayar sistemi tarafından sık kırmızı kodlamaya dönüştürür ve `string`türünde bir nesnede saklı olarak döndürür.

## <a name="string_type"></a>yol:: string_type

Tür `basic_string<value_type>`için bir eş anlamlı.

```cpp
typedef basic_string<value_type> string_type;
```

## <a name="swap"></a>path:: swap

`swap(mypath, right.mypath)`yürütür.

```cpp
void swap(path& right) noexcept;
```

## <a name="u16string"></a>yol:: u16string

`mypath` depolanan diziyi UTF-16 ' a dönüştürür ve `u16string`türünde bir nesne içinde depolanmış şekilde döndürür.

```cpp
u16string u16string() const;
```

## <a name="u32string"></a>yol:: u32string

`mypath` depolanan sırayı UTF-32 ' a dönüştürür ve `u32string`türünde bir nesne içinde depolanmış şekilde döndürür.

```cpp
u32string u32string() const;
```

## <a name="u8string"></a>yol:: u8string

`mypath` depolanan sırayı UTF-8 ' e dönüştürür ve `u8string`türünde bir nesne içinde depolanmış şekilde döndürür.

```cpp
string u8string() const;
```

## <a name="value_type"></a>yol:: value_type

Tür, ana bilgisayar işletim sistemi tarafından kullanılan `path` öğelerini açıklar.

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume POSIX
typedef char value_type;
#endif // filesystem model now defined
```

## <a name="wstring"></a>path:: wstring

`mypath` depolanan sırayı, bir **wchar_t** sırası için ana bilgisayar sistemi tarafından sık kırmızı kodlamaya dönüştürür ve `wstring`türünde bir nesnede depolanan döndürür.

```cpp
wstring wstring() const;
```

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
