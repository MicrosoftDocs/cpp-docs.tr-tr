---
title: regex_constants Sınıfı
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_constants
- regex/std::regex_constants::error_collate
- regex/std::regex_constants::error_ctype
- regex/std::regex_constants::error_escape
- regex/std::regex_constants::error_backref
- regex/std::regex_constants::error_brack
- regex/std::regex_constants::error_paren
- regex/std::regex_constants::error_brace
- regex/std::regex_constants::error_badbrace
- regex/std::regex_constants::error_range
- regex/std::regex_constants::error_space
- regex/std::regex_constants::error_badrepeat
- regex/std::regex_constants::error_complexity
- regex/std::regex_constants::error_stack
- regex/std::regex_constants::error_parse
- regex/std::regex_constants::error_syntax
- regex/std::regex_constants::match_default
- regex/std::regex_constants::match_not_bol
- regex/std::regex_constants::match_not_eol
- regex/std::regex_constants::match_not_bow
- regex/std::regex_constants::match_not_eow
- regex/std::regex_constants::match_any
- regex/std::regex_constants::match_not_null
- regex/std::regex_constants::match_continuous
- regex/std::regex_constants::match_prev_avail
- regex/std::regex_constants::format_default
- regex/std::regex_constants::format_sed
- regex/std::regex_constants::format_no_copy
- regex/std::regex_constants::format_first_only
- regex/std::regex_constants::ECMAScript
- regex/std::regex_constants::basic
- regex/std::regex_constants::extended
- regex/std::regex_constants::awk
- regex/std::regex_constants::grep
- regex/std::regex_constants::egrep
- regex/std::regex_constants::icase
- regex/std::regex_constants::nosubs
- regex/std::regex_constants::optimize
- regex/std::regex_constants::collate
helpviewer_keywords:
- std::regex_constants [C++]
- std::regex_constants [C++], error_collate
- std::regex_constants [C++], error_ctype
- std::regex_constants [C++], error_escape
- std::regex_constants [C++], error_backref
- std::regex_constants [C++], error_brack
- std::regex_constants [C++], error_paren
- std::regex_constants [C++], error_brace
- std::regex_constants [C++], error_badbrace
- std::regex_constants [C++], error_range
- std::regex_constants [C++], error_space
- std::regex_constants [C++], error_badrepeat
- std::regex_constants [C++], error_complexity
- std::regex_constants [C++], error_stack
- std::regex_constants [C++], error_parse
- std::regex_constants [C++], error_syntax
- std::regex_constants [C++], match_default
- std::regex_constants [C++], match_not_bol
- std::regex_constants [C++], match_not_eol
- std::regex_constants [C++], match_not_bow
- std::regex_constants [C++], match_not_eow
- std::regex_constants [C++], match_any
- std::regex_constants [C++], match_not_null
- std::regex_constants [C++], match_continuous
- std::regex_constants [C++], match_prev_avail
- std::regex_constants [C++], format_default
- std::regex_constants [C++], format_sed
- std::regex_constants [C++], format_no_copy
- std::regex_constants [C++], format_first_only
- std::regex_constants [C++], ECMAScript
- std::regex_constants [C++], basic
- std::regex_constants [C++], extended
- std::regex_constants [C++], awk
- std::regex_constants [C++], grep
- std::regex_constants [C++], egrep
- std::regex_constants [C++], icase
- std::regex_constants [C++], nosubs
- std::regex_constants [C++], optimize
- std::regex_constants [C++], collate
ms.assetid: 4a69c0ba-c46d-46e4-bd29-6f4efb805f26
ms.openlocfilehash: ee016e5cee1bde94a49a1b339d6910d60db4cea1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331956"
---
# <a name="regex_constants-namespace"></a>regex_constants ad alanı

Normal ifade bayrakları için ad alanı.

## <a name="syntax"></a>Sözdizimi

```cpp
namespace regex_constants {
    enum syntax_option_type;
    enum match_flag_type;
    enum error_type;
}
```

## <a name="remarks"></a>Açıklamalar

Ad alanı, `regex_constants` birkaç bayrak türünü ve ilişkili bayrak değerlerini kapsüller.

|||
|-|-|
|[error_type](#error_type)|Normal ifade sözdizimi hatalarını bildirmek için bayraklar.|
|[match_flag_type](#match_flag_type)|Normal ifade eşleştirme seçenekleri için bayraklar.|
|[syntax_option_type](#syntax_option_type)|Sözdizimi seçeneklerini seçmek için bayraklar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<regex>

**Ad alanı:** std

## <a name="regex_constantserror_type"></a><a name="error_type"></a>regex_constants:error_type

Normal ifade sözdizimi hatalarını bildirmek için bayraklar.

```cpp
enum error_type
    {    // identify error
    error_collate,
    error_ctype,
    error_escape,
    error_backref,
    error_brack,
    error_paren,
    error_brace,
    error_badbrace,
    error_range,
    error_space,
    error_badrepeat,
    error_complexity,
    error_stack,
    error_parse,
    error_syntax
    };
```

### <a name="remarks"></a>Açıklamalar

Tür, hata bayrakları tutabilen bir nesneyi açıklayan numaralandırılmış bir türdür. Farklı bayrak değerleri şunlardır:

`error_backref`-- ifade geçersiz bir geri başvuru içeriyordu

`error_badbrace`-- { } ifadesinde geçersiz bir sayı içeren ifade

`error_badrepeat`-- bir yinelenen ifade (çoğu bağlamda '*', '', '+', '{' bir ifade den önce değildi)

`error_brace`-- ifade eşleşmeyen bir '{' veya '}' içeriyordu

`error_brack`-- ifade eşleşmeyen bir '[' veya ']' içeriyordu

`error_collate`-- ifade geçersiz bir harmanlama öğesi adı içeriyordu

`error_complexity`-- çok karmaşık olduğu için bir eşleşme denemesi başarısız oldu

`error_ctype`-- ifade geçersiz bir karakter sınıf adı içeriyordu

`error_escape`-- ifade geçersiz bir kaçış dizisi içeriyordu

`error_paren`-- ifade eşleşmeyen bir '(' veya ')' içeriyordu

`error_parse`-- ifade ayrışdırmak için başarısız oldu

`error_range`-- ifade geçersiz bir karakter aralığı belirteç içeriyordu

`error_space`-- yeterli kaynak olmadığı için düzenli bir ifadeyi ayrıştma başarısız oldu

`error_stack`-- yeterli bellek olmadığı için bir eşleşme denemesi başarısız oldu

`error_syntax`-- sözdizimi hatasında ayrışma başarısız

`error_backref`-- ifade geçersiz bir geri başvuru içeriyordu

## <a name="regex_constantsmatch_flag_type"></a><a name="match_flag_type"></a>regex_constants:match_flag_type

Normal ifade eşleştirme seçenekleri için bayraklar.

```cpp
enum match_flag_type
    {    // specify matching and formatting rules
    match_default = 0x0000,
    match_not_bol = 0x0001,
    match_not_eol = 0x0002,
    match_not_bow = 0x0004,
    match_not_eow = 0x0008,
    match_any = 0x0010,
    match_not_null = 0x0020,
    match_continuous = 0x0040,
    match_prev_avail = 0x0100,
    format_default = 0x0000,
    format_sed = 0x0400,
    format_no_copy = 0x0800,
    format_first_only = 0x1000,
    _Match_not_null = 0x2000
    };
```

### <a name="remarks"></a>Açıklamalar

Tür, metin dizisini normal bir ifadeyle eşleştirirken kullanılacak seçenekleri açıklayan bir bitmask türüdür ve metin değiştirirken kullanılacak biçim bayraklarıdır. Seçenekler ile `|`birleştirilebilir.

Maç seçenekleri şunlardır:

`match_default`

`match_not_bol`-- hedef dizideki ilk konumu bir çizginin başlangıcı olarak ele alamayın

`match_not_eol`-- hedef sekanstaki son uç konumu bir çizginin sonu olarak ele alamayın

`match_not_bow`-- hedef dizideki ilk konumu bir sözcüğün başlangıcı olarak ele almaz

`match_not_eow`-- hedef dizideki geçmiş uç konumunu bir sözcüğün sonu olarak ele almaz

`match_any`-- birden fazla maç mümkünse herhangi bir maç kabul edilebilir

`match_not_null`-- boş bir alt sırayı eşleme olarak ele alma

`match_continuous`-- hedef sıranın başlangıcındakiler dışında eşleşmeleri aramayın

`match_prev_avail` -- `--first`geçerli bir yineleyicidir; `match_not_bol` yoksay `match_not_bow` ve ayarlanırsa

Biçim bayrakları şunlardır:

`format_default`-- ECMAScript biçim kurallarını kullanın

`format_sed`-- sed format kuralları nı kullanma

`format_no_copy`-- normal ifadeyle eşleşmeyen metni kopyalamayın

`format_first_only`-- ilkinden sonra maç aramayın

## <a name="regex_constantssyntax_option_type"></a><a name="syntax_option_type"></a>regex_constants:syntax_option_type

Sözdizimi seçeneklerini seçmek için bayraklar.

```cpp
enum syntax_option_type
    {    // specify RE syntax rules
    ECMAScript = 0x01,
    basic = 0x02,
    extended = 0x04,
    awk = 0x08,
    grep = 0x10,
    egrep = 0x20,
    _Gmask = 0x3F,

    icase = 0x0100,
    nosubs = 0x0200,
    optimize = 0x0400,
    collate = 0x0800
    };
```

### <a name="remarks"></a>Açıklamalar

Tür, normal bir ifade derlerken kullanılacak dil belirteçlerini ve sözdizimi değiştiricileri açıklayan bir bitmask türüdür. Seçenekler ile `|`birleştirilebilir. Aynı anda en fazla birden fazla dil belirteç kullanılmalıdır.

Dil belirteci:

`ECMAScript`-- ECMAScript olarak derlemek

`basic`-- BRE olarak derle

`extended`-- ERE olarak derle

`awk`-- awk olarak derlemek

`grep`-- grep olarak derlemek

`egrep`-- egrep olarak derlemek

Sözdizimi değiştiriciler şunlardır:

`icase`-- eşleşmeleri büyük/küçük harf duyarsız yapmak

`nosubs`-- uygulayıcı yakalama gruplarının içeriğini takip etmek gerekmez

`optimize`-- uygulama normal ifade derleme hızı yerine eşleştirme hızını vurgulamak gerekir

`collate`-- yerel duyarlı eşleşmeler yapmak

## <a name="see-also"></a>Ayrıca bkz.

[\<regex>](../standard-library/regex.md)\
[regex_error Sınıfı](../standard-library/regex-error-class.md)\
[\<regex> fonksiyonları](../standard-library/regex-functions.md)\
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)\
[\<regex> operatörleri](../standard-library/regex-operators.md)\
[regex_token_iterator Sınıfı](../standard-library/regex-token-iterator-class.md)\
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)\
[\<regex> typedefs](../standard-library/regex-typedefs.md)
