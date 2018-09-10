---
title: regex_constants sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f766df104df31ba2ba154c081338f7a6d1d4a05c
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107536"
---
# <a name="regexconstants-class"></a>regex_constants Sınıfı

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

Ad alanı `regex_constants` birkaç bayrak türünü ve bunların ilişkili bayrak değerlerini kapsüller.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<regex >

**Namespace:** std

## <a name="error_type"></a>  regex_constants::error_type

Normal ifade söz dizimi hatalarını raporlama için kullanılan bayraklar.

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

Hata bayrakları tutabilen bir nesneyi tanımlayan bir listeden seçimli türü türüdür. Farklı bayrak değerleri şunlardır:

`error_backref` --İfade geçersiz arka başvuru içeriyor.

`error_badbrace` --{} ifadesinde geçersiz bir sayı ifadesi içeriyor

`error_badrepeat` --bir yineleme ifadesi (bir ' *', '', '+', ' {' çoğu bağlamlarda) bir ifade tarafından öncesinde değil

`error_brace` --ifadesi eşleşmeyen yer alan ' {' veya '}'

`error_brack` --ifadesi eşleşmeyen yer alan ' [' veya ']'

`error_collate` --ifade yer alan geçersiz bir harmanlama öğesi adı

`error_complexity` --çok karmaşık olduğundan denenen bir eşleşme başarısız oldu

`error_ctype` --ifade yer alan bir geçersiz karakter sınıfı adı

`error_escape` --İfade geçersiz bir kaçış dizisi içeriyor

`error_paren` --ifadesi eşleşmeyen yer alan '(' veya')'

`error_parse` --ifadesi ayrıştırılamadı

`error_range` --ifade yer alan bir geçersiz karakter aralığı tanımlayıcısı

`error_space` --bir normal ifade ayrıştırma işlemi başarısız oldu çünkü kullanılabilir yeterli kaynak yok

`error_stack` --Denenen bir eşleşme başarısız oldu çünkü kullanılabilir yeterli bellek yoktu

`error_syntax` --bir sözdizimi hatası ayrıştırılamadı

`error_backref` --İfade geçersiz arka başvuru içeriyor.

## <a name="match_flag_type"></a>  regex_constants::match_flag_type

Seçenekleri eşleşen normal ifade bayrakları.

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

Bir normal ifade ve biçim karşı bir metin dizisi ile eşleşen metin değiştirirken kullanılan bayraklar yapılırken kullanılacak seçeneklerle bir bit maskesi türünde türüdür. Seçenekleri ile birleştirilebilir `|`.

Eşleşme seçenekleri şunlardır:

*match_default*<br/>

`match_not_bol` --Hedef dizideki ilk konumu bir satırın başına olarak davran değil

`match_not_eol` --past--end konumu hedef dizideki bir satırın sonuna davran değil

`match_not_bow` --Hedef dizideki ilk konumu olarak bir sözcüğün başlangıcını kabul değil

`match_not_eow` --past--end konumu hedef dizideki bir sözcüğün sonuna davran değil

`match_any` --herhangi bir eşleşme birden fazla eşleşme Mümkünse, kabul edilebilir

`match_not_null` --boş bir alt diziyi bir eşleşme olarak işle değil

`match_continuous` --Hedef dizinin başındaki dışında eşleşmeleri için arama

`match_prev_avail` -- `--first` Geçerli bir yineleyici olduğunu; Yoksay `match_not_bol` ve `match_not_bow` varsa Ayarla

Biçim bayrakları şunlardır:

`format_default` --ECMAScript biçim kuralları kullanma

`format_sed` --sed biçim kuralları kullanma

`format_no_copy` --normal ifadeyle eşleşmez metin kopyalamayın

`format_first_only` --sonra ilk öğe için eşleşme arama

## <a name="syntax_option_type"></a>  regex_constants::syntax_option_type

Söz dizimi seçenekleri için bayrakları.

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

Türü bir normal ifade derlenirken kullanılacak dil tanımlayıcıları ve söz dizimi değiştiriciler betimleyen bir bit maskesi türdür. Seçenekleri ile birleştirilebilir `|`. Aynı anda birden fazla dil tanımlayıcısı kullanılmalıdır.

Dil tanımlayıcılarıdır:

`ECMAScript` --ECMAScript derleme

`basic` --BRE derleme

`extended` --ERE derleme

`awk` --awk derleme

`grep` --grep derleme

`egrep` --egrep derleme

Söz dizimi değiştiricilerdir:

`icase` --eşleşme büyük/küçük harfe olun

`nosubs` --implementaton yakalama gruplarının içeriğini izlemenize yok

`optimize` --Uygulama normal ifade derlemesinin hız yerine eşleşen hızı vurgulamak

`collate` --olun, yerel ayar duyarlı eşleşir

## <a name="see-also"></a>Ayrıca bkz.

[\<Regex >](../standard-library/regex.md)<br/>
[regex_error Sınıfı](../standard-library/regex-error-class.md)<br/>
[\<Regex > işlevleri](../standard-library/regex-functions.md)<br/>
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)<br/>
[\<Regex > işleçleri](../standard-library/regex-operators.md)<br/>
[regex_token_iterator Sınıfı](../standard-library/regex-token-iterator-class.md)<br/>
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)<br/>
[\<Regex > tür tanımları](../standard-library/regex-typedefs.md)<br/>
