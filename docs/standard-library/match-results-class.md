---
title: match_results Sınıfı
ms.date: 09/10/2018
f1_keywords:
- regex/std::match_results
helpviewer_keywords:
- match_results class
ms.assetid: b504fdca-e5dd-429d-9960-6e27c9167fa6
ms.openlocfilehash: 32a5f9d20999740d4368f7901c797d87acce0be9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412975"
---
# <a name="matchresults-class"></a>match_results Sınıfı

Bir dizi alt eşleşmelerin tutar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class BidIt, class Alloc>
class match_results
```

## <a name="parameters"></a>Parametreler

*BidIt*<br/>
Alt eşleşmeleri için yineleyici türü.

*Ayırma*<br/>
Depolamayı yönetmek için bir ayırıcı türü.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı türü öğeler değiştirilebilir olmayan bir dizi denetleyen bir nesneyi tanımlayan `sub_match<BidIt>` bir normal ifade araması tarafından oluşturulur. Her öğenin o öğe için karşılık gelen yakalama grubuyla eşleşen alt diziyi işaret eder.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[match_results](#match_results)|Bir nesne oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Depolamayı yönetmek için bir ayırıcı türü.|
|[char_type](#char_type)|Öğenin türü.|
|[const_iterator](#const_iterator)|Alt eşleşmeleri için const yineleyici türü.|
|[const_reference](#const_reference)|Bir öğe const başvuru türü.|
|[difference_type](#difference_type)|Bir yineleyicinin fark türü.|
|[Yineleyici](#iterator)|Alt eşleşmeleri için yineleyici türü.|
|[Başvuru](#reference)|Bir öğe başvurusu türü.|
|[size_type](#size_type)|Alt eşleşme sayısı türü.|
|[string_type](#string_type)|Bir dize türü.|
|[value_type](#value_type)|Bir alt eşleşme türü.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[başlayın](#begin)|Alt eşleşme dizisi başlangıcını belirtir.|
|[boş](#empty)|Hiçbir alt eşleşmelerin sınar.|
|[Son](#end)|Alt eşleşme dizinin sonuna belirler.|
|[Biçim](#format)|Alt eşleşmeleri biçimlendirir.|
|[get_allocator](#get_allocator)|Depolanan ayırıcı döndürür.|
|[Uzunluğu](#length)|Bir alt eşleşme uzunluğunu döndürür.|
|[max_size](#max_size)|Alt eşleşmeleri en büyük sayısını alır.|
|[Konumu](#position)|Başlangıç uzaklığı bir alt alın.|
|[prefix](#prefix)|İlk alt eşleşme önce dizisini alır.|
|[Boyutu](#size)|Alt eşleşmelerin sayısını sayar.|
|[str](#str)|Bir alt eşleşme döndürür.|
|[suffix](#suffix)|Sonra son alt eşleşme dizisini alır.|
|[değiştirme](#swap)|İki match_results nesneleri değiştirir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Match_results nesne kopyalayın.|
|[İşleci\[\]](#op_at)|Bir alt nesneye erişim.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<regex >

**Namespace:** std

## <a name="example"></a>Örnek

```cpp
// std__regex__match_results.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
{
    std::regex rx("c(a*)|(b)");
    std::cmatch mr;

    std::regex_search("xcaaay", mr, rx);

    std::cout << "prefix: matched == " << std::boolalpha
        << mr.prefix().matched
        << ", value == " << mr.prefix() << std::endl;
    std::cout << "whole match: " << mr.length() << " chars, value == "
        << mr.str() << std::endl;
    std::cout << "suffix: matched == " << std::boolalpha
        << mr.suffix().matched
        << ", value == " << mr.suffix() << std::endl;
    std::cout << std::endl;

    std::string fmt("\"c(a*)|(b)\" matched \"$&\"\n"
        "\"(a*)\" matched \"$1\"\n"
        "\"(b)\" matched \"$2\"\n");
    std::cout << mr.format(fmt) << std::endl;
    std::cout << std::endl;

    // index through submatches
    for (size_t n = 0; n < mr.size(); ++n)
    {
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha
            << mr[n].matched <<
            " at position " << mr.position(n) << std::endl;
        std::cout << "  " << mr.length(n)
            << " chars, value == " << mr[n] << std::endl;
    }
    std::cout << std::endl;

    // iterate through submatches
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)
    {
        std::cout << "next submatch: matched == " << std::boolalpha
            << it->matched << std::endl;
        std::cout << "  " << it->length()
            << " chars, value == " << *it << std::endl;
    }
    std::cout << std::endl;

    // other members
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;

    std::cmatch::allocator_type al = mr.get_allocator();
    std::cmatch::string_type str = std::string("x");
    std::cmatch::size_type maxsiz = mr.max_size();
    std::cmatch::char_type ch = 'x';
    std::cmatch::difference_type dif = mr.begin() - mr.end();
    std::cmatch::const_iterator cit = mr.begin();
    std::cmatch::value_type val = *cit;
    std::cmatch::const_reference cref = val;
    std::cmatch::reference ref = val;

    maxsiz = maxsiz;  // to quiet "unused" warnings
    if (ref == cref)
        ch = ch;
    dif = dif;

    return (0);
}
```

```Output
prefix: matched == true, value == x
whole match: 4 chars, value == caaa
suffix: matched == true, value == y

"c(a*)|(b)" matched "caaa"
"(a*)" matched "aaa"
"(b)" matched ""

submatch[0]: matched == true at position 1
  4 chars, value == caaa
submatch[1]: matched == true at position 2
  3 chars, value == aaa
submatch[2]: matched == false at position 6
  0 chars, value ==

next submatch: matched == true
  4 chars, value == caaa
next submatch: matched == true
  3 chars, value == aaa
next submatch: matched == false
  0 chars, value ==

empty == false
```

## <a name="allocator_type"></a>  match_results::allocator_type

Depolamayı yönetmek için bir ayırıcı türü.

```cpp
typedef Alloc allocator_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef şablon bağımsız değişkeni eşanlamlıdır *ayırma*.

## <a name="begin"></a>  match_results::begin

Alt eşleşme dizisi başlangıcını belirtir.

```cpp
const_iterator begin() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi bu noktalarda ilk öğe dizisi (veya yalnızca boş bir dizi bitiminin ötesinde) bir rastgele erişim yineleyici döndürür.

## <a name="char_type"></a>  match_results::char_type

Öğenin türü.

```cpp
typedef typename iterator_traits<BidIt>::value_type char_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef türü eşanlamlıdır `iterator_traits<BidIt>::value_type`, aranan karakter dizisi ' öğe türü.

## <a name="const_iterator"></a>  match_results::const_iterator

Alt eşleşmeleri için const yineleyici türü.

```cpp
typedef T0 const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Typedef, denetlenen dizi için sabit bir rastgele erişim yineleyici olarak hizmet verebilen bir nesneyi tanımlar.

## <a name="const_reference"></a>  match_results::const_reference

Bir öğe const başvuru türü.

```cpp
typedef const typename Alloc::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

Typedef değerinin denetlenen dizideki bir öğe için sabit bir başvuru olarak hizmet verebilen bir nesneyi tanımlar.

## <a name="difference_type"></a>  match_results::difference_type

Bir yineleyicinin fark türü.

```cpp
typedef typename iterator_traits<BidIt>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef türü eşanlamlıdır `iterator_traits<BidIt>::difference_type`; değerinin denetlenen dizideki öğeler işaret herhangi iki yineleyici arasındaki farkı temsil edebilen bir nesneyi tanımlar.

## <a name="empty"></a>  match_results::empty

Hiçbir alt eşleşmelerin sınar.

```cpp
bool empty() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, yalnızca normal ifade araması başarısız olduysa true değerini döndürür.

## <a name="end"></a>  match_results::end

Alt eşleşme dizinin sonuna belirler.

```cpp
const_iterator end() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, dizinin sonuna hemen ötesine işaret eden bir yineleyici döndürür.

## <a name="format"></a>  match_results::format

Alt eşleşmeleri biçimlendirir.

```cpp
template <class OutIt>
OutIt format(OutIt out,
    const string_type& fmt, match_flag_type flags = format_default) const;

string_type format(const string_type& fmt, match_flag_type flags = format_default) const;
```

### <a name="parameters"></a>Parametreler

*OutIt*<br/>
Çıkış yineleyici türü.

*out*<br/>
Yazılacak çıkış akışı.

*FMT*<br/>
Biçim dizesi.

*bayrakları*<br/>
Biçim bayrakları.

### <a name="remarks"></a>Açıklamalar

Her üye işlevi biçiminin denetiminde biçimlendirilmiş metin üretir *fmt*. İlk üye işlevi biçimlendirilmiş metnin bağımsız değişkeni tarafından tanımlanan diziye Yazar *kullanıma* ve döndürür *kullanıma*. İkinci üye işlevi biçimlendirilmiş metnin bir kopyasını tutarak bir dize nesnesi döndürür.

Biçimlendirilmiş metin oluşturmak için. Biçim dizesindeki değişmez metin normalde hedef dizisine kopyalanır. Biçim dizesindeki her çıkış dizisi temsil ettiği metin tarafından değiştirilir. Kopyalama ve değiştirmeyle ilgili ayrıntılar işleve geçirilen biçim bayrakları tarafından denetlenir.

## <a name="get_allocator"></a>  match_results::get_allocator

Depolanan ayırıcı döndürür.

```cpp
allocator_type get_allocator() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi tarafından kullanılan ayırıcı nesnesinin bir kopyasını döndürür `*this` ayırmak için kendi `sub_match` nesneleri.

## <a name="iterator"></a>  match_results::iterator

Alt eşleşmeleri için yineleyici türü.

```cpp
typedef const_iterator iterator;
```

### <a name="remarks"></a>Açıklamalar

Denetlenen dizi için bir rastgele erişim yineleyici olarak hizmet verebilen bir nesneyi tanımlayan bir tür.

## <a name="length"></a>  match_results::length

Bir alt eşleşme uzunluğunu döndürür.

```cpp
difference_type length(size_type sub = 0) const;
```

### <a name="parameters"></a>Parametreler

*alt*<br/>
Alt eşleşme dizini.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü `(*this)[sub].length()`.

## <a name="match_results"></a>  match_results::match_results

Bir nesne oluşturur.

```cpp
explicit match_results(const Alloc& alloc = Alloc());

match_results(const match_results& right);
```

### <a name="parameters"></a>Parametreler

*Ayırma*<br/>
Depolanacak ayırıcı nesne.

*sağ*<br/>
Kopyalanacak match_results nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu yapıları bir `match_results` hiçbir alt eşleşmelerin tutan nesne. İkinci oluşturucu yapıları bir `match_results` bir kopyasını nesnesini *doğru*.

## <a name="max_size"></a>  match_results::max_size

Alt eşleşmeleri en büyük sayısını alır.

```cpp
size_type max_size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, nesneyi de denetleyebilir kastetmek uzunluğunu döndürür.

## <a name="op_eq"></a>  match_results::operator =

Match_results nesne kopyalayın.

```cpp
match_results& operator=(const match_results& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Kopyalanacak match_results nesne.

### <a name="remarks"></a>Açıklamalar

Üye işleci tarafından denetlenen dizinin değiştirir `*this` tarafından denetlenen dizinin bir kopyasını *doğru*.

## <a name="op_at"></a>  match_results::operator[]

Bir alt nesneye erişim.

```cpp
const_reference operator[](size_type n) const;
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Alt eşleşme dizini.

### <a name="remarks"></a>Açıklamalar

Üye işlevi öğeye bir başvuru döndürür *n* denetlenen dizi ya da boş bir başvuru `sub_match` , nesne `size() <= n` veya yakalama grubu *n* eşleşmenin bir parçası değildi.

## <a name="position"></a>  match_results::position

Başlangıç uzaklığı bir alt alın.

```cpp
difference_type position(size_type sub = 0) const;
```

### <a name="parameters"></a>Parametreler

*alt*<br/>
Alt eşleşme dizini.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü `std::distance(prefix().first, (*this)[sub].first)`, diğer bir deyişle, ilk karakter, alt eşleşme için hedef dizideki ilk karakteri uzaklığı işaret edilen öğe tarafından `n` denetlenen dizinin.

## <a name="prefix"></a>  match_results::prefix

İlk alt eşleşme önce dizisini alır.

```cpp
const_reference prefix() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi bir başvuru türü bir nesne döndürür `sub_match<BidIt>` işaret eden hedef dizideki başlangıcında başlar ve biter karakter dizisi `(*this)[0].first`, diğer bir deyişle, eşleşen alt diziyi önündeki metne işaret eder.

## <a name="reference"></a>  match_results::reference

Bir öğe başvurusu türü.

```cpp
typedef const_reference reference;
```

### <a name="remarks"></a>Açıklamalar

Türe ilişkin bir eşanlam türüdür `const_reference`.

## <a name="size"></a>  match_results::size

Alt eşleşmelerin sayısını sayar.

```cpp
size_type size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye araması için kullanılan normal ifadedeki yakalama gruplarının sayısı'birden fazla döndürür bir işlev veya arama yaptıysanız sıfır.

## <a name="size_type"></a>  match_results::size_type

Alt eşleşme sayısı türü.

```cpp
typedef typename Alloc::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

Türe ilişkin bir eşanlam türüdür `Alloc::size_type`.

## <a name="str"></a>  match_results::str

Bir alt eşleşme döndürür.

```cpp
string_type str(size_type sub = 0) const;
```

### <a name="parameters"></a>Parametreler

*alt*<br/>
Alt eşleşme dizini.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü `string_type((*this)[sub])`.

## <a name="string_type"></a>  match_results::string_type

Bir dize türü.

```cpp
typedef basic_string<char_type> string_type;
```

### <a name="remarks"></a>Açıklamalar

Türe ilişkin bir eşanlam türüdür `basic_string<char_type>`.

## <a name="suffix"></a>  match_results::suffix

Sonra son alt eşleşme dizisini alır.

```cpp
const_reference suffix() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi bir başvuru türü bir nesne döndürür `sub_match<BidIt>` işaret eden başlangıcı karakter dizisi `(*this)[size() - 1].second` ve diğer bir deyişle, hedef dizinin sonuna uçta eşleşen alt diziyi takip metne işaret.

## <a name="swap"></a>  match_results::swap

İki match_results nesneleri değiştirir.

```cpp
void swap(const match_results& right) throw();
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
İle takas match_results nesne.

### <a name="remarks"></a>Açıklamalar

Üye işlevi içeriğini değiştirir `*this` ve *doğru* sabit zamanlı ve özel durum oluşturmaz.

## <a name="value_type"></a>  match_results::value_type

Bir alt eşleşme türü.

```cpp
typedef sub_match<BidIt> value_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef türü eşanlamlıdır `sub_match<BidIt>`.

## <a name="see-also"></a>Ayrıca bkz.

[\<Regex >](../standard-library/regex.md)<br/>
