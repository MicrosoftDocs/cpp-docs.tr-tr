---
title: path Sınıfı
ms.date: 09/27/2018
f1_keywords:
- filesystem/std::experimental::filesystem::path
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
ms.openlocfilehash: 669dfd2c8cd8576ebfb6684bab7cf63cdd51babc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372115"
---
# <a name="path-class"></a>path Sınıfı

**Yol** sınıfı, bir yol `string_type`adı `myname` olarak kullanıma uygun, sergi amacıyla burada çağrılan bir tür nesnesini depolar. `string_type`için `basic_string<value_type>`eşanlamlıdır , nerede `value_type` Windows veya **POSIX üzerinde char** **wchar_t** için eşanlamlıdır.

Daha fazla bilgi ve kod örnekleri için [Bkz. Dosya Sistemi Gezintisi (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class path;
```

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Yolu](#path)|Bir `path`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[const_iterator](#const_iterator)|Bir eşanlamlı `iterator`.|
|[Yineleyici](#iterator)|`myname`Bileşenlerin belirlenmesini `path` belirleyen çift yönlü sabit bir yineleme|
|[string_type](#string_type)|Türü için `basic_string<value_type>`eşanlamlıdır.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Ekleme](#append)|Belirtilen `mypath`sırayı, dönüştürülür ve gerektiğinde bir preferred_separator ekler.|
|[Atamak](#assign)|Gerektiği `mypath` gibi dönüştürülen belirtilen sırayla değiştirilir.|
|[Başlamak](#begin)|Varsa, `path::iterator` yol adındaki ilk yol öğesini atamayı döndürür.|
|[c_str](#c_str)|`mypath`'deki ilk karaktere işaretçi döndürür|
|[Temizleyin](#clear)|Yürütür. `mypath.clear()`|
|[Karşılaştırmak](#compare)|Karşılaştırma değerlerini döndürür.|
|[Concat](#compare)|Belirtilen sırayı `mypath`gerektiği gibi dönüştürülür (ancak ayırıcı eklemez) ekler.|
|[empty](#empty)|`mypath.empty()` döndürür.|
|[Son -unda](#end)|Türünde `iterator`bir dizi sonu yinelemesi verir.|
|[Uzantısı](#extension)|'nin sonekini `filename()`verir.|
|[filename](#filename)|Adımın kök dizini bileşenini, `empty() path() : *--end()`özellikle döndürür. Bileşen boş olabilir.|
|[generic_string](#generic_string)|İleri `this->string<Elem, Traits, Alloc>(al)` eğik çizgiye dönüştürülen herhangi bir ters çizgi yle (Windows altında) döndürür.|
|[generic_u16string](#generic_u16string)|İleri `u16string()` eğik çizgiye dönüştürülen herhangi bir ters çizgi yle (Windows altında) döndürür.|
|[generic_u32string](#generic_u32string)|İleri `u32string()` eğik çizgiye dönüştürülen herhangi bir ters çizgi yle (Windows altında) döndürür.|
|[generic_u8string](#generic_u8string)|İleri `u8string()` eğik çizgiye dönüştürülen herhangi bir ters çizgi yle (Windows altında) döndürür.|
|[generic_wstring](#generic_wstring)|İleri `wstring()` eğik çizgiye dönüştürülen herhangi bir ters çizgi yle (Windows altında) döndürür.|
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
|[make_preferred](#make_preferred)|Her ayırıcıyı gerektiği gibi bir preferred_separator dönüştürür.|
|[yerel](#native)|`myname` döndürür.|
|[parent_path](#parent_path)|Üst yol bileşenini `myname`döndürür.|
|[preferred_separator](#preferred_separator)|Sabit nesne, ana bilgisayar işletim sistemine bağlı olarak yol bileşenlerini ayırmak için tercih edilen karakteri verir. |
|[relative_path](#relative_path)|Göreli yol bileşenini döndürür. `myname` |
|[remove_filename](#remove_filename)|Dosya adını kaldırır.|
|[replace_extension](#replace_extension)|uzantısı nı `myname`değiştirir. |
|[replace_filename](#replace_filename)|R Dosya adını değiştirir.|
|[root_directory](#root_directory)|Kök dizin bileşenini `myname`döndürür. |
|[root_name](#root_name)|Kök ad bileşenini `myname`döndürür. |
|[root_path](#root_path)|Kök yol bileşenini `myname`döndürür.|
|[Kök](#stem)|`myname`Bileşenini `stem` verir.|
|[Dize](#string)|Depolanan sırayı `mypath`dönüştürür.|
|[Takas](#swap)|Yürütür. `swap(mypath, right.mypath)`|
|[u16string](#u16string)|DEPOLANAN sırayı `mypath` UTF-16'ya dönüştürür ve depolanan türünde `u16string`bir nesnede döndürür.|
|[u32string](#u32string)|DEPOLANAN sırayı `mypath` UTF-32'ye dönüştürür ve depolanan türünde `u32string`bir nesnede döndürür.|
|[u8string](#u8string)|Depolanan sırayı `mypath` UTF-8'e dönüştürür ve bir tür `u8string`nesnede depolanır.|
|[value_type](#value_type)|Tür, ana bilgisayar işletim sistemi tarafından tercih edilen yol öğelerini açıklar.|
|[wstring](#wstring)|Depolanan sırayı, `mypath` ana bilgisayar sistemi tarafından bir `wchar_t` dizi için tercih edilen kodlamaya dönüştürür `wstring`ve türünde bir nesnede depolanır.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç=](#op_as)|Yolun öğelerini başka bir yolun kopyasıyla değiştirir.|
|[işleç+=](#op_add)|Çeşitli `concat` ifadeler.|
|[işleç/=](#op_divide)|Çeşitli `append` ifadeler.|
|[operatör string_type](#op_string)|`myname` döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<dosya sistemi>

**Ad alanı:** std::deneysel::filesystem

## <a name="pathappend"></a><a name="append"></a>yol::ek

Belirtilen `mypath`sırayı, dönüştürülür ve gerektiği gibi `preferred_separator` ekler.

```cpp
template <class Source>
path& append(const Source& source);

template <class InIt>
path& append(InIt first, InIt last);
```

### <a name="parameters"></a>Parametreler

*Kaynak*\
Belirtilen sıra.

*Ilk*\
Belirtilen sıranın başlangıcı.

*Son*\
Belirtilen sıranın sonu.

## <a name="pathassign"></a><a name="assign"></a>yol::atama

Gerektiği `mypath` gibi dönüştürülen belirtilen sırayla değiştirilir.

```cpp
template <class Source>
path& assign(const Source& source);

template <class InIt>
path& assign(InIt first, InIt last);
```

### <a name="parameters"></a>Parametreler

*Kaynak*\
Belirtilen sıra.

*Ilk*\
Belirtilen sıranın başlangıcı.

*Son*\
Belirtilen sıranın sonu.

## <a name="pathbegin"></a><a name="begin"></a>yol::başla

Varsa, `path::iterator` yol adındaki ilk yol öğesini atamayı döndürür.

```cpp
iterator begin() const;
```

## <a name="pathc_str"></a><a name="c_str"></a>yol::c_str

`mypath`'deki ilk karaktere işaretçi döndürür

```cpp
const value_type& *c_str() const noexcept;
```

## <a name="pathclear"></a><a name="clear"></a>yol::açık

Yürütür. `mypath.clear()`

```cpp
void clear() noexcept;
```

## <a name="pathcompare"></a><a name="compare"></a>yol::karşılaştır

İlk işlev `mypath.compare(pval.native())`döndürür. İkinci işlev `mypath.compare(str)`döndürür. Üçüncü işlev `mypath.compare(ptr)`döndürür.

```cpp
int compare(const path& pval) const noexcept;
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>Parametreler

*Pval*\
Karşılaştırma yolu.

*Str*\
Karşılaştırmak için dize.

*Ptr*\
Karşılaştırmak için işaretçi.

## <a name="pathconcat"></a><a name="concat"></a>yol::concat

Belirtilen sırayı `mypath`gerektiği gibi dönüştürülür (ancak ayırıcı eklemez) ekler.

```cpp
template <class Source>
path& concat(const Source& source);

template <class InIt>
path& concat(InIt first, InIt last);
```

### <a name="parameters"></a>Parametreler

*Kaynak*\
Belirtilen sıra.

*Ilk*\
Belirtilen sıranın başlangıcı.

*Son*\
Belirtilen sıranın sonu.

## <a name="pathconst_iterator"></a><a name="const_iterator"></a>yol::const_iterator

Bir eşanlamlı `iterator`.

```cpp
typedef iterator const_iterator;
```

## <a name="pathempty"></a><a name="empty"></a>yol::boş

`mypath.empty()` döndürür.

```cpp
bool empty() const noexcept;
```

## <a name="pathend"></a><a name="end"></a>yol::sonu

Türünde `iterator`bir dizi sonu yinelemesi verir.

```cpp
iterator end() const;
```

## <a name="pathextension"></a><a name="extension"></a>yol::uzantı

'nin sonekini `filename()`verir.

```cpp
path extension() const;
```

### <a name="remarks"></a>Açıklamalar

`filename() X` Bu tür sonek döndürür:

Nokta `X == path(".") || X == path("..")` `X` yoksa veya varsa, sonek boştur.

Aksi takdirde, sonek (ve içerir) en sağ nokta ile başlar.

## <a name="pathfilename"></a><a name="filename"></a>yol::dosya adı

Adımın kök dizini bileşenini, `empty() path() : *--end()`özellikle döndürür. Bileşen boş olabilir.

```cpp
path filename() const;
```

## <a name="pathgeneric_string"></a><a name="generic_string"></a>yol::generic_string

İleri `this->string<Elem, Traits, Alloc>(al)` eğik çizgiye dönüştürülen herhangi bir ters çizgi yle (Windows altında) döndürür.

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

## <a name="pathgeneric_u16string"></a><a name="generic_u16string"></a>yol::generic_u16string

İleri `u16string()` eğik çizgiye dönüştürülen herhangi bir ters çizgi yle (Windows altında) döndürür.

```cpp
u16string generic_u16string() const;
```

## <a name="pathgeneric_u32string"></a><a name="generic_u32string"></a>yol::generic_u32string

İleri `u32string()` eğik çizgiye dönüştürülen herhangi bir ters çizgi yle (Windows altında) döndürür.

```cpp
u32string generic_u32string() const;
```

## <a name="pathgeneric_u8string"></a><a name="generic_u8string"></a>yol::generic_u8string

İleri `u8string()` eğik çizgiye dönüştürülen herhangi bir ters çizgi yle (Windows altında) döndürür.

```cpp
string generic_u8string() const;
```

## <a name="pathgeneric_wstring"></a><a name="generic_wstring"></a>yol::generic_wstring

İleri `wstring()` eğik çizgiye dönüştürülen herhangi bir ters çizgi yle (Windows altında) döndürür.

```cpp
wstring generic_wstring() const;
```

## <a name="pathhas_extension"></a><a name="has_extension"></a>yol::has_extension

`!extension().empty()` döndürür.

```cpp
bool has_extension() const;
```

## <a name="pathhas_filename"></a><a name="has_filename"></a>yol::has_filename

`!filename().empty()` döndürür.

```cpp
bool has_filename() const;
```

## <a name="pathhas_parent_path"></a><a name="has_parent_path"></a>yol::has_parent_path

`!parent_path().empty()` döndürür.

```cpp
bool has_parent_path() const;
```

## <a name="pathhas_relative_path"></a><a name="has_relative_path"></a>yol::has_relative_path

`!relative_path().empty()` döndürür.

```cpp
bool has_relative_path() const;
```

## <a name="pathhas_root_directory"></a><a name="has_root_directory"></a>yol::has_root_directory

`!root_directory().empty()` döndürür.

```cpp
bool has_root_directory() const;
```

## <a name="pathhas_root_name"></a><a name="has_root_name"></a>yol::has_root_name

`!root_name().empty()` döndürür.

```cpp
bool has_root_name() const;
```

## <a name="pathhas_root_path"></a><a name="has_root_path"></a>yol::has_root_path

`!root_path().empty()` döndürür.

```cpp
bool has_root_path() const;
```

## <a name="pathhas_stem"></a><a name="has_stem"></a>yol::has_stem

`!stem().empty()` döndürür.

```cpp
bool has_stem() const;
```

## <a name="pathis_absolute"></a><a name="is_absolute"></a>yol::is_absolute

Windows için işlev `has_root_name() && has_root_directory()`döndürür. POSIX için işlev `has_root_directory()`döndürür.

```cpp
bool is_absolute() const;
```

## <a name="pathis_relative"></a><a name="is_relative"></a>yol::is_relative

`!is_absolute()` döndürür.

```cpp
bool is_relative() const;
```

## <a name="pathiterator"></a><a name="iterator"></a>yol::iterator

`myname`Yol bileşenlerini belirleyen çift yönlü sabit bir yineleme.

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

Sınıf, `path` `myname` dizideki bileşenleri belirleyen çift yönlü sabit bir yineleme açıklar:

1. varsa kök adı,

1. varsa kök dizini

1. üst `path`öğenin kalan dizin öğeleri , varsa, dosya adı ile biten, varsa

Türünden `pval` `path`bir nesne için:

1. `path::iterator X = pval.begin()`varsa, yol `path` adındaki ilk öğeyi belirtir.

1. `X == pval.end()`bileşenler dizisinin sonuna sadece geçmiş noktalar da `X` geçerlidir.

1. `*X`geçerli bileşenle eşleşen bir dize döndürür

1. `++X`varsa, dizideki bir sonraki bileşeni belirler.

1. `--X`varsa, dizideki önceki bileşeni belirler.

1. Değiştirerek, `myname` 'deki `myname`öğeleri ataen tüm yineleyiciler geçersiz kılın

## <a name="pathmake_preferred"></a><a name="make_preferred"></a>yol::make_preferred

Her ayırıcıyı gerektiği `preferred_separator` gibi bir ayırıcıya dönüştürür.

```cpp
path& make_preferred();
```

## <a name="pathnative"></a><a name="native"></a>yol::yerli

`myname` döndürür.

```cpp
const string_type& native() const noexcept;
```

## <a name="pathoperator"></a><a name="op_as"></a>yol::operator=

Yolun öğelerini başka bir yolun kopyasıyla değiştirir.

```cpp
path& operator=(const path& right);
path& operator=(path&& right) noexcept;

template <class Source>
path& operator=(const Source& source);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Kopyalanan `path` [yol.](../standard-library/path-class.md)

*Kaynak*\
Kaynak yolu.

### <a name="remarks"></a>Açıklamalar

İlk üye operatör `right.myname` kopyaları `myname`. İkinci üye `right.myname` `myname`operatör. Üçüncü üye operatör aynı `*this = path(source)`şekilde.

## <a name="pathoperator"></a><a name="op_add"></a>yol::operator+=

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

*Doğru*\
Eklenen yol.

*Str*\
Eklenen dize.

*Ptr*\
Eklenen işaretçi.

*Elem*\
Eklenen `value_type` veya `Elem`.

*Kaynak*\
Eklenen kaynak.

### <a name="remarks"></a>Açıklamalar

Üye işlevler aşağıdaki karşılık gelen ifadeler gibi çalışır:

1. `concat(right);`

1. `concat(path(str));`

1. `concat(ptr);`

1. `concat(string_type(1, elem));`

1. `concat(source);`

1. `concat(path(basic_string<Elem>(1, elem)));`

## <a name="pathoperator"></a><a name="op_divide"></a>yol::operator/=

Çeşitli `append` ifadeler.

```cpp
path& operator/=(const path& right);

template <class Source>
path& operator/=(const Source& source);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Eklenen yol.

*Kaynak*\
Eklenen kaynak.

### <a name="remarks"></a>Açıklamalar

Üye işlevler aşağıdaki karşılık gelen ifadeler gibi çalışır:

1. `append(right);`

1. `append(source);`

## <a name="pathoperator-string_type"></a><a name="op_string"></a>yol::operatör string_type

`myname` döndürür.

```cpp
operator string_type() const;
```

## <a name="pathparent_path"></a><a name="parent_path"></a>yol::parent_path

Üst yol bileşenini `myname`döndürür.

```cpp
path parent_path() const;
```

### <a name="remarks"></a>Açıklamalar

Ana yol bileşenini, `myname`özellikle çıkardıktan `myname` `filename().native()` sonra önek ve hemen önce gelen dizin ayırıcıları döndürür. (Eşit olarak, eğer, `begin() != end()`art arda uygulayarak `[begin(), --end())` `operator/=`aralığındaki tüm unsurların birleştirilmesidir .) Bileşen boş olabilir.

## <a name="pathpath"></a><a name="path"></a>yol::path

Çeşitli şekillerde `path` bir yapıinşa eder.

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

*Doğru*\
İnşa edilen yolun bir kopyası olması için bir yol.

*Kaynak*\
Hangi inşa yolu bir kopyası olmaktır kaynağı.

*Loc*\
Belirtilen yerel.

*Ilk*\
Kopyalanacak ilk öğenin konumu.

*Son*\
Kopyalanacak son öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Yapıcılar tüm çeşitli `myname` şekillerde inşa:

Çünkü `path()` öyle. `myname()`

Için `path(const path& right`) `myname(right.myname)`o .

Çünkü `path(path&& right)` öyle. `myname(right.myname)`

Çünkü `template<class Source> path(const Source& source)` öyle. `myname(source)`

Bunun `template<class Source> path(const Source& source, const locale& loc)` için `myname(source)`, herhangi bir gerekli codecvt `loc`fasedinme .

Çünkü `template<class InIt> path(InIt first, InIt last)` öyle. `myname(first, last)`

Bunun `template<class InIt> path(InIt first, InIt last, const locale& loc)` için `myname(first, last)`, herhangi bir gerekli codecvt `loc`fasedinme .

## <a name="pathpreferred_separator"></a><a name="preferred_separator"></a>yol::preferred_ayırıcı

Sabit nesne, ana bilgisayar işletim sistemine bağlı olarak yol bileşenlerini ayırmak için tercih edilen karakteri verir.

```cpp
#if _WIN32_C_LIB
static constexpr value_type preferred_separator == L'\\';
#else // assume POSIX
static constexpr value_type preferred_separator == '/';
#endif // filesystem model now defined
```

### <a name="remarks"></a>Açıklamalar

L'/'''''''''''yi yerine kullanmak Için Windows'un altındaki birçok bağlamda eşit şekilde izin verilebilir olduğunu unutmayın.

## <a name="pathrelative_path"></a><a name="relative_path"></a>yol::relative_path

Göreli yol bileşenini döndürür. `myname`

```cpp
path relative_path() const;
```

### <a name="remarks"></a>Açıklamalar

Nispi yol bileşenini, `myname`özellikle söktükten `myname` `root_path().native()` sonra sonek ve hemen sonraki gereksiz dizin ayırıcıları döndürür. Bileşen boş olabilir.

## <a name="pathremove_filename"></a><a name="remove_filename"></a>yol::remove_filename

Dosya adını kaldırır.

```cpp
path& remove_filename();
```

## <a name="pathreplace_extension"></a><a name="replace_extension"></a>yol::replace_extension

uzantısı nı `myname`değiştirir.

```cpp
path& replace_extension(const path& newext = path());
```

### <a name="parameters"></a>Parametreler

*newext*\
Yeni uzantı.

### <a name="remarks"></a>Açıklamalar

Önce sonek `extension().native()` kaldırır. `myname` Sonra `!newext.empty() && newext[0] != dot` eğer `dot` `*path(".").c_str()`(nerede), `dot` sonra `myname`eklenir. Sonra *newext* eklenir `myname`.

## <a name="pathreplace_filename"></a><a name="replace_filename"></a>yol::replace_filename

Dosya adını değiştirir.

```cpp
path& replace_filename(const path& pval);
```

### <a name="parameters"></a>Parametreler

*Pval*\
Dosya adının yolu.

### <a name="remarks"></a>Açıklamalar

Üye işlev yürütür:

```cpp
remove_filename();

*this /= pval;
return (*this);
```

## <a name="pathroot_directory"></a><a name="root_directory"></a>yol::root_directory

Kök dizin bileşenini `myname`döndürür.

```cpp
path root_directory() const;
```

### <a name="remarks"></a>Açıklamalar

Bileşen boş olabilir.

## <a name="pathroot_name"></a><a name="root_name"></a>yol::root_name

Kök ad bileşenini `myname`döndürür.

```cpp
path root_name() const;
```

### <a name="remarks"></a>Açıklamalar

Bileşen boş olabilir.

## <a name="pathroot_path"></a><a name="root_path"></a>yol::root_path

Kök yol bileşenini `myname`döndürür.

```cpp
path root_path() const;
```

### <a name="remarks"></a>Açıklamalar

Kök yol bileşenini `myname`verir, özellikle. `root_name()`  /  `root_directory` Bileşen boş olabilir.

## <a name="pathstem"></a><a name="stem"></a>yol::kök

`myname`Bileşenini `stem` verir.

```cpp
path stem() const;
```

### <a name="remarks"></a>Açıklamalar

Bileşenini, `stem` `myname`özellikle `filename().native()` herhangi bir `extension().native()` iz kaldırılan, verir. Bileşen boş olabilir.

## <a name="pathstring"></a><a name="string"></a>yol::string

Depolanan sırayı `mypath`dönüştürür.

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

### <a name="remarks"></a>Açıklamalar

İlk (şablon) üye işlev, depolanan `mypath` sırayı aşağıdaki gibi dönüştürür:

1. `string()`Için`string<char, Traits, Alloc>()`

1. `wstring()`Için`string<wchar_t, Traits, Alloc>()`

1. `u16string()`Için`string<char16_t, Traits, Alloc>()`

1. `u32string()`Için`string<char32_t, Traits, Alloc>()`

İkinci üye işlev, depolanan `mypath` sırayı **char** dizisi için ana bilgisayar sistemi tarafından tercih edilen kodlamaya dönüştürür `string`ve türünde bir nesnede depolanır.

## <a name="pathstring_type"></a><a name="string_type"></a>yol::string_type

Türü için `basic_string<value_type>`eşanlamlıdır.

```cpp
typedef basic_string<value_type> string_type;
```

## <a name="pathswap"></a><a name="swap"></a>yol::takas

Yürütür. `swap(mypath, right.mypath)`

```cpp
void swap(path& right) noexcept;
```

## <a name="pathu16string"></a><a name="u16string"></a>yol::u16string

DEPOLANAN sırayı `mypath` UTF-16'ya dönüştürür ve depolanan türünde `u16string`bir nesnede döndürür.

```cpp
u16string u16string() const;
```

## <a name="pathu32string"></a><a name="u32string"></a>yol::u32string

DEPOLANAN sırayı `mypath` UTF-32'ye dönüştürür ve depolanan türünde `u32string`bir nesnede döndürür.

```cpp
u32string u32string() const;
```

## <a name="pathu8string"></a><a name="u8string"></a>yol::u8string

Depolanan sırayı `mypath` UTF-8'e dönüştürür ve bir tür `u8string`nesnede depolanır.

```cpp
string u8string() const;
```

## <a name="pathvalue_type"></a><a name="value_type"></a>yol::value_type

Tür, ana `path` bilgisayar işletim sistemi tarafından tercih edilen öğeleri açıklar.

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume POSIX
typedef char value_type;
#endif // filesystem model now defined
```

## <a name="pathwstring"></a><a name="wstring"></a>yol::wstring

Depolanan `mypath` sırayı **wchar_t** dizisi için ana bilgisayar sistemi tarafından tercih edilen kodlamaya dönüştürür ve `wstring`bir tür nesnede depolanır.

```cpp
wstring wstring() const;
```

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)
