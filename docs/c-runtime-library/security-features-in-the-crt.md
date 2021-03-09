---
title: CRT'deki Güvenlik Özellikleri
description: Microsoft C çalışma zamanındaki güvenli CRT işlevlerine genel bakış.
ms.date: 09/29/2020
ms.topic: conceptual
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
ms.openlocfilehash: 96642e5e79f9df7c0a063582408c0463600be20f
ms.sourcegitcommit: 90c300b74f6556cb5d989802d2e80d79542f55e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2021
ms.locfileid: "102514687"
---
# <a name="security-features-in-the-crt"></a>CRT'deki Güvenlik Özellikleri

Birçok eski CRT işlevin daha yeni ve daha güvenli sürümleri vardır. Güvenli bir işlev varsa, daha eski, daha az güvenli sürüm kullanım dışı olarak işaretlenir ve yeni sürüm `_s` ("Secure") sonekine sahiptir.

Bu bağlamda, "kullanım dışı" işlevin kullanılması önerilmez. İşlevin CRT 'dan kaldırılmak üzere zamanlandığı anlamına gelmez.

Güvenli işlevler güvenlik hatalarını engellemez veya düzeltmez. Bunun yerine, hatalar oluştuğunda bunları yakalar. Bunlar hata koşulları için ek denetimler gerçekleştirir. Bir hata varsa, bir hata işleyicisi çağırır (bkz. [parametre doğrulama](../c-runtime-library/parameter-validation.md)).

Örneğin, `strcpy` işlevi kopyalama yaptığı dizenin hedef arabellek için çok büyük olup olmadığını söyleyebilir. Güvenli karşılığı, `strcpy_s` arabelleğin boyutunu parametre olarak alır. Bu nedenle, bir arabellek taşmasının gerçekleşeceğini tespit edebilir. `strcpy_s`11 karakteri 10 karakter arabelleğine kopyalamak için kullanırsanız, bu, bölüminizdeki bir hatadır; hata `strcpy_s` bilgilerinizi düzeltemezsiniz. Ancak hatayı algılayabilir ve geçersiz parametre işleyicisini çağırarak sizi bilgilendirebilirler.

## <a name="eliminating-deprecation-warnings"></a>Kullanımdan kaldırma uyarılarını ortadan kaldırma

Daha eski, daha az güvenli işlevler için kullanımdan kaldırma uyarılarını ortadan kaldırmanın birkaç yolu vardır. En basit, `_CRT_SECURE_NO_WARNINGS` [Uyarı](../preprocessor/warning.md) pragmasını tanımlamak veya kullanmak için yeterlidir. Kullanımdan kaldırma uyarılarını devre dışı bırakır, ancak uyarıların oluşmasına neden olan güvenlik sorunları hala mevcut olur. Kullanımdan kaldırma uyarılarını etkin bırakmak ve yeni CRT güvenlik özelliklerinden yararlanmak daha iyidir.

C++ ' da, bunu yapmanın en kolay yolu [Güvenli şablon aşırı yüklemelerini](../c-runtime-library/secure-template-overloads.md)kullanmaktır. Bu, çok sayıda durumda çağrıları, bu işlevlerin güvenli sürümlerine yönelik çağrılarla kullanım dışı işlevlerle değiştirerek kullanımdan kaldırma uyarılarını ortadan kaldıracak. Örneğin, bu kullanımdan kaldırılan bu çağrıyı göz önünde bulundurun `strcpy` :

```
char szBuf[10];
strcpy(szBuf, "test"); // warning: deprecated
```

`_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES`1 olarak tanımlamak `strcpy` , çağrısı değiştirilerek `strcpy_s` , arabellek taşmalarını önleyen uyarıyı ortadan kaldırır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../c-runtime-library/secure-template-overloads.md).

Güvenli şablon aşırı yüklemeleri olmadan kullanım dışı bırakılan işlevlerde, güvenli sürümleri kullanmak için kodunuzu el ile güncelleştirmeyi göz önünde bulundurmanız gerekir.

Güvenlikle ilgili olmayan başka bir kullanımdan kaldırma uyarısı kaynağı, POSIX işlevleridir. POSIX işlev adlarını standart eşdeğerleriyle değiştirin (örneğin, [_access](../c-runtime-library/reference/access-waccess.md) [erişimi](../c-runtime-library/reference/access-crt.md) DEĞIŞTIRIN) veya ekleyerek POSIX ile ilgili kullanımdan kaldırma uyarılarını devre dışı bırakın `_CRT_NONSTDC_NO_WARNINGS` . Daha fazla bilgi için bkz. [Uyumluluk](compatibility.md).

## <a name="additional-security-features"></a>Ek güvenlik özellikleri

Bazı güvenlik özellikleri şunları içerir:

- `Parameter Validation`. Güvenli işlevler ve bunlara ait güvenli olmayan karşılıklarının birçoğu, parametreleri doğrular. Doğrulama şunlar olabilir:

  - **Null** değerler denetleniyor.
  - Numaralandırılmış değerler geçerliliği denetleniyor.
  - İntegral değerlerinin geçerli aralıklar halinde olup olmadığı denetleniyor.

- Daha fazla bilgi için bkz. [parametre doğrulama](../c-runtime-library/parameter-validation.md).

- Geçersiz parametrelere yönelik bir işleyiciye geliştirici için de erişilebilir. Bir işlev geçersiz bir parametreyle karşılaştığında, uygulamadan çıkma ve çıkış yapmak yerine CRT, bu sorunları [_set_invalid_parameter_handler _set_thread_local_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)aracılığıyla denetlemenizi sağlar.

- `Sized Buffers`. Arabellek boyutunu, arabelleğe yazan herhangi bir güvenli işleve geçirmeniz gerekir. Güvenli sürümler, arabelleğe yazılmadan önce arabelleğin yeterince büyük olduğunu doğrular. Kötü amaçlı kodun yürütülmesine izin veren tehlikeli arabellek taşma hatalarından kaçınmaya yardımcı olur. Bu işlevler genellikle bir `errno` hata kodu döndürür ve arabelleğin boyutu çok küçükse geçersiz parametre işleyicisini çağırır. Gibi giriş arabelleklerinden okunan işlevlerin `gets` , en büyük boyut belirtmenizi gerektiren güvenli sürümleri vardır.

- `Null termination`. Sonlandırılamayan dizelerin kullanıldığı bazı işlevler, dizelerin düzgün şekilde null olarak sonlandırıldığından emin olan güvenli sürümlere sahiptir.

- `Enhanced error reporting`. Güvenli işlevler, önceden varolan işlevlerde kullanılabilir olandan daha fazla hata bilgisine sahip hata kodları döndürüyor. Önceden var olan işlevlerin güvenli işlevleri ve çoğu artık ayarlanır `errno` ve `errno` daha iyi hata raporlaması sağlamak için genellikle bir kod türü de döndürür.

- `Filesystem security`. Güvenli dosya g/ç API 'Leri, varsayılan durumda güvenli dosya erişimini destekler.

- `Windows security`. Güvenli işlem API 'Leri güvenlik ilkeleri uygular ve ACL 'Lerin belirtilmesine izin verir.

- `Format string syntax checking`. Geçersiz dizeler algılandı, örneğin, Biçim dizelerinde yanlış tür alanı karakterleri kullanılıyor `printf` .

## <a name="see-also"></a>Ayrıca bkz.

[Parametre doğrulama](../c-runtime-library/parameter-validation.md)<br/>
[Güvenli şablon aşırı yüklemeleri](../c-runtime-library/secure-template-overloads.md)<br/>
[C çalışma zamanı (CRT) ve C++ standart kitaplığı (STL) `.lib` dosyaları](../c-runtime-library/crt-library-features.md)
