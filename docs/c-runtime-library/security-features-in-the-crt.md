---
title: CRT'deki güvenlik özellikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _CRT_SECURE_NO_DEPRECATE
- _CRT_NONSTDC_NO_WARNINGS
- _CRT_SECURE_NO_WARNINGS
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ce188ea5d28fa99d6133129edbace8e2886f0f5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="security-features-in-the-crt"></a>CRT'deki Güvenlik Özellikleri
Birçok eski CRT işlevleri daha güvenli, daha yeni sürümlerde. Güvenli işlevi varsa, daha eski, daha az güvenli sürüm kullanım dışı olarak işaretlenmiş ve yeni sürüme sahip `_s` ("güvenli") soneki.  
  
 Bu bağlamda "kullanım dışı" yalnızca bir işlevin kullanımı önerilmez anlamına gelir; işlev CRT kaldırılması planlanmıştır göstermez.  
  
 Güvenli işlevleri etmeyin engellemek veya güvenlik hataları düzeltin; Bunun yerine, ortaya çıkan hataları yakalar. Bunlar hata koşulları için ek denetimleri gerçekleştirmek ve bir hata olması durumunda, bunlar bir hata işleyicisi çağırma (bkz [parametre doğrulaması](../c-runtime-library/parameter-validation.md)).  
  
 Örneğin, `strcpy` işlevi vardır, kopyalama dize hedef arabelleğini için çok büyük olup olmadığını belirten bir yolu yoktur. Ancak, güvenli kendisine karşılık gelen `strcpy_s`, bir parametre olarak arabellek boyutunu alır, böylece bir arabellek taşması olmadığını belirleyebilir meydana gelir. Kullanırsanız `strcpy_s` on karakterleri bir hatadır, bir bölümü üzerinde; on karakter arabellek, içine kopyalamak için `strcpy_s` , hata düzeltemezsiniz ancak bu, hata algılayabilir ve geçersiz parametre işleyicisi çağırarak bildirin.  
  
## <a name="eliminating-deprecation-warnings"></a>Kullanımdan kaldırma uyarıları ortadan  
 Kullanımdan kaldırma uyarıları daha eski, daha az güvenli işlevler için ortadan kaldırmak için birkaç yolu vardır. Yalnızca tanımlamak için en kolayıdır `_CRT_SECURE_NO_WARNINGS` veya [uyarı](../preprocessor/warning.md) pragması. Ya da kullanımdan kaldırma uyarıları devre dışı bırakır, ancak Elbette uyarılar neden güvenlik sorunları hala mevcut. Uyarıları etkin ve yeni CRT güvenlik özelliklerden yararlanmak kullanımdan bırakın kadar iyidir.  
  
 C++'da, bunu yapmanın en kolay yolu kullanmaktır [güvenli şablon aşırı yüklemeler](../c-runtime-library/secure-template-overloads.md), hangi birçok durumda ortadan kullanımdan kaldırma uyarıları bu işlevlerin yeni güvenli sürümlerini çağrıları ile kullanım dışı işlev çağrıları değiştirerek. Örneğin, bu kullanım çağrısına göz önünde bulundurun `strcpy`:  
  
```  
char szBuf[10];   
strcpy(szBuf, "test"); // warning: deprecated   
```  
  
 Tanımlama `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` değiştirerek 1 uyarı ortadan kaldırır gibi `strcpy` çağrısı `strcpy_s`, arabellek taşmaları engeller. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../c-runtime-library/secure-template-overloads.md).  
  
 Güvenli şablon aşırı yüklemeleri olmadan bu kullanım dışı işlevleri için kesinlikle güvenli sürümlerini kullanmak üzere kodunuzu el ile güncelleştirme dikkate almalısınız.  
  
 Başka bir kullanımdan kaldırma uyarıları, güvenlik, ilgisiz POSIX işlevleri kaynağıdır. Standart kullanıcıların eşdeğerleriyle POSIX işlev adları (örneğin, değiştirme [erişim](../c-runtime-library/reference/access-crt.md) için [_access](../c-runtime-library/reference/access-waccess.md)), veya tanımlayarak POSIX ile ilgili kullanımdan kaldırma uyarıları devre dışı bırakma `_CRT_NONSTDC_NO_WARNINGS`. Daha fazla bilgi için bkz: [Uyumluluk](compatibility.md).  
  
## <a name="additional-security-features"></a>Ek güvenlik özellikleri  
 Güvenlik özelliklerden bazıları şunlardır:  
  
-   `Parameter Validation`. Her iki güvenli işlevleri ve işlevleri birçok önceden var olan sürümü CRT işlevleri için geçirilen parametre doğrulanır. Bu doğrulama şunları içerir:  
  
    -   Denetleme `NULL` değerleri işlevlere geçirilen.  
  
    -   Numaralandırılmış değerler geçerliliğini denetleniyor.  
  
    -   Tam sayı değerleri geçerli aralıklardaki olduğunu denetleniyor.  
  
-   Daha fazla bilgi için bkz: [parametre doğrulaması](../c-runtime-library/parameter-validation.md).  
  
-   Geçersiz parametreler için bir işleyici de geliştiriciler için erişilebilir. Bir mekanizmanın ve uygulama çıkma yerine geçersiz bir parametre karşılaşıldığında CRT bu sorunları denetlemek için bir yol sağlar. [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)işlevi.  
  
-   `Sized Buffers`. Güvenli işlevleri arabellek boyutu bir arabelleğe Yazar herhangi bir işlev geçirilmesi gerekir. Güvenli sürümleri, kötü amaçlı kod yürütmek izin verebilir tehlikeli arabellek taşması hatalarını önlemek için yardımcı yazmadan önce arabellek yeterince büyük olduğunu doğrulayın. Genellikle bu işlevlerin dönüş bir `errno` hata kodunu yazın ve arabellek boyutu çok küçükse geçersiz parametre işleyicisi çağırma. Giriş önbelleklerden okuma işlevleri `gets`, boyut sınırı belirtmek ihtiyaç duyduğunuz güvenli sürümlere sahip.  
  
-   `Null termination`. Sol olası olmayan sonlandırılmış dizeler, dizeleri olduğundan emin olun güvenli sürümlerde bazı işlevler null düzgün bir şekilde sonlandırıldı.  
  
-   `Enhanced error reporting`. Güvenli işlevleri ile önceden var olan işlevler kullanılabilir olandan daha fazla hata bilgileriyle hata kodlarını döndürür. Güvenli işlevleri ve önceden var olan işlevlerin çoğunu şimdi kurun `errno` ve genellikle bir `errno` türü de daha iyi hata raporlama sağlamak için kod.  
  
-   `Filesystem security`. Güvenli dosya g/ç API'leri destek güvenli dosya erişimi varsayılan durumda.  
  
-   `Windows security`. Güvenli işlem API'leri güvenlik ilkeleri uygulayabilir ve ACL'leri belirtilmesine olanak tanır.  
  
-   `Format string syntax checking`. Geçersiz dizeler algılandığında, örneğin, hatalı türü alan karakterleri kullanarak `printf` biçim dizeleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Parametre doğrulama](../c-runtime-library/parameter-validation.md)   
 [Güvenli şablon aşırı yüklemeleri](../c-runtime-library/secure-template-overloads.md)   
 [CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)