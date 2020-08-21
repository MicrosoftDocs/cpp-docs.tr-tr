---
title: '&lt;charconv &gt; işlevleri'
description: <charconv>Tamsayı veya kayan nokta değerlerini karakterlerden veya karakter başına dönüştüren kitaplık işlevlerini açıklar
ms.date: 08/20/2020
f1_keywords:
- charconv/std::to_chars
- charconv/std::from_chars
helpviewer_keywords:
- std::charconv [C++], to_chars
- std::charconv [C++], from_chars
ms.openlocfilehash: b8117f2a272f33be2bb5fef6ba8fa53ec794b63b
ms.sourcegitcommit: f1752bf90b4f869633a859ace85439ca19e208b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2020
ms.locfileid: "88722160"
---
# <a name="ltcharconvgt-functions"></a>&lt;charconv &gt; işlevleri

\<charconv>Üst bilgi, aşağıdaki üye olmayan işlevleri içerir:

| **Üye olmayan işlevler** | **Açıklama** |
|-|-|
|[to_chars](#to_chars) | Bir tamsayı veya kayan nokta değerini bir diziye dönüştürür **`char`** . |
|[from_chars](#from_chars) | Bir dizisini bir **`char`** tamsayı veya kayan noktalı değere dönüştürür. |

Bu dönüştürme işlevleri performans için ayarlanır ve ayrıca en kısa gidiş dönüş davranışını destekler. En kısa gidiş dönüş davranışı bir sayının karakter olarak dönüştürülmesi durumunda, bu karakterleri bir kayan noktaya dönüştürürken özgün sayının kurtarılmasını sağlamak için yalnızca yeterli duyarlık yazıldığı anlamına gelir.

- Karakter bir sayıya dönüştürülürken, sayısal değerin null ile sonlandırılmış olması gerekmez. Benzer şekilde, bir sayıyı karakter olarak dönüştürürken sonuç null ile Sonlandırılmamış değildir.
- Dönüştürme işlevleri bellek ayırmaz. Her durumda arabelleğe sahip olursunuz.
- Dönüştürme işlevleri throw değildir. Dönüştürmenin başarılı olup olmadığını belirleyebilmeniz için bir sonuç döndürülür.
- Dönüştürme işlevleri çalışma zamanı yuvarlama moduna duyarlı değildir.
- Dönüştürme işlevleri yerel ayara duyarlı değildir. Virgül kullanan yerel ayarlarda her zaman ondalık noktalarını `'.'` ve ', ' olarak her zaman yazdırır ve ayrıştırır.

## `to_chars`

Bir tamsayı veya kayan nokta değerini bir diziye dönüştürür **`char`** .

`value`Aralığı doldurarak bir karakter dizesine dönüştürür \[ `first` , `last` burada \[ `first` , `last` ) geçerli bir Aralık olmalıdır.
Bir [to_chars_result yapısı](to-chars-result-structure.md)döndürür. Dönüştürme başarılı olursa, tarafından gösterildiği gibi `to_char_result.ec` , üye `ptr` yazılan karakterlerin bir son bitiş işaretçisidir. Aksi takdirde, değerine sahiptir, `to_char_result.ec` `errc::value_too_large` `to_char_result.ptr` değeri vardır `last` ve aralığının içeriği \[ `first` `last` belirtilmemiş).

Başarısız olan tek yol, `to_chars` sonucu tutmak için yeterince büyük bir arabellek sağlarsanız olur.

```cpp
// integer to chars

to_chars_result to_chars(char* first, char* last, char value, int base = 10);
to_chars_result to_chars(char* first, char* last, signed char value, int base = 10);
to_chars_result to_chars(char* first, char* last, unsigned char value, int base = 10);
to_chars_result to_chars(char* first, char* last, short value, int base = 10);
to_chars_result to_chars(char* first, char* last, unsigned short value, int base = 10);
to_chars_result to_chars(char* first, char* last, int value, int base = 10);
to_chars_result to_chars(char* first, char* last, unsigned int value, int base = 10);
to_chars_result to_chars(char* first, char* last, long value, int base = 10);
to_chars_result to_chars(char* first, char* last, unsigned long value, int base = 10);
to_chars_result to_chars(char* first, char* last, long long value, int base = 10);
to_chars_result to_chars(char* first, char* last, unsigned long long value, int base = 10);
to_chars_result to_chars(char* first, char* last, bool value, int base = 10) = delete;

// floating-point to chars

to_chars_result to_chars(char* first, char* last, float value);
to_chars_result to_chars(char* first, char* last, double value);
to_chars_result to_chars(char* first, char* last, long double value);
to_chars_result to_chars(char* first, char* last, float value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, double value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, long double value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, float value, chars_format fmt, int precision);
to_chars_result to_chars(char* first, char* last, double value, chars_format fmt, int precision);
to_chars_result to_chars(char* first, char* last, long double value, chars_format fmt, int precision);
```

### <a name="parameters"></a>Parametreler

*adı*\
, Doldurulacak arabelleğin başlangıcını işaret eder.

*soyadına*\
Arabelleği sona erdirmek için bir karakter sonunu geçti.

*deeri*\
Dönüştürülecek değer. `value`Negatifse, temsili ile başlar `-` .

*temel*\
Tamsayı dönüştürmeleri için, karakter olarak dönüştürme sırasında kullanılacak temel `value` . 2 ile 36 (dahil) arasında olmalıdır. Önünde sıfır olmaz. 10.. 35 (dahil) aralığındaki rakamlar a küçük harfli karakter olarak temsil edilir. kadar

*FMT*\
Kayan nokta dönüştürmeleri için, bilimsel, sabit veya onaltılı gibi kullanılacak dönüştürme biçimini belirten bir bit maskesi. Ayrıntılar için [chars_format](chars-format-class.md) bakın.

*duyarlılık*\
Kayan nokta dönüştürmeleri için, dönüştürülmüş değer için duyarlık basamak sayısı.

### <a name="return-value"></a>Döndürülen değer

Dönüştürmenin sonucunu içeren bir [to_chars_result](to-chars-result-structure.md) .

### <a name="remarks"></a>Açıklamalar

Bir [chars_format](chars-format-class.md) parametresi alan işlevler, dönüştürme belirticisini şu şekilde kullandıkları gibi tespit eder: ise, dönüştürme belirticisi ise, ise `printf()` `'f'` `fmt` `chars_format::fixed` `'e'` `fmt` `chars_format::scientific` `'a'` ( `0x` sonuç içinde önde gelen) ise ve ise `fmt` `chars_format::hex` `'g'` `fmt` `chars_format::general` . En kısa sabit Gösterim belirtildiğinde, değer çok büyük veya çok küçük olduğunda mümkün olan en kısa Gösterim olabileceği için yine de uzun bir çıkışa neden olabilir.

Aşağıdaki tabloda, ve parametrelerinin farklı bileşimleri verilen dönüştürme davranışı açıklanmaktadır `fmt` `precision` . "En kısa gidiş dönüş davranışı" terimi, ilgili işlevi kullanarak bu gösterimi ayrıştırmanın `from_chars` değeri tam olarak kurtarabileceği için gereken en az basamak sayısını yazmak anlamına gelir.

| `fmt` ve `precision` birleşimi | Çıktı |
|--|--|
|  Hiçbiri | Sabit veya bilimsel gösterimden hangisi daha kısadır ve bir tiekesici olarak düzeltildi.</br>Bu davranış, parametreyi alan herhangi bir aşırı yükleme tarafından benzetimi yapılamıyor `fmt` . |
| `fmt` | Belirtilen biçim için, en kısa bilimsel biçim gibi en kısa gidiş dönüş davranışı. |
| `fmt` ve `precision` | , `printf()` En kısa gidiş dönüş davranışı olmadan, aşağıdaki stili, belirtilen duyarlık kullanır. |

### <a name="example"></a>Örnek

```cpp
#include <charconv>
#include <stdio.h>
#include <system_error>

template <typename T> void TestToChars(const T t)
{
    static_assert(std::is_floating_point_v<T>);
    constexpr bool IsFloat = std::is_same_v<T, float>;

    char buf[100]; // 100 is large enough for double and long double values because the longest possible outputs are "-1.23456735e-36" and "-1.2345678901234567e-100".
    constexpr size_t size = IsFloat ? 15 : 24;
    const std::to_chars_result res = std::to_chars(buf, buf + size, t);  // points to buffer area it can use. Must be char, not wchar_t, etc.
    
    if (res.ec == std::errc{}) // no error
    {
        // %.*s provides the exact number of characters to output because the output range, [buf, res.ptr), isn't null-terminated
        printf("success: %.*s\n", static_cast<int>(res.ptr - buf), buf);
    }
    else // probably std::errc::value_too_large
    {
        printf("Error: %d\n", static_cast<int>(res.ec));
    }
}

int main()
{
    TestToChars(123.34);
    return 0;
}
```

## `from_chars`

Bir dizisini bir **`char`** tamsayı veya kayan noktalı değere dönüştürür.

```cpp
// char to an integer value

from_chars_result from_chars(const char* first, const char* last, char& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, signed char& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, unsigned char& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, short& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, unsigned short& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, int& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, unsigned int& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, long& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, unsigned long& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, long long& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, unsigned long long& value, int base = 10);

// char to a floating-point value

from_chars_result from_chars(const char* first, const char* last, float& value, chars_format fmt = chars_format::general);
from_chars_result from_chars(const char* first, const char* last, double& value, chars_format fmt = chars_format::general);
from_chars_result from_chars(const char* first, const char* last, long double& value, chars_format fmt = chars_format::general);
```

### <a name="parameters"></a>Parametreler

*adı*\
Dönüştürülecek karakter arabelleğinin başlangıcını işaret eder.

*soyadına*\
Dönüştürülecek karakter arabelleğinin bitiş öğesinden bir geçen noktayı işaret eder.

*deeri*\
Dönüştürme başarılı olursa dönüştürmenin sonucunu içerir.

*temel*\
Tamsayı dönüştürmeleri için, dönüştürme sırasında kullanılacak temel. 2 ile 36 (dahil) arasında olmalıdır.

*FMT*\
Kayan nokta dönüştürmeleri için, dönüştürülecek karakter dizisinin biçimi. Ayrıntılar için [chars_format](chars-format-class.md) bakın.

### <a name="remarks"></a>Açıklamalar

`from_chars()` \[ `first` `last` Bir sayı deseninin,) \[ `first` `last` geçerli bir Aralık olması için gerekli olduğu, bu dizeyi analiz eden işlevler.

Karakterler ayrıştırılırken boşluk yok sayılır. Örneğin, arabelleğin aksine, `strtod()` arabelleğin geçerli bir sayısal gösterimle başlaması gerekir.

Bir [from_chars_result yapısı](from-chars-result-structure.md)döndürür.

Bir sayı düzeniyle eşleşen bir karakter yoksa, `value` değiştirilmemiş, `from_chars_result.ptr` `first` ve ' a işaret eder `from_chars_result.ec` `errc::invalid_argument` .

Bir sayı düzeniyle yalnızca bazı karakterler eşleşirse, bu, `from_chars_result.ptr` Düzenle eşleşmeyen ilk karaktere işaret eder veya `last` tüm karakterler eşleşiyorsa parametre değeri vardır.

Ayrıştırılmış değer, türüne göre Aralık gösterilebilir tablosunda değilse `value` , `value` değiştirilmemiş ve `from_chars_result.ec` olur `errc::result_out_of_range` .

Aksi takdirde, `value` ayrıştırıldıktan sonra ayrıştırılmış değere ayarlanır ve `from_chars_result.ec` eşittir `errc{}` .

### <a name="example"></a>Örnek

```cpp
#include <charconv>
#include <stdio.h>
#include <string_view>
#include <system_error>

double TestFromChars(const std::string_view sv)
{
    const char* const first = sv.data();
    const char* const last = first + sv.size();
    double dbl;

    const std::from_chars_result res = std::from_chars(first, last, dbl);

    if (res.ec == std::errc{}) // no error
    {
        printf("success: %g\n", dbl);
    }
    else
    {
        printf("Error: %d\n", static_cast<int>(res.ec));
    }

    return dbl;
}

int main()
{
    double dbl = TestFromChars("123.34");
    return 0;
}
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<charconv>

**Ad alanı:** std

/std: c++ 17 veya sonraki bir sürümü gereklidir.

## <a name="see-also"></a>Ayrıca bkz.

[\<charconv>](charconv.md)  
[Gidiş dönüşlerin](https://www.exploringbinary.com/the-shortest-decimal-string-that-round-trips-examples/) 
 en kısa ondalık dizesi [printf () biçim belirticileri](..\c-runtime-library\format-specification-syntax-printf-and-wprintf-functions.md)