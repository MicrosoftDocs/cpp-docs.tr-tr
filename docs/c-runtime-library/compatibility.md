---
title: Uyumluluk
description: Standart C Kitaplığı, POSIX, güvenli CRT ve Mağaza uygulamaları ile Microsoft Universal C çalışma zamanı kitaplığı 'nın (UCRT) uyumluluğunu açıklar.
ms.date: 9/11/2020
helpviewer_keywords:
- CRT, compatibility
- compatibility, C runtime libraries
- compatibility
ms.assetid: 346709cb-edda-4909-9a19-3d253eddb6b7
ms.openlocfilehash: 711d5b3c95269413a0d94f568d3e3cb7b7dff721
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506873"
---
# <a name="compatibility"></a>Uyumluluk

Evrensel C çalışma zamanı kitaplığı (UCRT), C++ uygunluğu için gereken C standart kitaplığının çoğunu destekler. C99 (ISO/ıEC 9899:1999) kitaplığını belirli özel durumlarla uygular:

- içinde katı tür uyumluluğu \<complex.h> .
- `aligned_alloc`Bu, büyük olasılıkla uygulanmayacak, çünkü Windows işletim sistemi hizalanmış ayırmaları desteklemez. `_aligned_malloc`Bunun yerine standart olmayan ' ı kullanın.
- `strerrorlen_s`
- içinde atomik destek \<stdatomic.h>
- iş parçacığı desteği \<threads.h>

UıCRT, POSIX 'nin büyük bir alt kümesini de uygular. 1 (ISO/ıEC 9945-1:1996, POSIX sistem uygulaması program arabirimi) C Kitaplığı. Ancak, belirli bir POSIX standardına tam olarak uyumlu değildir. UıCRT Ayrıca, standart bir parçası olmayan, Microsoft 'a özgü birkaç işlevi ve makroları uygular.

Visual C++ Microsoft uygulamasına özgü işlevler vcruntime kitaplığı 'nda bulunur.  Bu işlevlerin birçoğu iç kullanım içindir ve Kullanıcı kodu tarafından çağrılamaz. Bazıları hata ayıklama ve uygulama uyumluluğuyla kullanılmak üzere belgelenmiştir.

C++ standardı, uygulamaya genel ad alanındaki alt çizgiyle başlayan adları ayırır. Hem POSIX işlevleri hem de Microsoft 'a özgü çalışma zamanı kitaplığı işlevleri genel ad alanında bulunur, ancak standart C çalışma zamanı kitaplığının bir parçası değildir. Bu işlevlerin tercih edilen Microsoft uygulamalarının önde bir alt çizgi olmasının nedeni budur. Taşınabilirlik için UCRT Ayrıca varsayılan adları destekler, ancak Microsoft C++ derleyicisi bunları kullanan kod derlendiğinde kullanımdan kaldırma uyarısı verir. İşlevlerin kendisi değil, yalnızca varsayılan adlar kullanımdan kaldırılmıştır. Uyarıyı bastırmak için, `_CRT_NONSTDC_NO_WARNINGS` özgün POSIX adlarını kullanan koddaki tüm üst bilgileri dahil etmeden önce tanımlayın.

Standart C kitaplığındaki bazı işlevlerin güvenli olmayan kullanım geçmişi, yanlış kullanılan parametreler ve Denetlenmemiş Arabellekler nedeniyle Bu işlevler genellikle koddaki güvenlik sorunlarının kaynağıdır. Microsoft, bu işlevlerin parametre kullanımını doğrulayan daha güvenli bir sürümünü oluşturdu. Çalışma zamanında bir sorun algılandığında geçersiz parametre işleyicisini çağırır.  Varsayılan olarak, Microsoft C++ derleyicisi, daha güvenli bir değişken kullanılabilir olan bir işlev kullanıldığında kullanımdan kaldırma uyarısı verir. Kodunuzu C++ olarak derlerken, `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` çoğu uyarıyı kaldırmak için 1 olarak tanımlayabilirsiniz. Bu makro, taşınabilir kaynak kodunu koruyarak şablon aşırı yüklemelerinin daha güvenli türevlerini çağırmasını sağlar. Uyarıyı bastırmak için, `_CRT_SECURE_NO_WARNINGS` Bu işlevleri kullanan kodda herhangi bir üst bilgi dahil etmeden önce tanımlayın. Daha fazla bilgi için bkz. [CRT Içindeki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md).

Belirli işlevler için belgeler içinde belirtilmedikçe, UıCRT Windows API 'siyle uyumludur.  Bazı işlevler Windows Mağazası veya Evrensel Windows Platformu ([UWP](/uwp)) uygulamalarında desteklenmez. Bu işlevler, [Evrensel Windows platformu uygulamalarda desteklenmeyen crt işlevlerinde](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)listelenmiştir.

## <a name="related-articles"></a>İlgili Makaleler

|Başlık|Açıklama|
|-----------|-----------------|
|[UWP uygulamaları, Windows Çalışma Zamanı ve C çalışma zamanı](../c-runtime-library/windows-store-apps-the-windows-runtime-and-the-c-run-time.md)|UıCRT yordamlarının Evrensel Windows uygulamaları veya Microsoft Store uygulamalarıyla uyumlu olmadığı açıklanır.|
|[ANSI C uyumluluğu](../c-runtime-library/ansi-c-compliance.md)|UCRT 'da standart uyumlu adlandırmayı açıklar.|
|[UNIX](../c-runtime-library/unix.md)|Programların UNIX 'e taşıma yönergelerini sağlar.|
|[Windows platformları (CRT)](../c-runtime-library/windows-platforms-crt.md)|CRT 'nin desteklediği işletim sistemlerini listeler.|
|[Geriye dönük uyumluluk](../c-runtime-library/backward-compatibility.md)|Eski CRT adlarını yeni olanlarla nasıl eşleneceğini açıklar.|
|[CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md)|CRT kitaplığı (. lib) dosyalarına ve ilişkili derleyici seçeneklerine genel bir bakış sağlar.|
