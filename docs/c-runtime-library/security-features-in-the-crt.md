---
title: CRT'deki Güvenlik Özellikleri
ms.date: 11/04/2016
f1_keywords:
- _CRT_SECURE_NO_DEPRECATE
- _CRT_NONSTDC_NO_WARNINGS
- _CRT_SECURE_NO_WARNINGS
helpviewer_keywords:
- security deprecation warnings [C++]
- CRT_NONSTDC_NO_DEPRECATE
- buffers [C++], buffer overruns
- deprecation warnings (security-related), disabling
- _CRT_NONSTDC_NO_WARNINGS
- security [CRT]
- _CRT_SECURE_NO_WARNINGS
- _CRT_NONSTDC_NO_DEPRECATE
- _CRT_SECURE_NO_DEPRECATE
- security-enhanced CRT
- CRT_SECURE_NO_WARNINGS
- CRT_SECURE_NO_DEPRECATE
- deprecation warnings (security-related)
- buffer overruns
- CRT_NONSTDC_NO_WARNINGS
- CRT, security enhancements
- parameters [C++], validation
ms.assetid: d9568b08-9514-49cd-b3dc-2454ded195a3
ms.openlocfilehash: a6ebbb09bc724fe1d3b2f06a27cb6708acb7566b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538366"
---
# <a name="security-features-in-the-crt"></a>CRT'deki Güvenlik Özellikleri

Eski pek çok CRT işlevi daha yeni ve daha güvenli sürümleri vardır. Güvenli işlevi varsa, eski ve daha az güvenli sürümü kullanım dışı olarak işaretlenmiş ve yeni sürümü, `_s` ("güvenli") soneki.

Bu bağlamda "kullanım dışı" yalnızca işlevin kullanımı önerilmez anlamına gelir; işlev CRT kaldırılması için zamanlandı göstermez.

Güvenli işlevler değil engellemek veya güvenlik hataları düzeltmek; Bunun yerine, ortaya çıkan hataları yakalayın. Bunlar hata koşulları için ek denetimler gerçekleştirmek ve bir hata olması durumunda, bunlar bir hata işleyicisini çağırır (bkz [Parameter Validation](../c-runtime-library/parameter-validation.md)).

Örneğin, `strcpy` işleve sahip kopyalama dize, hedef arabelleği için çok büyük olup olmadığını belirten bir yolu yoktur. Ancak, güvenli çözümlemesiyle `strcpy_s`, parametre olarak arabellek boyutunu alır, böylece bir arabellek taşması durumunda belirleyebilir meydana gelir. Kullanırsanız `strcpy_s` yapmanıza; bir hata on karakter arabelleğine, on karakter kopyalamak için `strcpy_s` , hata düzeltemezsiniz ancak bu, hata algılama ve geçersiz parametre işleyicisini çağırarak bildirin.

## <a name="eliminating-deprecation-warnings"></a>Kullanımdan kaldırma uyarıları ortadan kaldırır.

Eski ve daha az güvenli işlevler için kullanımdan kaldırılma uyarıları ortadan kaldırmak için birkaç yolu vardır. Basit yalnızca tanımlamaktır `_CRT_SECURE_NO_WARNINGS` veya [uyarı](../preprocessor/warning.md) pragması. Ya da kullanımdan kaldırma uyarıları devre dışı bırakır, ancak Elbette uyarıları neden olan güvenlik sorunları mevcut. Uyarıları etkin ve yeni CRT güvenlik özelliklerinden yararlanmak kullanımdan kaldırma bırakın kadar iyidir.

C++'da, bunu yapmanın en kolay yolu kullanmaktır [güvenli şablon aşırı yüklemeleri](../c-runtime-library/secure-template-overloads.md), çoğu durumda, ortadan kullanımdan kaldırma uyarıları kullanım dışı işlev çağrıları bu işlevlerin güvenli sürümleri yeni çağrıları ile değiştirerek. Örneğin, bu kullanım çağrı düşünün `strcpy`:

```
char szBuf[10];
strcpy(szBuf, "test"); // warning: deprecated
```

Tanımlama `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` değiştirerek 1 uyarı ortadan kaldırır gibi `strcpy` çağrısı `strcpy_s`, arabellek taşmalarına engeller. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../c-runtime-library/secure-template-overloads.md).

Güvenli şablon aşırı yüklemeleri olmadan bu kullanım dışı bırakılan işlevler için kesinlikle güvenli sürümler kullanmak için kodunuzu el ile güncelleştirme dikkate almalısınız.

Başka bir kullanımdan kaldırma uyarıları, güvenlik, ilgisiz POSIX işlevleri kaynağıdır. POSIX işlev adlarını standart eşdeğerleriyle değiştirin (değiştirin; Örneğin, [erişim](../c-runtime-library/reference/access-crt.md) için [_access](../c-runtime-library/reference/access-waccess.md)), veya tanımlayarak POSIX ile ilgili kullanımdan kaldırma uyarıları devre dışı bırakma `_CRT_NONSTDC_NO_WARNINGS`. Daha fazla bilgi için [Uyumluluk](compatibility.md).

## <a name="additional-security-features"></a>Ek güvenlik özellikleri

Güvenlik özelliklerinden bazıları şunlardır:

- `Parameter Validation`. Güvenli her iki işlev ve birçok önceden var olan sürümü işlevleri CRT işlevleri için geçirilen parametre doğrulanır. Bu doğrulama şunlardır:

   - Denetleme **NULL** değerleri, işleve geçirilen.

   - Numaralandırılmış değerler geçerliliğini denetleniyor.

   - Tamsayı değerlerinin geçerli aralığı olduğunu denetleme.

- Daha fazla bilgi için [Parameter Validation](../c-runtime-library/parameter-validation.md).

- Geçersiz parametre işleyicisi da geliştiriciler için erişilebilir. Bir mekanizmanın ve uygulamadan çıkmak yerine geçersiz bir parametre ile karşılaşıldığında CRT ile ilgili sorunları kontrol etmek için bir yol sağlar. [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)işlevi.

- `Sized Buffers`. Güvenli İşlevler, arabellek boyutu bir arabelleğe Yazar herhangi bir işleve geçirilen gerektirir. Güvenli sürümler, yürütülecek kötü amaçlı kod yürütülmesine tehlikeli arabellek taşma hataları önlemeye yardımcı yazmadan önce arabellek büyüklüğü olduğunu doğrulayın. Bu işlevler genellikle döndürür bir `errno` hata kodunu yazın ve arabellek boyutu çok küçükse, geçersiz parametre işleyicisini çağırır. Giriş önbelleklerden okuma işlevleri `gets`, boyut sınırı belirtmek ihtiyaç duyduğunuz güvenli sürümlere sahiptir.

- `Null termination`. Olası olmayan sonlandırılmış dizeler sol bazı işlevler düzgün null ile sonlandırılmış dizeler olduğundan emin olun güvenli sürümleri vardır.

- `Enhanced error reporting`. Güvenli işlevler önceden var olan işlevleriyle kullanılabilir olandan daha fazla hata bilgileri ile hata kodlarını döndürür. Güvenli işlevler ve önceden var olan işlevlerin çoğunu kümesini şimdi `errno` ve genellikle bir `errno` kod türü de daha iyi hata raporlama sağlamak için.

- `Filesystem security`. Güvenli dosya g/ç API'leri destek güvenli dosya erişimi varsayılan durumda.

- `Windows security`. Güvenli işlem API'leri, güvenlik ilkelerini zorunlu kılmasına ve belirtilmesi için sistem ACL'lerini sağlar.

- `Format string syntax checking`. Geçersiz dizeler algılandı, örneğin, yanlış türü alan karakterleri kullanarak `printf` biçim dizeleri.

## <a name="see-also"></a>Ayrıca Bkz.

[Parametre Doğrulama](../c-runtime-library/parameter-validation.md)<br/>
[Güvenli Şablon Aşırı Yüklemeleri](../c-runtime-library/secure-template-overloads.md)<br/>
[CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)