---
title: path Sınıfı
ms.date: 09/27/2018
f1_keywords:
- filesystem/std::experimental::filesystem::path
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
ms.openlocfilehash: d7c8c739c3d235383ede0509cfa87b41200efeca
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233008"
---
# <a name="path-class"></a>path Sınıfı

**Path** sınıfı, `string_type` `myname` bir yol adı olarak kullanım için uygun şekilde, burada çağrılan,,, bir nesne türü içerir. `string_type`, için bir eş anladır `basic_string<value_type>` , burada `value_type` **`wchar_t`** Windows veya POSIX üzerinde için bir eş anlamlı olur **`char`** .

Daha fazla bilgi ve kod örnekleri için bkz. [dosya sistemi Gezintisi (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class path;
```

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Yolun](#path)|Bir oluşturur `path` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[const_iterator](#const_iterator)|İçin bir eş anlamlı `iterator` .|
|[iden](#iterator)|Bileşenlerini atayan çift yönlü bir sabit Yineleyici `path` `myname` .|
|[string_type](#string_type)|Tür için bir eş anlamlı `basic_string<value_type>` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[ýna](#append)|Gerektiğinde belirtilen diziyi ekler `mypath` , dönüştürülür ve preferred_separator ekler.|
|[assign (atamak)](#assign) |`mypath`Gerektiğinde, belirtilen sırayla değiştirilir.|
|[başladı](#begin)|Varsa `path::iterator` , PATHNAME içindeki ilk yol öğesini bir belirleme döndürür.|
|[c_str](#c_str)|İçindeki ilk karaktere bir işaretçi döndürür `mypath` .|
|[lediğiniz](#clear)|Yürütülür `mypath.clear()` .|
|[Karşılaştır](#compare)|Karşılaştırma değerlerini döndürür.|
|[Concat](#compare)|`mypath`Gerektiğinde, dönüştürülmüş (ayırıcı eklemek değil) belirtilen diziyi ekler.|
|[empty](#empty)|`mypath.empty()` döndürür.|
|[erer](#end)|Türünde bir dizi sonu yineleyiciyi döndürür `iterator` .|
|[uzantının](#extension)|Sonekini döndürür `filename()` .|
|[filename](#filename)|Özel olarak myname kök dizin bileşenini döndürür `empty() path() : *--end()` . Bileşen boş olabilir.|
|[generic_string](#generic_string)|`this->string<Elem, Traits, Alloc>(al)`İle (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.|
|[generic_u16string](#generic_u16string)|`u16string()`İle (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.|
|[generic_u32string](#generic_u32string)|`u32string()`İle (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.|
|[generic_u8string](#generic_u8string)|`u8string()`İle (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.|
|[generic_wstring](#generic_wstring)|`wstring()`İle (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.|
|[has_extension](#has_extension)|`!extension().empty()` döndürür.|
|[has_filename](#has_filename)|`!filename().empty()` döndürür.|
|[has_parent_path](#has_parent_path)|`!parent_path().empty()` döndürür.|
|[has_relative_path](#has_relative_path)|`!relative_path().empty()` döndürür.|
|[has_root_directory](#has_root_directory)|`!root_directory().empty()` döndürür.|
|[has_root_name](#has_root_name)|`!root_name().empty()` döndürür.|
|[has_root_path](#has_root_path)|`!root_path().empty()` döndürür.|
|[has_stem](#has_stem)|`!stem().empty()` döndürür.|
|[is_absolute](#is_absolute)|Windows için işlev döndürür `has_root_name() && has_root_directory()` . POSIX için, işlev döndürür `has_root_directory()` .|
|[is_relative](#is_relative)|`!is_absolute()` döndürür.|
|[make_preferred](#make_preferred)|Her ayırıcıyı gerektiğinde preferred_separator dönüştürür.|
|[native (yerel)](#native) |`myname` döndürür.|
|[parent_path](#parent_path)|Öğesinin üst yol bileşenini döndürür `myname` .|
|[preferred_separator](#preferred_separator)|Sabit nesne, ana bilgisayar işletim sistemine bağlı olarak yol bileşenlerini ayırmak için tercih edilen karakteri verir. |
|[relative_path](#relative_path)|Göreli yol bileşenini döndürür `myname` . |
|[remove_filename](#remove_filename)|Dosya adını kaldırır.|
|[replace_extension](#replace_extension)|Uzantısının yerini alır `myname` . |
|[replace_filename](#replace_filename)|RBu dosya adını alır.|
|[root_directory](#root_directory)|Kök dizin bileşenini döndürür `myname` . |
|[root_name](#root_name)|Kök adı bileşenini döndürür `myname` . |
|[root_path](#root_path)|Kök yolu bileşenini döndürür `myname` .|
|[stem](#stem)|Bileşenini döndürür `stem` `myname` .|
|[dizisinde](#string)|İçinde depolanan sırayı dönüştürür `mypath` .|
|[Kur](#swap)|Yürütülür `swap(mypath, right.mypath)` .|
|[u16string](#u16string)|İçinde depolanan diziyi `mypath` UTF-16 ' a dönüştürür ve türündeki bir nesne içinde depolanmış şekilde döndürür `u16string` .|
|[u32string](#u32string)|İçinde depolanan diziyi `mypath` UTF-32 ' a dönüştürür ve türündeki bir nesne içinde depolanmış şekilde döndürür `u32string` .|
|[u8string](#u8string)|İçinde depolanan diziyi `mypath` UTF-8 ' e dönüştürür ve türünde bir nesne içinde depolanmış şekilde döndürür `u8string` .|
|[value_type](#value_type)|Bu tür, ana bilgisayar işletim sistemi tarafından sık kırmızı yol öğelerini tanımlar.|
|[wstring](#wstring)|İçinde depolanan sırayı, `mypath` ana bilgisayar sistemi tarafından bir sıra için sık kırmızı kodlamaya dönüştürür **`wchar_t`** ve türündeki bir nesneye depolanmış şekilde döndürür `wstring` .|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_as)|Yolun öğelerini başka bir yolun kopyasıyla değiştirir.|
|[işleç + =](#op_add)|Çeşitli `concat` ifadeler.|
|[işleç/=](#op_divide)|Çeşitli `append` ifadeler.|
|[işleç string_type](#op_string)|`myname` döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<filesystem>

**Ad alanı:** std:: deneysel:: FileSystem

## <a name="pathappend"></a><a name="append"></a>path:: Append

Belirtilen diziyi `mypath` , dönüştürülecek ve `preferred_separator` gereken şekilde sonuna ekler.

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

## <a name="pathassign"></a><a name="assign"></a>path:: Assign

`mypath`Gerektiğinde, belirtilen sırayla değiştirilir.

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

## <a name="pathbegin"></a><a name="begin"></a>path:: Begin

Varsa `path::iterator` , PATHNAME içindeki ilk yol öğesini bir belirleme döndürür.

```cpp
iterator begin() const;
```

## <a name="pathc_str"></a><a name="c_str"></a>yol:: c_str

İçindeki ilk karaktere bir işaretçi döndürür `mypath` .

```cpp
const value_type& *c_str() const noexcept;
```

## <a name="pathclear"></a><a name="clear"></a>path:: Clear

Yürütülür `mypath.clear()` .

```cpp
void clear() noexcept;
```

## <a name="pathcompare"></a><a name="compare"></a>path:: Compare

İlk işlev döndürür `mypath.compare(pval.native())` . İkinci işlev döndürür `mypath.compare(str)` . Üçüncü işlev döndürür `mypath.compare(ptr)` .

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

## <a name="pathconcat"></a><a name="concat"></a>path:: Concat

`mypath`Gerektiğinde, dönüştürülmüş (ayırıcı eklemek değil) belirtilen diziyi ekler.

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

## <a name="pathconst_iterator"></a><a name="const_iterator"></a>yol:: const_iterator

İçin bir eş anlamlı `iterator` .

```cpp
typedef iterator const_iterator;
```

## <a name="pathempty"></a><a name="empty"></a>path:: Empty

`mypath.empty()` döndürür.

```cpp
bool empty() const noexcept;
```

## <a name="pathend"></a><a name="end"></a>path:: End

Türünde bir dizi sonu yineleyiciyi döndürür `iterator` .

```cpp
iterator end() const;
```

## <a name="pathextension"></a><a name="extension"></a>path:: Extension

Sonekini döndürür `filename()` .

```cpp
path extension() const;
```

### <a name="remarks"></a>Açıklamalar

Şu şekilde sonek döndürür `filename() X` :

`X == path(".") || X == path("..")`Ya da `X` nokta içermiyorsa, sonek boştur.

Aksi takdirde, sonek en sağdaki noktayı (ve içerir) ile başlar.

## <a name="pathfilename"></a><a name="filename"></a>yol:: filename

Özel olarak myname kök dizin bileşenini döndürür `empty() path() : *--end()` . Bileşen boş olabilir.

```cpp
path filename() const;
```

## <a name="pathgeneric_string"></a><a name="generic_string"></a>yol:: generic_string

`this->string<Elem, Traits, Alloc>(al)`İle (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

## <a name="pathgeneric_u16string"></a><a name="generic_u16string"></a>yol:: generic_u16string

`u16string()`İle (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.

```cpp
u16string generic_u16string() const;
```

## <a name="pathgeneric_u32string"></a><a name="generic_u32string"></a>yol:: generic_u32string

`u32string()`İle (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.

```cpp
u32string generic_u32string() const;
```

## <a name="pathgeneric_u8string"></a><a name="generic_u8string"></a>yol:: generic_u8string

`u8string()`İle (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.

```cpp
string generic_u8string() const;
```

## <a name="pathgeneric_wstring"></a><a name="generic_wstring"></a>yol:: generic_wstring

`wstring()`İle (Windows 'un altında) eğik çizgiye dönüştürülecek ters eğik çizgi döndürür.

```cpp
wstring generic_wstring() const;
```

## <a name="pathhas_extension"></a><a name="has_extension"></a>yol:: has_extension

`!extension().empty()` döndürür.

```cpp
bool has_extension() const;
```

## <a name="pathhas_filename"></a><a name="has_filename"></a>yol:: has_filename

`!filename().empty()` döndürür.

```cpp
bool has_filename() const;
```

## <a name="pathhas_parent_path"></a><a name="has_parent_path"></a>yol:: has_parent_path

`!parent_path().empty()` döndürür.

```cpp
bool has_parent_path() const;
```

## <a name="pathhas_relative_path"></a><a name="has_relative_path"></a>yol:: has_relative_path

`!relative_path().empty()` döndürür.

```cpp
bool has_relative_path() const;
```

## <a name="pathhas_root_directory"></a><a name="has_root_directory"></a>yol:: has_root_directory

`!root_directory().empty()` döndürür.

```cpp
bool has_root_directory() const;
```

## <a name="pathhas_root_name"></a><a name="has_root_name"></a>yol:: has_root_name

`!root_name().empty()` döndürür.

```cpp
bool has_root_name() const;
```

## <a name="pathhas_root_path"></a><a name="has_root_path"></a>yol:: has_root_path

`!root_path().empty()` döndürür.

```cpp
bool has_root_path() const;
```

## <a name="pathhas_stem"></a><a name="has_stem"></a>yol:: has_stem

`!stem().empty()` döndürür.

```cpp
bool has_stem() const;
```

## <a name="pathis_absolute"></a><a name="is_absolute"></a>yol:: is_absolute

Windows için işlev döndürür `has_root_name() && has_root_directory()` . POSIX için, işlev döndürür `has_root_directory()` .

```cpp
bool is_absolute() const;
```

## <a name="pathis_relative"></a><a name="is_relative"></a>yol:: is_relative

`!is_absolute()` döndürür.

```cpp
bool is_relative() const;
```

## <a name="pathiterator"></a><a name="iterator"></a>yol:: Yineleyici

Yol bileşenlerini atayan çift yönlü bir sabit Yineleyici `myname` .

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

Sınıfı, dizideki bileşenleri atayan çift yönlü bir sabit yineleyiciyi açıklar `path` `myname` :

1. varsa kök adı

1. varsa kök dizin

1. varsa, üst öğenin kalan dizin öğeleri, varsa `path` dosya adıyla biter

Şu `pval` türde bir nesne için `path` :

1. `path::iterator X = pval.begin()`varsa `path` , PATHNAME içindeki ilk öğeyi belirler.

1. `X == pval.end()`, `X` bileşen dizisinin sonundan hemen sonra işaret ettiği zaman geçerlidir.

1. `*X`geçerli bileşenle eşleşen bir dize döndürür

1. `++X`varsa dizideki sonraki bileşeni belirler.

1. `--X`varsa, dizideki önceki bileşeni belirler.

1. Değiştirme `myname` , içindeki öğeleri tanımlayarak tüm yineleyiciler geçersiz kılar `myname` .

## <a name="pathmake_preferred"></a><a name="make_preferred"></a>yol:: make_preferred

Her ayırıcıyı gerektiğinde bir öğesine dönüştürür `preferred_separator` .

```cpp
path& make_preferred();
```

## <a name="pathnative"></a><a name="native"></a>path:: Native

`myname` döndürür.

```cpp
const string_type& native() const noexcept;
```

## <a name="pathoperator"></a><a name="op_as"></a>path:: operator =

Yolun öğelerini başka bir yolun kopyasıyla değiştirir.

```cpp
path& operator=(const path& right);
path& operator=(path&& right) noexcept;

template <class Source>
path& operator=(const Source& source);
```

### <a name="parameters"></a>Parametreler

*Right*\
İçine Kopyalanmakta olan [yol](../standard-library/path-class.md) `path` .

*kaynaktaki*\
Kaynak yolu.

### <a name="remarks"></a>Açıklamalar

İlk üye işleci öğesine kopyalar `right.myname` `myname` . İkinci üye işleci öğesine gider `right.myname` `myname` . Üçüncü üye işleci ile aynı şekilde davranır `*this = path(source)` .

## <a name="pathoperator"></a><a name="op_add"></a>path:: operator + =

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
Eklendi `value_type` veya `Elem` .

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

## <a name="pathoperator"></a><a name="op_divide"></a>path:: operator/=

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

## <a name="pathoperator-string_type"></a><a name="op_string"></a>path:: operator string_type

`myname` döndürür.

```cpp
operator string_type() const;
```

## <a name="pathparent_path"></a><a name="parent_path"></a>yol::p arent_path

Öğesinin üst yol bileşenini döndürür `myname` .

```cpp
path parent_path() const;
```

### <a name="remarks"></a>Açıklamalar

Öğesinin üst yol bileşenini `myname` , özellikle `myname` kaldırıldıktan sonra öneki `filename().native()` ve hemen önceki Dizin ayırıcılarını döndürür. (Eşit olarak, ise `begin() != end()` , Aralık içindeki tüm öğelerin birleştirilme, büyük ölçüde `[begin(), --end())` uygulanmasıyla yapılır `operator/=` .) Bileşen boş olabilir.

## <a name="pathpath"></a><a name="path"></a>yol::p m

`path`Çeşitli şekillerde oluşturur.

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

`path()`Bunun için `myname()` .

İçin `path(const path& right` ) `myname(right.myname)` .

`path(path&& right)`Bunun için `myname(right.myname)` .

`template<class Source> path(const Source& source)`Bunun için `myname(source)` .

`template<class Source> path(const Source& source, const locale& loc)`Bunun için `myname(source)` , ' den gereken codecvt modellerini elde edin `loc` .

`template<class InIt> path(InIt first, InIt last)`Bunun için `myname(first, last)` .

`template<class InIt> path(InIt first, InIt last, const locale& loc)`Bunun için `myname(first, last)` , ' den gereken codecvt modellerini elde edin `loc` .

## <a name="pathpreferred_separator"></a><a name="preferred_separator"></a>yol::p referred_separator

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

## <a name="pathrelative_path"></a><a name="relative_path"></a>yol:: relative_path

Göreli yol bileşenini döndürür `myname` .

```cpp
path relative_path() const;
```

### <a name="remarks"></a>Açıklamalar

Öğesinin göreli yol bileşenini `myname` , özellikle `myname` kaldırıldıktan sonra `root_path().native()` ve bundan sonraki tüm yedekli Dizin ayırıcıları döndürür. Bileşen boş olabilir.

## <a name="pathremove_filename"></a><a name="remove_filename"></a>yol:: remove_filename

Dosya adını kaldırır.

```cpp
path& remove_filename();
```

## <a name="pathreplace_extension"></a><a name="replace_extension"></a>yol:: replace_extension

Uzantısının yerini alır `myname` .

```cpp
path& replace_extension(const path& newext = path());
```

### <a name="parameters"></a>Parametreler

*newext*\
Yeni uzantı.

### <a name="remarks"></a>Açıklamalar

Önce son eki `extension().native()` öğesinden kaldırır `myname` . Sonra `!newext.empty() && newext[0] != dot` (nerede olursa `dot` `*path(".").c_str()` ), `dot` öğesine eklenir `myname` . Ardından *newext* öğesine eklenir `myname` .

## <a name="pathreplace_filename"></a><a name="replace_filename"></a>yol:: replace_filename

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

## <a name="pathroot_directory"></a><a name="root_directory"></a>yol:: root_directory

Kök dizin bileşenini döndürür `myname` .

```cpp
path root_directory() const;
```

### <a name="remarks"></a>Açıklamalar

Bileşen boş olabilir.

## <a name="pathroot_name"></a><a name="root_name"></a>yol:: root_name

Kök adı bileşenini döndürür `myname` .

```cpp
path root_name() const;
```

### <a name="remarks"></a>Açıklamalar

Bileşen boş olabilir.

## <a name="pathroot_path"></a><a name="root_path"></a>yol:: root_path

Kök yolu bileşenini döndürür `myname` .

```cpp
path root_path() const;
```

### <a name="remarks"></a>Açıklamalar

, Özel olarak öğesinin kök yolu bileşenini döndürür `myname` `root_name()`  /  `root_directory` . Bileşen boş olabilir.

## <a name="pathstem"></a><a name="stem"></a>path:: stem

Bileşenini döndürür `stem` `myname` .

```cpp
path stem() const;
```

### <a name="remarks"></a>Açıklamalar

`stem` `myname` , Özellikle de `filename().native()` sondaki kaldırılmış olan bileşenini döndürür `extension().native()` . Bileşen boş olabilir.

## <a name="pathstring"></a><a name="string"></a>path:: String

İçinde depolanan sırayı dönüştürür `mypath` .

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

### <a name="remarks"></a>Açıklamalar

İlk (Template) üye işlevi, depolanan sırayı `mypath` aynı şekilde dönüştürür:

1. `string()`bekleniyor`string<char, Traits, Alloc>()`

1. `wstring()`bekleniyor`string<wchar_t, Traits, Alloc>()`

1. `u16string()`bekleniyor`string<char16_t, Traits, Alloc>()`

1. `u32string()`bekleniyor`string<char32_t, Traits, Alloc>()`

İkinci üye işlevi, içinde depolanan sırayı, `mypath` ana bilgisayar sistemi tarafından bir sıra için sık kırmızı kodlamaya dönüştürür **`char`** ve türündeki bir nesneye depolanmış şekilde döndürür `string` .

## <a name="pathstring_type"></a><a name="string_type"></a>yol:: string_type

Tür için bir eş anlamlı `basic_string<value_type>` .

```cpp
typedef basic_string<value_type> string_type;
```

## <a name="pathswap"></a><a name="swap"></a>path:: swap

Yürütülür `swap(mypath, right.mypath)` .

```cpp
void swap(path& right) noexcept;
```

## <a name="pathu16string"></a><a name="u16string"></a>yol:: u16string

İçinde depolanan diziyi `mypath` UTF-16 ' a dönüştürür ve türündeki bir nesne içinde depolanmış şekilde döndürür `u16string` .

```cpp
u16string u16string() const;
```

## <a name="pathu32string"></a><a name="u32string"></a>yol:: u32string

İçinde depolanan diziyi `mypath` UTF-32 ' a dönüştürür ve türündeki bir nesne içinde depolanmış şekilde döndürür `u32string` .

```cpp
u32string u32string() const;
```

## <a name="pathu8string"></a><a name="u8string"></a>yol:: u8string

İçinde depolanan diziyi `mypath` UTF-8 ' e dönüştürür ve türünde bir nesne içinde depolanmış şekilde döndürür `u8string` .

```cpp
string u8string() const;
```

## <a name="pathvalue_type"></a><a name="value_type"></a>yol:: value_type

Türü, `path` ana bilgisayar işletim sistemi tarafından sık kırmızı olan öğeleri tanımlar.

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume POSIX
typedef char value_type;
#endif // filesystem model now defined
```

## <a name="pathwstring"></a><a name="wstring"></a>path:: wstring

İçinde depolanan sırayı, `mypath` ana bilgisayar sistemi tarafından bir sıra için sık kırmızı kodlamaya dönüştürür **`wchar_t`** ve türündeki bir nesneye depolanmış şekilde döndürür `wstring` .

```cpp
wstring wstring() const;
```

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
