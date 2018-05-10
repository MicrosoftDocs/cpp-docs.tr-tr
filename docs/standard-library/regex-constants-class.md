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
ms.openlocfilehash: fcf3a5fcdb8c604dac368b60cf4a368bdb1c3f14
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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

Ad alanı `regex_constants` birkaç bayrağı türlerini ve bunların ilişkili bayrak değerleri yalıtır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<regex >

**Namespace:** std

## <a name="error_type"></a>  regex_constants::error_type

Normal ifade sözdizimi hataları raporlama için işaretler.

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

Hata bayrakları tutabilen bir nesneyi tanımlayan bir enum türü türüdür. Ayrı bayrak değerleri şunlardır:

`error_backref` --İfade geçersiz arka başvuru içeriyor

`error_badbrace` --İfade geçersiz bir sayı {} ifadesinde bulunan

`error_badrepeat` --bir yineleme ifadesi (biri ' *', '', '+', ' {' çoğu bağlamlarda) bir ifade tarafından öncesinde değil

`error_brace` --ifade eşleşmeyen bulunan ' {' veya '}'

`error_brack` --ifade eşleşmeyen bulunan ' [' veya ']'

`error_collate` --İfade geçersiz bir harmanlama öğe adı yer alan

`error_complexity` --Denenen bir eşleşme çok karmaşık olduğundan başarısız oldu

`error_ctype` --İfade geçersiz karakter sınıf adı içeriyor

`error_escape` --İfade geçersiz kaçış dizisi içeriyor

`error_paren` --ifade eşleşmeyen bulunan '(' veya')'

`error_parse` --ifadesi ayrıştırılamadı

`error_range` --bir geçersiz karakter aralığı belirticisi ifade içeriyor

`error_space` --bir normal ifade ayrıştırma başarısız oldu kullanılabilir yeterli kaynak yok

`error_stack` --Denenen bir eşleşme başarısız oldu çünkü kullanılabilir yeterli bellek yoktu

`error_syntax` --bir sözdizimi hatası ayrıştırılamadı

`error_backref` --İfade geçersiz arka başvuru içeriyor

## <a name="match_flag_type"></a>  regex_constants::match_flag_type

Normal ifade seçenekleri eşleşen bayrakları.

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

Türü bir normal ifade ve biçim karşı bir metin dizisi eşleşen metni yerleştirirken kullanılacak bayrakları yapılırken kullanılacak seçenekleri açıklayan bir bit maskesi türüdür. Seçenekler ile birleştirilebilir `|`.

Eşleşme Seçenekler şunlardır:

`match_default`

`match_not_bol` --hedef sırası ilk konumda bir satır başına olarak görmeyin

`match_not_eol` --hedef sırası geçmiş--end konumda bir satır sonu olarak görmeyin

`match_not_bow` --hedef sırası ilk konumda bir sözcüğün başlangıcına olarak görmeyin

`match_not_eow` --hedef sırası geçmiş--end konumda bir sözcüğün sonuna görmeyin

`match_any` --birden fazla eşleşme mümkün ise eşleşme kabul edilebilir.

`match_not_null` --boş bir değişkene bir eşleşme olarak görmeyin

`match_continuous` --hedef sırası başındaki dışında eşleşmeler arama değil

`match_prev_avail` -- `--first` Geçerli bir yineleyici olan; Yoksay `match_not_bol` ve `match_not_bow` varsa Ayarla

Biçim bayraklar şunlardır:

`format_default` --ECMAScript biçimi kurallarını kullan

`format_sed` --azaltılabilir biçimi kurallarını kullan

`format_no_copy` --normal ifadeyle eşleşmez metin kopyalamayın

`format_first_only` --için eşleşen birinci sonra arama

## <a name="syntax_option_type"></a>  regex_constants::syntax_option_type

Sözdizimi seçenekleri seçmek için işaretler.

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

Dil tanımlayıcıları ve sözdizimi değiştiricileri normal bir ifade derleme yapılırken kullanılacak açıklayan bir bit maskesi türü türüdür. Seçenekler ile birleştirilebilir `|`. Aynı anda birden fazla dil belirleyici kullanılmalıdır.

Dil tanımlayıcıları şunlardır:

`ECMAScript` --ECMAScript derleme

`basic` --BRE derleme

`extended` --ERE derleme

`awk` --awk derleme

`grep` --grep derleme

`egrep` --egrep derleme

Sözdizimi değiştiricileri şunlardır:

`icase` --eşleşmeleri büyük küçük harf duyarsız olun

`nosubs` --implementaton yakalama grupları içeriğini izlemenize yok

`optimize` --Uygulama normal ifade derleme hızına yerine eşleşen hızı vurgulamak

`collate` --yapma yerel ayara duyarlı eşleşir

## <a name="see-also"></a>Ayrıca bkz.

[\<Regex >](../standard-library/regex.md)<br/>
[regex_error Sınıfı](../standard-library/regex-error-class.md)<br/>
[\<Regex > işlevleri](../standard-library/regex-functions.md)<br/>
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)<br/>
[\<Regex > işleçleri](../standard-library/regex-operators.md)<br/>
[regex_token_iterator Sınıfı](../standard-library/regex-token-iterator-class.md)<br/>
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)<br/>
[\<Regex > tür tanımları](../standard-library/regex-typedefs.md)<br/>
