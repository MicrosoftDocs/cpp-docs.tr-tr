---
title: match_results Sınıfı
ms.date: 09/10/2018
f1_keywords:
- regex/std::match_results
helpviewer_keywords:
- match_results class
ms.assetid: b504fdca-e5dd-429d-9960-6e27c9167fa6
ms.openlocfilehash: 31154a38f8bbcb879fd871f1eb1bf5a4b15af79b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371017"
---
# <a name="match_results-class"></a>match_results Sınıfı

Bir alt eşleşme dizisi tutar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class BidIt, class Alloc>
class match_results
```

## <a name="parameters"></a>Parametreler

*BidIt*\
Alt eşleşmeler için yineleyici türü.

*Ayırma*\
Depolamayı yönetmek için bir ayırıcı türü.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, normal bir ifade araması tarafından oluşturulan `sub_match<BidIt>` tür öğelerinin değiştirilemez sırasını denetleyen bir nesneyi açıklar. Her öğe, bu öğeye karşılık gelen yakalama grubuyla eşleşen alt diziyi işaret eder.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Match_results](#match_results)|Nesneyi inşa eder.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Allocator_type](#allocator_type)|Depolamayı yönetmek için bir ayırıcı türü.|
|[Char_type](#char_type)|Öğenin türü.|
|[const_iterator](#const_iterator)|Alt eşleşmeler için const yineleyici türü.|
|[const_reference](#const_reference)|Bir öğe const başvuru türü.|
|[difference_type](#difference_type)|Yineleyici farkının türü.|
|[Yineleyici](#iterator)|Alt eşleşmeler için yineleyici türü.|
|[Başvuru](#reference)|Öğe başvurusu türü.|
|[size_type](#size_type)|Alt eşleşme sayısı türü.|
|[string_type](#string_type)|Bir dize türü.|
|[value_type](#value_type)|Alt eşleşme türü.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Başlamak](#begin)|Alt eşleşme sırasının başlangıcını belirtir.|
|[empty](#empty)|Alt eşleşmeler için testler.|
|[Son -unda](#end)|Alt eşleşme dizisinin sonunu belirtir.|
|[Biçim](#format)|Alt eşleşmeleri biçimlendirir.|
|[Get_allocator](#get_allocator)|Depolanan ayırıcıyı döndürür.|
|[Uzun -luğu](#length)|Bir alt eşleşmenin uzunluğunu döndürür.|
|[max_size](#max_size)|En fazla sayıda alt eşleşme alır.|
|[Konum](#position)|Bir alt grubun ofset'ini başlatın.|
|[Önek](#prefix)|İlk alt eşleşmeden önce sıra alır.|
|[Boyutu](#size)|Alt eşleşme sayısını sayar.|
|[Str](#str)|Bir alt eşleşme döndürür.|
|[Soneki](#suffix)|Son alt eşleşmeden sonra sıraalır.|
|[Takas](#swap)|İki match_results nesnedeğiştirir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç=](#op_eq)|match_results bir nesneyi kopyalayın.|
|[Işleç\[\]](#op_at)|Bir alt nesneye erişin.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<regex>

**Ad alanı:** std

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

## <a name="match_resultsallocator_type"></a><a name="allocator_type"></a>match_results:allocator_type

Depolamayı yönetmek için bir ayırıcı türü.

```cpp
typedef Alloc allocator_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef şablon argümanı *Alloc*için eşanlamlıdır.

## <a name="match_resultsbegin"></a><a name="begin"></a>match_results::başla

Alt eşleşme sırasının başlangıcını belirtir.

```cpp
const_iterator begin() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, dizinin ilk öğesini (veya boş bir dizinin sonundan hemen sonra) işaret eden rasgele bir erişim yinelemesi döndürür.

## <a name="match_resultschar_type"></a><a name="char_type"></a>match_results:char_type

Öğenin türü.

```cpp
typedef typename iterator_traits<BidIt>::value_type char_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef, aranan karakter dizisinin öğe `iterator_traits<BidIt>::value_type`türü olan türüyle eş anlamlıdır.

## <a name="match_resultsconst_iterator"></a><a name="const_iterator"></a>match_results:const_iterator

Alt eşleşmeler için const yineleyici türü.

```cpp
typedef T0 const_iterator;
```

### <a name="remarks"></a>Açıklamalar

Typedef, denetlenen dizi için sabit bir rasgele erişim yinelemesi olarak hizmet verebilen bir nesneyi açıklar.

## <a name="match_resultsconst_reference"></a><a name="const_reference"></a>match_results::const_reference

Bir öğe const başvuru türü.

```cpp
typedef const typename Alloc::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

Typedef, denetlenen dizinin bir öğesine sabit bir başvuru olarak hizmet verebilecek bir nesneyi açıklar.

## <a name="match_resultsdifference_type"></a><a name="difference_type"></a>match_results::difference_type

Yineleyici farkının türü.

```cpp
typedef typename iterator_traits<BidIt>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef türü `iterator_traits<BidIt>::difference_type`için eşanlamlıdır; denetite dizisinin öğelerini işaret eden herhangi iki yineleyici arasındaki farkı temsil eden bir nesneyi açıklar.

## <a name="match_resultsempty"></a><a name="empty"></a>match_results::boş

Alt eşleşmeler için testler.

```cpp
bool empty() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev yalnızca normal ifade araması başarısız olursa doğru döndürür.

## <a name="match_resultsend"></a><a name="end"></a>match_results::sonu

Alt eşleşme dizisinin sonunu belirtir.

```cpp
const_iterator end() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, dizinin sonundan hemen ötesine işaret eden bir yineleyici döndürür.

## <a name="match_resultsformat"></a><a name="format"></a>match_results::biçim

Alt eşleşmeleri biçimlendirir.

```cpp
template <class OutIt>
OutIt format(OutIt out,
    const string_type& fmt, match_flag_type flags = format_default) const;

string_type format(const string_type& fmt, match_flag_type flags = format_default) const;
```

### <a name="parameters"></a>Parametreler

*OutIt*\
Çıkış yineleyici türü.

*çıkış*\
Yazılacak çıkış akışı.

*Fmt*\
Biçim dizesi.

*Bayrak*\
Biçim bayrakları.

### <a name="remarks"></a>Açıklamalar

Her üye işlev, *fmt*biçiminin kontrolü altında biçimlendirilmiş metin oluşturur. İlk üye işlev, biçimlendirilmiş metni bağımsız değişkeni *tarafından* tanımlanan sıraya yazar ve *dışarı*döner. İkinci üye işlev biçimlendirilmiş metnin bir kopyasını tutan bir dize nesnesini döndürür.

Biçimlendirilmiş metin oluşturmak için. biçim dizesindeki edebi metin normalde hedef sıraya kopyalanır. Biçim dizesindeki her çıkış dizisi temsil ettiği metin tarafından değiştirilir. Kopyalama ve değiştirmeyle ilgili ayrıntılar işleve geçirilen biçim bayrakları tarafından denetlenir.

## <a name="match_resultsget_allocator"></a><a name="get_allocator"></a>match_results:get_allocator

Depolanan ayırıcıyı döndürür.

```cpp
allocator_type get_allocator() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, `*this` `sub_match` nesnelerini ayırmak için kullanılan ayırıcı nesnenin bir kopyasını döndürür.

## <a name="match_resultsiterator"></a><a name="iterator"></a>match_results::iterator

Alt eşleşmeler için yineleyici türü.

```cpp
typedef const_iterator iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, denetlenen dizi için rasgele erişim yineleyicisi olarak hizmet verebilen bir nesneyi açıklar.

## <a name="match_resultslength"></a><a name="length"></a>match_results::uzunluk

Bir alt eşleşmenin uzunluğunu döndürür.

```cpp
difference_type length(size_type sub = 0) const;
```

### <a name="parameters"></a>Parametreler

*Alt*\
Alt eşleşmenin dizini.

### <a name="remarks"></a>Açıklamalar

Üye işlev `(*this)[sub].length()`döndürür.

## <a name="match_resultsmatch_results"></a><a name="match_results"></a>match_results:match_results

Nesneyi inşa eder.

```cpp
explicit match_results(const Alloc& alloc = Alloc());

match_results(const match_results& right);
```

### <a name="parameters"></a>Parametreler

*Ayırma*\
Depolanacak ayırıcı nesne.

*Doğru*\
Match_results nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, alt `match_results` eşleşmeleri olmayan bir nesne inşa eder. İkinci oluşturucu, `match_results` *hakkın*kopyası olan bir nesne yi inşa eder.

## <a name="match_resultsmax_size"></a><a name="max_size"></a>match_results::max_size

En fazla sayıda alt eşleşme alır.

```cpp
size_type max_size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, nesnenin denetleyebileceği en uzun dizinin uzunluğunu döndürür.

## <a name="match_resultsoperator"></a><a name="op_eq"></a>match_results::operator=

match_results bir nesneyi kopyalayın.

```cpp
match_results& operator=(const match_results& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Match_results nesnesi.

### <a name="remarks"></a>Açıklamalar

Üye işleç, kontrol edilen `*this` sırayı *sağ*tarafından kontrol edilen dizinin bir kopyasıyla değiştirir.

## <a name="match_resultsoperator"></a><a name="op_at"></a>match_results::operatör[]

Bir alt nesneye erişin.

```cpp
const_reference operator[](size_type n) const;
```

### <a name="parameters"></a>Parametreler

*n*\
Alt eşleşme dizini.

### <a name="remarks"></a>Açıklamalar

Üye işlev, denetimaltındaki dizinin *n* öğesine bir başvuru veya `sub_match` yakalama `size() <= n` grubu *n* eşleşmenin bir parçası değilse boş bir nesneye bir başvuru döndürür.

## <a name="match_resultsposition"></a><a name="position"></a>match_results::pozyasyon

Bir alt grubun ofset'ini başlatın.

```cpp
difference_type position(size_type sub = 0) const;
```

### <a name="parameters"></a>Parametreler

*Alt*\
Alt eşleşme dizini.

### <a name="remarks"></a>Açıklamalar

Üye işlev, `std::distance(prefix().first, (*this)[sub].first)`yani hedef dizideki ilk karakterden, kontrol edilen dizinin öğesi `n` tarafından işaret edilen alt eşleşmedeki ilk karaktere olan uzaklığı döndürür.

## <a name="match_resultsprefix"></a><a name="prefix"></a>match_results::p düzeltme

İlk alt eşleşmeden önce sıra alır.

```cpp
const_reference prefix() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, hedef dizinin başında `sub_match<BidIt>` başlayan ve eşleşen `(*this)[0].first`alt diziden önce gelen metne işaret eden karakter dizisini gösteren bir tür nesneye başvuru verir.

## <a name="match_resultsreference"></a><a name="reference"></a>match_results::referans

Öğe başvurusu türü.

```cpp
typedef const_reference reference;
```

### <a name="remarks"></a>Açıklamalar

Türü türü `const_reference`için eşanlamlıdır.

## <a name="match_resultssize"></a><a name="size"></a>match_results::boyut

Alt eşleşme sayısını sayar.

```cpp
size_type size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, arama için kullanılan normal ifadedeki yakalama gruplarının sayısından bir fazla veya arama yapılmamışsa sıfır döndürür.

## <a name="match_resultssize_type"></a><a name="size_type"></a>match_results:size_type

Alt eşleşme sayısı türü.

```cpp
typedef typename Alloc::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

Türü türü `Alloc::size_type`için eşanlamlıdır.

## <a name="match_resultsstr"></a><a name="str"></a>match_results::str

Bir alt eşleşme döndürür.

```cpp
string_type str(size_type sub = 0) const;
```

### <a name="parameters"></a>Parametreler

*Alt*\
Alt eşleşme dizini.

### <a name="remarks"></a>Açıklamalar

Üye işlev `string_type((*this)[sub])`döndürür.

## <a name="match_resultsstring_type"></a><a name="string_type"></a>match_results:string_type

Bir dize türü.

```cpp
typedef basic_string<char_type> string_type;
```

### <a name="remarks"></a>Açıklamalar

Türü türü `basic_string<char_type>`için eşanlamlıdır.

## <a name="match_resultssuffix"></a><a name="suffix"></a>match_results::soneki

Son alt eşleşmeden sonra sıraalır.

```cpp
const_reference suffix() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, hedef dizinin sonunda `sub_match<BidIt>` başlayıp `(*this)[size() - 1].second` biten karakter dizisini gösteren bir tür nesneye bir başvuru döndürür, yani eşleşen alt sırayı izleyen metne işaret eder.

## <a name="match_resultsswap"></a><a name="swap"></a>match_results::takas

İki match_results nesnedeğiştirir.

```cpp
void swap(const match_results& right) throw();
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Takas match_results nesnesi.

### <a name="remarks"></a>Açıklamalar

Üye işlev, içeriğini `*this` ve *doğru* içeriğini sürekli olarak değiştirir ve özel durumlar atmaz.

## <a name="match_resultsvalue_type"></a><a name="value_type"></a>match_results:value_type

Alt eşleşme türü.

```cpp
typedef sub_match<BidIt> value_type;
```

### <a name="remarks"></a>Açıklamalar

Typedef türü `sub_match<BidIt>`için eşanlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<regex>](../standard-library/regex.md)
