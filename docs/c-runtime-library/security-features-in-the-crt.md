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
ms.openlocfilehash: 1b42c766a7b75cb3f4d5c20d715968905d529d04
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361002"
---
# <a name="security-features-in-the-crt"></a>CRT'deki Güvenlik Özellikleri

Birçok eski CRT işlevi daha yeni, daha güvenli sürümlere sahiptir. Güvenli bir işlev varsa, eski, daha az güvenli sürüm amortismana lı `_s` olarak işaretlenir ve yeni sürümde ("güvenli") sonek bulunur.

Bu bağlamda, "amortismana" sadece bir işlevin kullanımı tavsiye edilmez anlamına gelir; işlevinin CRT'den kaldırılacak zamanlandığını göstermez.

Güvenli işlevler güvenlik hatalarını önlemez veya düzeltmez; bunun yerine, oluştuklarında hataları yakalarlar. Hata koşulları için ek denetimler gerçekleştirirler ve bir hata durumunda bir hata işleyicisi çağırırlar [(bkz. Parametre Doğrulama).](../c-runtime-library/parameter-validation.md)

Örneğin, işlevin, `strcpy` kopyaladığının dize hedef arabelleği için çok büyük olup olmadığını söylemenin bir yolu yoktur. Ancak, güvenli muadili, `strcpy_s`arabellek boyutunu bir parametre olarak alır, böylece bir arabellek taşması oluşacak olup olmadığını belirleyebilirsiniz. On bir `strcpy_s` karakteri on karakterli bir arabelleğe kopyalamak için kullanırsanız, bu sizin tarafınızdan bir hatadır; `strcpy_s` hatanızı düzeltemez, ancak hatanızı algılayabilir ve geçersiz parametre işleyicisini çağırarak sizi bilgilendirebilir.

## <a name="eliminating-deprecation-warnings"></a>Amortisman uyarılarını ortadan kaldırma

Eski, daha az güvenli işlevler için amortisman uyarılarını ortadan kaldırmanın çeşitli yolları vardır. En basiti, `_CRT_SECURE_NO_WARNINGS` [uyarı](../preprocessor/warning.md) pragmasını tanımlamak veya kullanmaktır. Ya amortisman uyarıları devre dışı, ama tabii ki uyarılar neden güvenlik sorunları hala var. Amortisman uyarılarını etkin bırakmak ve yeni CRT güvenlik özelliklerinden yararlanmak çok daha iyidir.

C++'da bunu yapmanın en kolay yolu, çoğu durumda bu işlevlerin yeni güvenli sürümlerine yapılan çağrılarla amortismanlı işlevlere yapılan çağrıları değiştirerek amortisman uyarılarını ortadan kaldıran [Secure Template Overloads'ı](../c-runtime-library/secure-template-overloads.md)kullanmaktır. Örneğin, bu amortismana lı aramayı `strcpy`şu şekilde düşünün:

```
char szBuf[10];
strcpy(szBuf, "test"); // warning: deprecated
```

1 `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` olarak tanımlanması, aramayı `strcpy` `strcpy_s`değiştirerek uyarıyı ortadan kaldırır , bu da arabellek taşmasını önler. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../c-runtime-library/secure-template-overloads.md)

Güvenli şablon aşırı yüklemeleri olmadan amortismana tabi olan işlevler için, güvenli sürümleri kullanmak için kodunuzu el ile güncelleştirmeyi kesinlikle düşünmelisiniz.

Güvenlikle ilgisi olmayan bir diğer amortisman uyarıları kaynağı da POSIX işlevleridir. POSIX işlev adlarını standart eşdeğerleriyle değiştirin (örneğin, `_CRT_NONSTDC_NO_WARNINGS` [_access'a erişimi](../c-runtime-library/reference/access-crt.md) değiştirin ) veya POSIX ile ilgili amortisman uyarılarını tanımlayarak devre dışı [_access](../c-runtime-library/reference/access-waccess.md) Daha fazla bilgi için [Uyumluluk'a](compatibility.md)bakın.

## <a name="additional-security-features"></a>Ek Güvenlik Özellikleri

Güvenlik özelliklerinden bazıları şunlardır:

- `Parameter Validation`. CRT işlevlerine geçirilen parametreler, hem güvenli işlevlerde hem de işlevlerin önceden var olan birçok sürümünde doğrulanır. Bu doğrulamalar şunlardır:

  - Null **değerleri** işlevleri geçti denetle.

  - Geçerlilik için numaralandırılmış değerleri denetleme.

  - Integral değerlerinin geçerli aralıklarda olup olmadığını denetleme.

- Daha fazla bilgi için [Parametre Doğrulama'ya](../c-runtime-library/parameter-validation.md)bakın.

- Geçersiz parametreler için bir işleyici de geliştirici tarafından erişilebilir. Geçersiz bir parametreyle karşılaştığında, uygulamanın öne çıkması ve çıkmak yerine, CRT bu sorunları [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) işleviyle denetlemek için bir yol sağlar.

- `Sized Buffers`. Güvenli işlevler, arabellek boyutunun arabelleğe yazan herhangi bir işleve geçirilmesini gerektirir. Güvenli sürümler, arabellek ona yazmadan önce yeterince büyük olduğunu doğrular, kötü amaçlı kod yürütmek için izin verebilir tehlikeli arabellek taşma hataları önlemek için yardımcı. Bu işlevler `errno` genellikle bir hata kodu türü döndürür ve arabellek boyutu çok küçükse geçersiz parametre işleyicisini çağırır. Giriş arabelleklerinden okunan işlevler, örneğin, `gets`maksimum boyut belirtmenizi gerektiren güvenli sürümlere sahiptir.

- `Null termination`. Sonlandırılmayan dizeleri bırakan bazı işlevler, dizelerin düzgün bir şekilde geçersiz kılınmasını sağlayan güvenli sürümlere sahiptir.

- `Enhanced error reporting`. Güvenli işlevler, önceden varolan işlevlerle birlikte kullanılabilenden daha fazla hata bilgisiyle hata kodları döndürdü. Güvenli işlevler ve önceden varolan `errno` işlevlerin çoğu `errno` artık ayarlanır ve daha iyi hata raporlaması sağlamak için genellikle bir kod türünü de döndürmektedir.

- `Filesystem security`. Güvenli dosya G/Ç API'leri varsayılan durumda güvenli dosya erişimini destekler.

- `Windows security`. Güvenli işlem API'leri güvenlik ilkelerini uygular ve ADC'lerin belirtilmesine izin verir.

- `Format string syntax checking`. Geçersiz dizeleri, örneğin, `printf` biçim dizeleri yanlış tür alan karakterleri kullanılarak algılanır.

## <a name="see-also"></a>Ayrıca bkz.

[Parametre Doğrulama](../c-runtime-library/parameter-validation.md)<br/>
[Güvenli Şablon Overloads](../c-runtime-library/secure-template-overloads.md)<br/>
[CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)
