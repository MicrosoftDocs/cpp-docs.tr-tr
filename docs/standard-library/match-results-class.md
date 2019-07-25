---
title: match_results Sınıfı
ms.date: 09/10/2018
f1_keywords:
- regex/std::match_results
helpviewer_keywords:
- match_results class
ms.assetid: b504fdca-e5dd-429d-9960-6e27c9167fa6
ms.openlocfilehash: 72a948c7f8422b36b94a16cdb2c815bca92d20c7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456382"
---
# <a name="matchresults-class"></a>match_results Sınıfı

Bir dizi alt eşleşme tutar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class BidIt, class Alloc>
class match_results
```

## <a name="parameters"></a>Parametreler

*BidIt*\
Alt eşleşmeler için Yineleyici türü.

*Tahsis*\
Depolamayı yönetmek için bir ayırıcı türü.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir normal ifade arama tarafından oluşturulan türdeki `sub_match<BidIt>` öğelerin değiştirilemeyen bir dizisini denetleyen bir nesneyi tanımlar. Her öğe, bu öğeye karşılık gelen yakalama grubuyla eşleşen alt diziyi işaret eder.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[match_results](#match_results)|Nesnesini oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[allocator_type](#allocator_type)|Depolamayı yönetmek için bir ayırıcı türü.|
|[char_type](#char_type)|Öğenin türü.|
|[const_iterator](#const_iterator)|Alt eşleşmeler için const yineleyici türü.|
|[const_reference](#const_reference)|Bir öğe const başvurusunun türü.|
|[difference_type](#difference_type)|Yineleyici farkının türü.|
|[iden](#iterator)|Alt eşleşmeler için Yineleyici türü.|
|[Başvuru](#reference)|Öğe başvurusunun türü.|
|[size_type](#size_type)|Alt eşleşme sayısı türü.|
|[string_type](#string_type)|Bir dizenin türü.|
|[value_type](#value_type)|Alt eşleşme türü.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[başladı](#begin)|Alt eşleşme sırasının başlangıcını belirtir.|
|[empty](#empty)|Alt eşleşme olmaması için testler.|
|[erer](#end)|Alt eşleşme sırasının sonunu belirtir.|
|[format](#format)|Alt eşleşmeleri biçimlendirir.|
|[get_allocator](#get_allocator)|Depolanan ayırıcıyı döndürür.|
|[length](#length)|Alt eşleşme uzunluğunu döndürür.|
|[max_size](#max_size)|En fazla sayıda alt eşleşme alır.|
|[yerine](#position)|Bir alt grubun başlangıç sapmasını alın.|
|[prefix](#prefix)|İlk alt eşleşmeden önce sırayı alır.|
|[boyutla](#size)|Alt eşleşmelerin sayısını sayar.|
|[üstbilgisine](#str)|Bir alt eşleşme döndürür.|
|[suffix](#suffix)|Son alt eşleşmesinden sonra sırayı alır.|
|[Kur](#swap)|İki match_results nesnesini değiştirir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Bir match_results nesnesini kopyalayın.|
|[işlecinde\[\]](#op_at)|Bir alt nesneye erişin.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<Regex >

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

## <a name="allocator_type"></a>match_results::allocator_type

Depolamayı yönetmek için bir ayırıcı türü.

```cpp
typedef Alloc allocator_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, şablon bağımsız değişkeni *ayırma*için bir eş anlamlı.

## <a name="begin"></a>match_results:: Begin

Alt eşleşme sırasının başlangıcını belirtir.

```cpp
const_iterator begin() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, dizinin ilk öğesinde (veya boş bir dizinin sonunun ötesinde) işaret eden bir rastgele erişim yineleyici döndürür.

## <a name="char_type"></a>match_results::char_type

Öğenin türü.

```cpp
typedef typename iterator_traits<BidIt>::value_type char_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, aranan karakter dizisinin öğe türü olan `iterator_traits<BidIt>::value_type`türün bir eş anlamlısıdır.

## <a name="const_iterator"></a>match_results::const_iterator

Alt eşleşmeler için const yineleyici türü.

```cpp
typedef T0 const_iterator;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, denetimli sıra için sabit bir rastgele erişim Yineleyici işlevi görebilecek bir nesneyi tanımlar.

## <a name="const_reference"></a>match_results::const_reference

Bir öğe const başvurusunun türü.

```cpp
typedef const typename Alloc::const_reference const_reference;
```

### <a name="remarks"></a>Açıklamalar

TypeDef, denetlenen dizinin bir öğesine sabit başvuru olarak işlev görebilecek bir nesne açıklar.

## <a name="difference_type"></a>  match_results::difference_type

Yineleyici farkının türü.

```cpp
typedef typename iterator_traits<BidIt>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef türün `iterator_traits<BidIt>::difference_type`eşanlamlısıdır; denetimli sıranın öğelerine işaret eden iki yineleyiciler arasındaki farkı temsil eden bir nesneyi tanımlar.

## <a name="empty"></a>match_results:: Empty

Alt eşleşme olmaması için testler.

```cpp
bool empty() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi yalnızca normal ifade araması başarısız olursa true değerini döndürür.

## <a name="end"></a>match_results:: End

Alt eşleşme sırasının sonunu belirtir.

```cpp
const_iterator end() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, dizinin sonunun hemen ötesinde işaret eden bir yineleyici döndürür.

## <a name="format"></a>match_results:: Format

Alt eşleşmeleri biçimlendirir.

```cpp
template <class OutIt>
OutIt format(OutIt out,
    const string_type& fmt, match_flag_type flags = format_default) const;

string_type format(const string_type& fmt, match_flag_type flags = format_default) const;
```

### <a name="parameters"></a>Parametreler

*Utit*\
Çıkış yineleyici türü.

*dışı*\
Yazılacak çıkış akışı.

*FMT*\
Biçim dizesi.

*larına*\
Biçim bayrakları.

### <a name="remarks"></a>Açıklamalar

Her üye işlevi, *FMT*biçimindeki denetimin altında biçimli metin üretir. İlk üye işlevi, biçimli metni *bağımsız değişkeni tarafından* tanımlanan diziye yazar *ve döndürür.* İkinci üye işlevi biçimlendirilmiş metnin bir kopyasını tutarak bir dize nesnesi döndürür.

Biçimli metin oluşturmak için. biçim dizesindeki değişmez metin genellikle hedef diziye kopyalanır. Biçim dizesindeki her çıkış dizisi temsil ettiği metin tarafından değiştirilir. Kopyalama ve değiştirmeyle ilgili ayrıntılar işleve geçirilen biçim bayrakları tarafından denetlenir.

## <a name="get_allocator"></a>match_results::get_allocator

Depolanan ayırıcıyı döndürür.

```cpp
allocator_type get_allocator() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `*this` `sub_match` nesnelerini ayırmak için tarafından kullanılan ayırıcı nesnesinin bir kopyasını döndürür.

## <a name="iterator"></a>match_results:: Yineleyici

Alt eşleşmeler için Yineleyici türü.

```cpp
typedef const_iterator iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü, denetimli sıra için rastgele erişim Yineleyici işlevi görebilecek bir nesneyi tanımlar.

## <a name="length"></a>match_results:: length

Alt eşleşme uzunluğunu döndürür.

```cpp
difference_type length(size_type sub = 0) const;
```

### <a name="parameters"></a>Parametreler

*alt*\
Alt eşleşmenin dizini.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `(*this)[sub].length()`.

## <a name="match_results"></a>match_results::match_results

Nesnesini oluşturur.

```cpp
explicit match_results(const Alloc& alloc = Alloc());

match_results(const match_results& right);
```

### <a name="parameters"></a>Parametreler

*tahsis*\
Depolanacak ayırıcı nesne.

*Right*\
Kopyalanacak match_results nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, alt eşleşme `match_results` içermeyen bir nesne oluşturur. İkinci Oluşturucu, *sağ*kopyası `match_results` olan bir nesne oluşturur.

## <a name="max_size"></a>match_results::max_size

En fazla sayıda alt eşleşme alır.

```cpp
size_type max_size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, nesnenin denetleyecan en uzun sırasının uzunluğunu döndürür.

## <a name="op_eq"></a>match_results:: operator =

Bir match_results nesnesini kopyalayın.

```cpp
match_results& operator=(const match_results& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Kopyalanacak match_results nesnesi.

### <a name="remarks"></a>Açıklamalar

Member işleci, tarafından `*this` denetlenen sıranın, *sağdan*denetlenen sıranın bir kopyasıyla yerini alır.

## <a name="op_at"></a>match_results:: operator []

Bir alt nesneye erişin.

```cpp
const_reference operator[](size_type n) const;
```

### <a name="parameters"></a>Parametreler

*No*\
Alt eşleşmenin dizini.

### <a name="remarks"></a>Açıklamalar

Üye işlevi denetlenen sıranın *n* öğesine bir başvuru ya da yakalama grubu `sub_match` *n* , eşleşmenin bir parçası değilse boş bir nesneye `size() <= n` bir başvuru döndürür.

## <a name="position"></a>match_results::p onumu

Bir alt grubun başlangıç sapmasını alın.

```cpp
difference_type position(size_type sub = 0) const;
```

### <a name="parameters"></a>Parametreler

*alt*\
Alt eşleşmenin dizini.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, diğer `std::distance(prefix().first, (*this)[sub].first)`bir deyişle, hedef dizideki ilk karakterden, denetimli sıranın öğesine `n` göre işaret edilen alt eşleşenlerin ilk karakterine olan uzaklığı döndürür.

## <a name="prefix"></a>match_results::p yeniden düzeltir

İlk alt eşleşmeden önce sırayı alır.

```cpp
const_reference prefix() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, hedef dizinin başlangıcında başlayan ve ' de `sub_match<BidIt>` `(*this)[0].first`biten karakter dizisini işaret eden bir öğesine bir başvuru döndürür, diğer bir deyişle, eşleşen alt dizinin önündeki metni işaret eder.

## <a name="reference"></a>match_results:: Reference

Öğe başvurusunun türü.

```cpp
typedef const_reference reference;
```

### <a name="remarks"></a>Açıklamalar

Tür için `const_reference`bir eş anlamlı türü.

## <a name="size"></a>match_results:: size

Alt eşleşmelerin sayısını sayar.

```cpp
size_type size() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, arama için kullanılan normal ifadede bulunan yakalama gruplarının sayısından bir daha fazla döndürür veya hiçbir arama yapılmmışsa sıfırdır.

## <a name="size_type"></a>match_results::size_type

Alt eşleşme sayısı türü.

```cpp
typedef typename Alloc::size_type size_type;
```

### <a name="remarks"></a>Açıklamalar

Tür için `Alloc::size_type`bir eş anlamlı türü.

## <a name="str"></a>match_results:: Str

Bir alt eşleşme döndürür.

```cpp
string_type str(size_type sub = 0) const;
```

### <a name="parameters"></a>Parametreler

*alt*\
Alt eşleşmenin dizini.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür `string_type((*this)[sub])`.

## <a name="string_type"></a>match_results::string_type

Bir dizenin türü.

```cpp
typedef basic_string<char_type> string_type;
```

### <a name="remarks"></a>Açıklamalar

Tür için `basic_string<char_type>`bir eş anlamlı türü.

## <a name="suffix"></a>match_results:: suffix

Son alt eşleşmesinden sonra sırayı alır.

```cpp
const_reference suffix() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, hedef dizinin sonunda `sub_match<BidIt>` `(*this)[size() - 1].second` başlayan ve biten karakter dizisine işaret eden bir türü bir başvuru döndürür, diğer bir deyişle, eşleşen alt diziyi izleyen metni gösterir.

## <a name="swap"></a>match_results:: swap

İki match_results nesnesini değiştirir.

```cpp
void swap(const match_results& right) throw();
```

### <a name="parameters"></a>Parametreler

*Right*\
Match_results nesnesi ile takas edilecek.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, sabit zamanlı `*this` ve *sağ* içeriğini değiştirir ve özel durum oluşturmaz.

## <a name="value_type"></a>match_results::value_type

Alt eşleşme türü.

```cpp
typedef sub_match<BidIt> value_type;
```

### <a name="remarks"></a>Açıklamalar

TypeDef türün `sub_match<BidIt>`eşanlamlısıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<Regex >](../standard-library/regex.md)
