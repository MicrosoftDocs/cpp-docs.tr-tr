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
ms.openlocfilehash: c8abca8109db9c781d63721b795feb01161fdb40
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78876157"
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

Ad alanı `regex_constants` çeşitli bayrak türlerini ve bunlarla ilişkili bayrak değerlerini kapsüller.

|||
|-|-|
|[error_type](#error_type)|Normal ifade sözdizimi hatalarını raporlamaya yönelik bayraklar.|
|[match_flag_type](#match_flag_type)|Normal ifade eşleştirme seçeneklerine yönelik bayraklar.|
|[syntax_option_type](#syntax_option_type)|Sözdizimi seçeneklerini belirlemek için bayraklar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<Regex >

**Ad alanı:** std

## <a name="error_type"></a>regex_constants:: error_type

Normal ifade sözdizimi hatalarını raporlamaya yönelik bayraklar.

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

Tür, hata bayraklarını tutabilecek bir nesneyi açıklayan, numaralandırılmış bir türdür. DISTINCT bayrak değerleri şunlardır:

`error_backref`--ifade geçersiz bir geri başvuru içeriyordu

`error_badbrace`--ifade bir {} ifadesinde geçersiz bir sayı içeriyordu

`error_badrepeat`--bir yineleme ifadesi (' * ', ' ', ' + ', ' {' çoðu bağlamdaki) bir ifadenin önünde değil

`error_brace`--ifade eşleşmeyen bir ' {' veya '} ' içeriyor

`error_brack`--ifade eşleşmeyen bir ' [' veya '] ' içeriyor

`error_collate`--ifade geçersiz bir harmanlama öğesi adı içeriyordu

`error_complexity`--denenen eşleşme çok karmaşık olduğundan başarısız oldu

`error_ctype`--ifade geçersiz bir karakter sınıfı adı içeriyordu

`error_escape`--ifade geçersiz bir kaçış sırası içeriyordu

`error_paren`--ifade eşleşmeyen bir ' (' veya ') ' içeriyor

`error_parse`--ifade ayrıştırılamadı

`error_range`--ifade geçersiz bir karakter aralığı belirleyicisi içeriyordu

`error_space`--kullanılabilir yeterli kaynak olmadığından düzenli bir ifade ayrıştırma başarısız oldu

`error_stack`--yeterli kullanılabilir bellek olmadığından, denenen bir eşleşme başarısız oldu

`error_syntax`--bir sözdizimi hatası üzerinde ayrıştırma başarısız oldu

`error_backref`--ifade geçersiz bir geri başvuru içeriyordu

## <a name="match_flag_type"></a>regex_constants:: match_flag_type

Normal ifade eşleştirme seçeneklerine yönelik bayraklar.

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

Türü bir metin dizisini bir normal ifade ve metin değiştirirken kullanılacak biçim bayrakları ile eşleştirirken kullanılacak seçenekleri açıklayan bir bit maskesi türüdür. Seçenekler, `|`ile birleştirilebilir.

Eşleşme seçenekleri şunlardır:

`match_default`

`match_not_bol`--hedef dizideki ilk konumu satırın başı olarak değerlendirin

`match_not_eol`--hedef dizideki son bitiş konumunu satırın sonu olarak değerlendirin

`match_not_bow`--bir sözcüğün başlangıcında hedef dizideki ilk konumu değerlendirin

`match_not_eow`--bir sözcüğün sonu olarak hedef dizideki son bitiş konumunu işleme

`match_any`--birden fazla eşleşme mümkünse eşleşme kabul edilebilir

`match_not_null`--boş bir alt diziyi eşleşme olarak değerlendirin

`match_continuous`--hedef dizinin başından farklı eşleşmeleri arama

`match_prev_avail` -- `--first` geçerli bir yineleyici; `match_not_bol` yoksay ve ayarlandıysa `match_not_bow`

Biçim bayrakları şunlardır:

`format_default`--ECMAScript biçim kurallarını kullanın

`format_sed`--sed biçim kurallarını kullan

`format_no_copy`--normal ifadeyle eşleşmeyen metni kopyalamayın

`format_first_only`--birinciden sonra Eşleşmeler arama

## <a name="syntax_option_type"></a>regex_constants:: syntax_option_type

Sözdizimi seçeneklerini belirlemek için bayraklar.

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

Türü, bir normal ifade derlenirken kullanılacak dil tanımlayıcılarını ve sözdizimi değiştiricilerini açıklayan bir bit maskesi türüdür. Seçenekler, `|`ile birleştirilebilir. Tek seferde birden fazla dil belirticisi kullanılmamalıdır.

Dil belirticileri şunlardır:

`ECMAScript`--ECMAScript olarak derle

`basic`--BRE olarak derle

`extended`--@ olarak derle

`awk`--awk olarak derle

`grep`--grep olarak derle

`egrep`--egrep olarak derle

Sözdizimi değiştiricileri şunlardır:

`icase`--eşleşme büyük/küçük harf duyarsız

`nosubs`--uygulama, yakalama gruplarının içeriğini izlememek zorunda değildir

`optimize`--uygulama, normal ifade derlemesinin hızına göre değil, eşleşme hızını vurgumalıdır

`collate`--eşleşmelerin yerel ayara duyarlı olması

## <a name="see-also"></a>Ayrıca bkz.

[\<regex >](../standard-library/regex.md)\
[Regex_error sınıfı](../standard-library/regex-error-class.md)\
[\<regex > işlevleri](../standard-library/regex-functions.md)\
[Regex_iterator sınıfı](../standard-library/regex-iterator-class.md)\
[\<regex > işleçleri](../standard-library/regex-operators.md)\
[Regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md)\
[regex_traits sınıfı](../standard-library/regex-traits-class.md)\
[\<Regex > tür tanımları](../standard-library/regex-typedefs.md)
