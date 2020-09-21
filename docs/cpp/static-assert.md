---
title: static_assert
ms.date: 07/29/2019
f1_keywords:
- static_assert_cpp
helpviewer_keywords:
- assertions [C++], static_assert
- static_assert
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
ms.openlocfilehash: b30af5fcf5d4f58143e657d84e743ef09a34e268
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742976"
---
# <a name="static_assert"></a>static_assert

Derleme zamanında yazılım onayını sınar. Belirtilen sabit ifade ise, **`false`** derleyici belirtilen iletiyi görüntüler, varsa, derleme C2338 hatasıyla başarısız olur; aksi takdirde, bildirimin etkisi yoktur.

## <a name="syntax"></a>Söz dizimi

```
static_assert( constant-expression, string-literal );

static_assert( constant-expression ); // C++17 (Visual Studio 2017 and later)
```

### <a name="parameters"></a>Parametreler

*Sabit ifadesi*\
Boole değerine dönüştürülemeyen bir integral sabit ifadesi. Değerlendirilen ifade sıfır (false) ise, *dize-sabit* parametresi görüntülenir ve derleme hata vererek başarısız olur. İfade sıfır değilse (true) **`static_assert`** bildiriminde hiçbir etkisi yoktur.

*dize sabit değeri*\
*Sabit ifade* parametresi sıfırsa görüntülenen bir ileti. İleti, derleyicinin [taban karakter kümesindeki](../c-language/ascii-character-set.md) bir karakter dizesidir; Yani [çok baytlı veya geniş karakterler](../c-language/multibyte-and-wide-characters.md)değildir.

## <a name="remarks"></a>Açıklamalar

Bir bildirimin *sabit ifade* parametresi **`static_assert`** bir *yazılım*onayını temsil eder. Yazılım onay belgesi, programınızda belirli bir noktada doğru olması beklenen bir koşulu belirtir. Koşul doğru ise, **`static_assert`** bildirimin hiçbir etkisi yoktur. Koşul false ise, onay başarısız olur, derleyici iletiyi *dize sabit değeri* parametresinde görüntüler ve derleme hata vererek başarısız olur. Visual Studio 2017 ve üzeri sürümlerde dize-sabit parametresi isteğe bağlıdır.

**`static_assert`** Bildirim, derleme zamanında bir yazılım onayını sınar. Buna karşılık, [onaylama makrosu ve _assert ve _wassert işlevleri](../c-runtime-library/reference/assert-macro-assert-wassert.md) , bir yazılım onayını çalışma zamanında test ediyor ve boşluk veya zaman içinde çalışma süresi maliyeti doğurur. **`static_assert`** Bildirim, şablon bağımsız değişkenleri *sabit ifade* parametresine dahil edildiğinden, özellikle hata ayıklama için yararlıdır.

Derleyici, **`static_assert`** bildirime rastlana kadar sözdizimi hataları için bildirimi inceler. Derleyici, bir şablon parametresine bağlı değilse, *sabit ifade* parametresini hemen değerlendirir. Aksi halde, derleyici, şablon örneği oluşturulurken *sabit ifade* parametresini değerlendirir. Sonuç olarak, derleyici, bildirim ile karşılaşıldığında bir kez tanılama iletisi ve şablon örneği oluşturulduğunda bir hata verebilir.

**`static_assert`** Anahtar sözcüğünü ad alanı, sınıf veya blok kapsamı ' nde kullanabilirsiniz. ( **`static_assert`** Anahtar sözcüğü, ad alanı kapsamında kullanılabilmesi için, programınıza yeni bir ad sunmasa bile, teknik olarak bir bildirimidir.)

## <a name="description-of-static_assert-with-namespace-scope"></a>Ad alanı kapsamına sahip static_assert açıklaması

Aşağıdaki örnekte, **`static_assert`** bildiriminde ad alanı kapsamı vardır. Derleyici, türü boyutunu bildiğinden `void *` , ifade hemen değerlendirilir.

## <a name="example-of-static_assert-with-namespace-scope"></a>Ad alanı kapsamına sahip static_assert örneği

```cpp
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");
```

## <a name="description-of-static_assert-with-class-scope"></a>Sınıf kapsamıyla static_assert açıklaması

Aşağıdaki örnekte, **`static_assert`** bildiriminde sınıf kapsamı vardır. , **`static_assert`** Bir şablon parametresinin *düz bir eski veri* (pod) türü olduğunu doğrular. Derleyici **`static_assert`** bildirildiği zaman bildirimi inceler, ancak sınıf şablonu içinde örneklendirilene kadar *sabit ifade* parametresini değerlendirmez `basic_string` `main()` .

## <a name="example-of-static_assert-with-class-scope"></a>Sınıf kapsamına sahip static_assert örneği

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

## <a name="description"></a>Description

Aşağıdaki örnekte, **`static_assert`** bildiriminde blok kapsamı vardır. **`static_assert`** VMPage yapısının boyutunun, sistemin sanal bellek PageSize değerine eşit olduğunu doğrular.

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
[#error yönergesi (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)<br/>
[onaylama makrosu, _assert _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)<br/>
[Şablonlar](../cpp/templates-cpp.md)<br/>
[ASCII karakter kümesi](../c-language/ascii-character-set.md)<br/>
[Bildirimler ve tanımlar](declarations-and-definitions-cpp.md)
