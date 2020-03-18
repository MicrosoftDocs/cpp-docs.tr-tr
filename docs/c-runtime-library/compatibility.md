---
title: Uyumluluk
description: Standart C Kitaplığı, POSIX, güvenli CRT ve Mağaza uygulamaları ile Microsoft Universal C çalışma zamanı kitaplığı 'nın (UCRT) uyumluluğunu açıklar.
ms.date: 12/06/2019
helpviewer_keywords:
- CRT, compatibility
- compatibility, C run-time libraries
- compatibility
ms.assetid: 346709cb-edda-4909-9a19-3d253eddb6b7
ms.openlocfilehash: fba85462218d0cc2ba1d52caa4e59b2cfb9f4fd6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443491"
---
# <a name="compatibility"></a>Uyumluluk

Evrensel C çalışma zamanı kitaplığı (UCRT), uygunluk için C++ gereken C standart kitaplığının çoğunu destekler. C99 (ISO/ıEC 9899:1999) kitaplığı belirli özel durumlarla birlikte uygular: \<tgmath. h > ' de tanımlanan tür-genel makrolar ve \<karmaşık. h > katı tür uyumluluğu. UıCRT, POSIX 'nin büyük bir alt kümesini de uygular. 1 (ISO/ıEC 9945-1:1996, POSIX sistem uygulaması program arabirimi) C Kitaplığı. Ancak, belirli bir POSIX standardına tam olarak uyumlu değildir. UıCRT Ayrıca, standart bir parçası olmayan, Microsoft 'a özgü birkaç işlevi ve makroları uygular.

Visual C++ 'in Microsoft uygulamasına özgü işlevler vcruntime kitaplığı 'nda bulunur.  Bu işlevlerin birçoğu iç kullanım içindir ve Kullanıcı kodu tarafından çağrılamaz. Bazıları hata ayıklama ve uygulama uyumluluğuyla kullanılmak üzere belgelenmiştir.

Standart C++ , uygulamaya genel ad alanındaki alt çizgiyle başlayan adları ayırır. Hem POSIX işlevleri hem de Microsoft 'a özgü çalışma zamanı kitaplığı işlevleri genel ad alanında bulunur, ancak standart C çalışma zamanı kitaplığının bir parçası değildir. Bu işlevlerin tercih edilen Microsoft uygulamalarının önde bir alt çizgi olmasının nedeni budur. Taşınabilirliği için UCRT Ayrıca varsayılan adları destekler, ancak Microsoft C++ derleyicisi bunları kullanan kod derlendiğinde kullanımdan kaldırma uyarısı verir. İşlevlerin kendisi değil, yalnızca varsayılan adlar kullanımdan kaldırılmıştır. Uyarıyı gizlemek için, özgün POSIX adlarını kullanan koddaki tüm üst bilgileri eklemeden önce `_CRT_NONSTDC_NO_WARNINGS` tanımlayın.

Standart C kitaplığındaki bazı işlevlerin güvenli olmayan kullanım geçmişi, yanlış kullanılan parametreler ve Denetlenmemiş Arabellekler nedeniyle Bu işlevler genellikle koddaki güvenlik sorunlarının kaynağıdır. Microsoft, bu işlevlerin parametre kullanımını doğrulayan daha güvenli bir sürümünü oluşturdu. Çalışma zamanında bir sorun algılandığında geçersiz parametre işleyicisini çağırır.  Varsayılan olarak, Microsoft C++ derleyicisi daha güvenli bir değişken kullanılabilir olan bir işlev kullanıldığında kullanımdan kaldırma uyarısı verir. Kodunuzu olarak C++derlerken, çoğu uyarıyı kaldırmak için `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` olarak tanımlayabilirsiniz. Bu makro, taşınabilir kaynak kodunu koruyarak şablon aşırı yüklemelerinin daha güvenli türevlerini çağırmasını sağlar. Uyarıyı bastırmak için, bu işlevleri kullanan koddaki tüm üst bilgileri eklemeden önce `_CRT_SECURE_NO_WARNINGS` tanımlayın. Daha fazla bilgi için bkz. [CRT Içindeki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md).

Belirli işlevler için belgeler içinde belirtilmedikçe, UıCRT Windows API 'siyle uyumludur.  Bazı işlevler Windows Mağazası veya Evrensel Windows Platformu ([UWP](/uwp)) uygulamalarında desteklenmez. Bu işlevler, [Evrensel Windows platformu uygulamalarda desteklenmeyen crt işlevlerinde](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)listelenmiştir.

## <a name="related-articles"></a>İlgili Makaleler

|Başlık|Açıklama|
|-----------|-----------------|
|[UWP Uygulamaları, Windows Çalışma Zamanı ve C Çalışma Zamanı](../c-runtime-library/windows-store-apps-the-windows-runtime-and-the-c-run-time.md)|UıCRT yordamlarının Evrensel Windows uygulamaları veya Microsoft Store uygulamalarıyla uyumlu olmadığı açıklanır.|
|[ANSI C Uyumluluğu](../c-runtime-library/ansi-c-compliance.md)|UCRT 'da standart uyumlu adlandırmayı açıklar.|
|[UNIX](../c-runtime-library/unix.md)|Programların UNIX 'e taşıma yönergelerini sağlar.|
|[Windows Platformları (CRT)](../c-runtime-library/windows-platforms-crt.md)|CRT 'nin desteklediği işletim sistemlerini listeler.|
|[Geriye Dönük Uyumluluk](../c-runtime-library/backward-compatibility.md)|Eski CRT adlarını yeni olanlarla nasıl eşleneceğini açıklar.|
|[CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)|CRT kitaplığı (. lib) dosyalarına ve ilişkili derleyici seçeneklerine genel bir bakış sağlar.|