---
title: static_assert
ms.date: 11/04/2016
f1_keywords:
- static_assert_cpp
helpviewer_keywords:
- C++ keywords, static_assert
- C2338
- assertions [C++], static_assert
- static_assert
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
ms.openlocfilehash: d5ef1ba45001a2b1a3ee1f2da46f66224857b070
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330661"
---
# <a name="staticassert"></a>static_assert

Derleme zamanında yazılım onayını sınar. Belirtilen sabit ifade FALSE ise, derleyici bir sağlanır ve derleme hatalarını hata C2338 ile başarısız olursa belirtilen iletiyi görüntüler; Aksi halde bildirimin etkisi yoktur.

## <a name="syntax"></a>Sözdizimi

```
static_assert( constant-expression, string-literal );

static_assert( constant-expression ); // Visual Studio 2017 and later
```

#### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*constant-expression*|Bir Boolean değerine dönüştürülebilen integral sabit ifadesi.<br /><br /> Değerlendirilmiş ifade sıfırsa (false) *dize sabit değeri* parametresi görüntülenir ve derleme bir hata ile başarısız oluyor. İfade sıfır olmayan (true), ise **static_assert** bildiriminin etkisi yoktur.|
|*dize sabit değeri*|Bir ileti görüntülenir *sabit-ifade* parametresi sıfırsa. İleti bir karakter dizesidir [temel karakter kümesinde](../c-language/ascii-character-set.md) olduğundan derleyici; değil [çok baytlı veya geniş karakterler](../c-language/multibyte-and-wide-characters.md).|

## <a name="remarks"></a>Açıklamalar

*Sabit-ifade* parametresinin bir **static_assert** bildirimini temsil eder bir *yazılım onayını*. Yazılım onaylama programınızda belirli bir noktada doğru olması beklenen bir koşulu belirtir. Koşul true ise **static_assert** bildiriminin etkisi yoktur. Koşul yanlışsa onaylama işlemi başarısızsa, derleyici iletisi görüntüler *dize sabit değeri* parametre ve bir hata ile derleme başarısız. Visual Studio 2017 ve sonraki sürümlerinde, dize sabit değeri parametresi isteğe bağlıdır.

**Static_assert** bildirimi derleme zamanında yazılım onayını sınar. Buna karşılık, [assert makrosu, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) makrosu, çalışma zamanında yazılım onayını sınar ve boş alan veya süre çalışma zamanı maliyetine neden olur. **Static_assert** bildirimi, şablon bağımsız değişkenleri eklenebilir olduğundan, şablonları hata ayıklama için özellikle kullanışlıdır *sabit-ifade* parametresi.

Derleyici inceler **static_assert** bildirimi bildirimi oluştuğunda sözdizimi hataları. Derleyici değerlendirir *sabit-ifade* parametresini hemen, bir şablon parametresine bağımlı değildir. Aksi halde, derleyici değerlendirir *sabit-ifade* şablon örneği başlatıldığında parametresi. Sonuç olarak, derleyici bir tanılama iletisi kez ne zaman sorun bildirimle karşılaşıldığında ve yeniden şablon oluşturulduğunda.

Kullanabileceğiniz **static_assert** ad alanı, sınıf veya blok kapsamında anahtar sözcüğü. ( **Static_assert** anahtar sözcüğü, bir bildirim teknik rağmen ad uzayı kapsamında kullanılabildiğinden, yeni adı programınıza sunmaz.)

## <a name="description"></a>Açıklama

Aşağıdaki örnekte, **static_assert** bildirimi ad alanı kapsamına sahiptir. Derleyici türünün boyutunu bildiğinden `void *`, ifade hemen değerlendirilir.

## <a name="example"></a>Örnek

```cpp
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");
```

## <a name="description"></a>Açıklama

Aşağıdaki örnekte, **static_assert** bildirimi sınıf kapsamına sahiptir. **Static_assert** şablon parametresi olduğunu doğrulayan bir *düz eski veriler* (POD) türünde. Derleyici inceler **static_assert** bildirilmiş ancak değerlendirmez bildirimi *sabit-ifade* kadar parametre `basic_string` içindesınıfşablonuoluşturulana`main()`.

## <a name="example"></a>Örnek

```cpp
#include <type_traits>
#include <iosfwd>
namespace std {
template <class CharT, class Traits = std::char_traits<CharT> >
class basic_string {
    static_assert(std::is_pod<CharT>::value,
                  "Template argument CharT must be a POD type in class template basic_string");
    // ...
    };
}

struct NonPOD {
    NonPOD(const NonPOD &) {}
    virtual ~NonPOD() {}
};

int main()
{
    std::basic_string<char> bs;
}
```

## <a name="description"></a>Açıklama

Aşağıdaki örnekte, **static_assert** bildirimi blok kapsamına sahiptir. **Static_assert** VMPage yapısının boyutunun sistemin sanal bellek sayfa için ona eşit olduğunu doğrular.

## <a name="example"></a>Örnek

```cpp
#include <sys/param.h> // defines PAGESIZE
class VMMClient {
public:
    struct VMPage { // ...
           };
    int check_pagesize() {
    static_assert(sizeof(VMPage) == PAGESIZE,
        "Struct VMPage must be the same size as a system virtual memory page.");
    // ...
    }
// ...
};
```

## <a name="see-also"></a>Ayrıca bkz.

[Onaylama ve Kullanıcının Sağladığı İletiler (C++)](../cpp/assertion-and-user-supplied-messages-cpp.md)<br/>
[#error Yönergesi (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)<br/>
[assert Makrosu, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)<br/>
[Şablonlar](../cpp/templates-cpp.md)<br/>
[ASCII Karakter Kümesi](../c-language/ascii-character-set.md)<br/>
[Bildirimler ve Tanımlar](declarations-and-definitions-cpp.md)