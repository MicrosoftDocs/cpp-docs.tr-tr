---
title: static_assert
ms.date: 07/29/2019
f1_keywords:
- static_assert_cpp
helpviewer_keywords:
- assertions [C++], static_assert
- static_assert
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
ms.openlocfilehash: 4ac79c23379dd1bf1c85521fdf0c28947d3b7ab9
ms.sourcegitcommit: 20a1356193fbe0ddd1002e798b952917eafc3439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68661592"
---
# <a name="staticassert"></a>static_assert

Derleme zamanında yazılım onayını sınar. Belirtilen sabit ifade FALSE ise, derleyici belirtilen iletiyi, varsa, bir hata varsa ve derleme C2338 hatasıyla başarısız olur. Aksi takdirde, bildirimin etkisi yoktur.

## <a name="syntax"></a>Sözdizimi

```
static_assert( constant-expression, string-literal );

static_assert( constant-expression ); // C++17 (Visual Studio 2017 and later)
```

#### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*constant-expression*|Boole değerine dönüştürülemeyen bir integral sabit ifadesi.<br /><br /> Değerlendirilen ifade sıfır (false) ise, *dize-sabit* parametresi görüntülenir ve derleme hata vererek başarısız olur. İfade sıfır değilse (true), **static_assert** bildiriminin etkisi yoktur.|
|*dize sabit değeri*|*Sabit ifade* parametresi sıfırsa görüntülenen bir ileti. İleti, derleyicinin [taban karakter kümesindeki](../c-language/ascii-character-set.md) bir karakter dizesidir; Yani [çok baytlı veya geniş karakterler](../c-language/multibyte-and-wide-characters.md)değildir.|

## <a name="remarks"></a>Açıklamalar

Bir **static_assert** bildiriminin *sabit ifade* parametresi bir *yazılım*onayını temsil eder. Yazılım onay belgesi, programınızda belirli bir noktada doğru olması beklenen bir koşulu belirtir. Koşul doğru ise, **static_assert** bildiriminin etkisi yoktur. Koşul false ise, onay başarısız olur, derleyici iletiyi *dize sabit değeri* parametresinde görüntüler ve derleme hata vererek başarısız olur. Visual Studio 2017 ve üzeri sürümlerde dize-sabit parametresi isteğe bağlıdır.

**Static_assert** bildirimi, derleme zamanında bir yazılım onayını sınar. Buna karşılık, [onaylama makrosu ve _onaylama ve _aşi işlevleri](../c-runtime-library/reference/assert-macro-assert-wassert.md) , bir yazılım onayını çalışma zamanında test ediyor ve bir çalışma zamanı maliyetine boşluk veya saat içinde neden olacak. Şablon bağımsız değişkenleri *sabit ifade* parametresine dahil edilebilir olduğundan, **static_assert** bildirimi özellikle hata ayıklama için yararlıdır.

Derleyici, bildirime karşılaşıldığında sözdizimi hataları için **static_assert** bildirimini inceler. Derleyici, bir şablon parametresine bağlı değilse, *sabit ifade* parametresini hemen değerlendirir. Aksi halde, derleyici, şablon örneği oluşturulurken *sabit ifade* parametresini değerlendirir. Sonuç olarak, derleyici, bildirim ile karşılaşıldığında bir kez tanılama iletisi ve şablon örneği oluşturulduğunda bir hata verebilir.

Ad alanı, sınıf veya blok kapsamındaki **static_assert** anahtar sözcüğünü kullanabilirsiniz. ( **Static_assert** anahtar sözcüğü Teknik olarak bir bildirimde bulunur, ancak bu ad alanı kapsamında kullanılabilmesi için programınıza yeni bir ad sunmaz.)

## <a name="description"></a>Açıklama

Aşağıdaki örnekte, **static_assert** bildiriminde ad alanı kapsamı vardır. Derleyici, türü `void *`boyutunu bildiğinden, ifade hemen değerlendirilir.

## <a name="example"></a>Örnek

```cpp
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");
```

## <a name="description"></a>Açıklama

Aşağıdaki örnekte, **static_assert** bildirimi sınıf kapsamına sahiptir. **Static_assert** , bir şablon parametresinin *düz bir eski veri* (pod) türü olduğunu doğrular. Derleyici, bildirildiği zaman **static_assert** bildirimini inceler, ancak `basic_string` sınıf şablonu ' de `main()`örneklendirilene kadar *sabit ifade* parametresini değerlendirmez.

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

Aşağıdaki örnekte, **static_assert** bildiriminde blok kapsamı vardır. **Static_assert** , VMPage yapısının boyutunun, sistemin sanal bellek PageSize değerine eşit olduğunu doğrular.

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