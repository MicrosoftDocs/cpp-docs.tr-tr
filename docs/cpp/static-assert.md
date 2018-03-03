---
title: static_assert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- static_assert_cpp
dev_langs:
- C++
helpviewer_keywords:
- C++ keywords, static_assert
- C2338
- assertions [C++], static_assert
- static_assert
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 660b91f4902e42d393509aa190172e53839b2621
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="staticassert"></a>static_assert
Derleme zamanında yazılım onaylama sınar. Belirtilen sabit ifade ise `false`, bir tane belirtilmişse derleyici belirtilen iletisi görüntüler ve derleme C2338 hatasıyla başarısız oluyor; Aksi takdirde, bildirim hiçbir etkisi olmaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```   
static_assert( constant-expression, string-literal );  

**Visual Studio 2017 and later:**
static_assert( constant-expression ); 
```  
  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`constant-expression`|Bir Boolean değerine dönüştürülebilir bir tam sayı sabit ifade.<br /><br /> Değerlendirilmiş ifadeyi sıfırsa (false), `string-literal` parametresi görüntülenir ve derleme bir hata ile başarısız olur. İfade sıfır olmayan bir değer (true) ise, `static_assert` bildirimi etkisi yoktur.|  
|`string-literal`|Varsa görüntülenen bir ileti `constant-expression` parametresi sıfırda. İleti bir karakter dizesidir [temel karakter kümesi](../c-language/ascii-character-set.md) olduğu derleyici; değil [birden çok baytlı veya uluslararası karakter](../c-language/multibyte-and-wide-characters.md).|  
  
## <a name="remarks"></a>Açıklamalar  
 `constant-expression` Parametresinin bir `static_assert` bildirimi gösteren bir *yazılım onaylama*. Bir yazılım onaylama programınızdaki belirli bir noktada doğru olması için beklediğiniz bir koşulu belirtir. Koşul true ise `static_assert` bildirimi etkisi yoktur. Koşul yanlış ise, onaylama işlemi başarısız olursa, derleyici iletisi görüntüler `string-literal` parametre ve bir hata ile derleme başarısız oluyor. Visual Studio 2017 ve daha sonra değişmez dize değeri parametresi isteğe bağlıdır. 
  
 `static_assert` Bildirimi derleme zamanında yazılım onaylama sınar. Buna karşılık, [assert makrosu, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) makrosu çalışma zamanında yazılım onaylama sınar ve çalışma zamanında Maliyet alanı ya da saat oluşturur. `static_assert` Bildirimidir bağımsız şablon eklenebilir olduğundan, şablonları hata ayıklama için özellikle yararlı `constant-expression` parametresi.  
  
 Derleyici inceler `static_assert` bildirimi karşılaşıldığında söz dizimi hataları için bildirimi. Derleyici değerlendirir `constant-expression` hemen bir şablon parametresi dayanmayacak, parametre. Aksi takdirde derleyici değerlendirir `constant-expression` şablon örneği oluşturulduğunda parametresi. Sonuç olarak, derleyici bir tanılama iletisi kez ne zaman sorun bildirimi ile karşılaştı ve yeniden ne zaman şablon örneği.  
  
 Kullanabileceğiniz `static_assert` anahtar sözcük ad alanı, sınıf veya blok kapsamı. ( `static_assert` Sözcüktür bildirimi teknik olarak, ad alanı kapsamda kullanılabildiğinden, yeni bir ad, programa sunmaz olsa bile.)  
  
## <a name="description"></a>Açıklama  
 Aşağıdaki örnekte, `static_assert` bildirimi ad alanı kapsama sahiptir. Yazı tipi boyutu derleyici bildiği için `void *`, ifade hemen değerlendirilir.  
  
## <a name="example"></a>Örnek  
  
```  
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");  
```  
  
## <a name="description"></a>Açıklama  
 Aşağıdaki örnekte, `static_assert` bildirimi sınıf kapsamı vardır. `static_assert` Şablon parametresi olduğunu doğrulayan bir *düz eski verileri* (POD) yazın. Derleyici inceler `static_assert` bildirilmiş ancak değil değerlendirmek bildirimi `constant-expression` kadar parametresi `basic_string` sınıf şablonu örneği `main()`.  
  
## <a name="example"></a>Örnek  
  
```  
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
 Aşağıdaki örnekte, `static_assert` bildirimi blok kapsamı vardır. `static_assert` VMPage yapısı boyutunu sisteminin sanal bellek pagesize eşit olduğunu doğrular.  
  
## <a name="example"></a>Örnek  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Onaylama ve kullanıcının sağladığı iletiler (C++)](../cpp/assertion-and-user-supplied-messages-cpp.md)   
 [#error yönergesi (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)   
 [Assert makrosu, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [Şablonları](../cpp/templates-cpp.md)   
 [ASCII karakter kümesi](../c-language/ascii-character-set.md)   
 [Bildirimler ve tanımlar](declarations-and-definitions-cpp.md)