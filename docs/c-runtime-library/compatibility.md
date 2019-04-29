---
title: Uyumluluk
ms.date: 11/04/2016
f1_keywords:
- c.programs
helpviewer_keywords:
- CRT, compatibility
- compatibility, C run-time libraries
- compatibility
ms.assetid: 346709cb-edda-4909-9a19-3d253eddb6b7
ms.openlocfilehash: f562a6a214cd1fb3feba2caf26831797d4b182fb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62344687"
---
# <a name="compatibility"></a>Uyumluluk

Evrensel C Çalışma Zamanı Kitaplığı'nı (UCRT) C++ uyumluluk için gereken standart C Kitaplığı çoğunu destekler. C99 (ISO/IEC 9899:1999) kitaplığı içinde tanımlanan tür genel makro istisnalarla uygulayan \<tgmath.h > ve sıkı Uyumluluk \<complex.h >. UCRT POSIX.1 büyük bir alt kümesi uygulayan (ISO/IEC 9945-1:1996, POSIX sistem uygulaması Program arabirimi) C Kitaplığı, ancak değil tam olarak uyumlu herhangi belirli POSIX standart.  Ayrıca, çeşitli Microsoft'a özgü işlevleri ve standart bir parçası olmayan makroları UCRT uygular.

Microsoft Visual C++ uygulaması için belirli işlevleri vcruntime Kitaplığı'nda bulunur.  Bu işlevlerin birçoğu, dahili kullanım içindir ve kullanıcı kodu tarafından çağrılamaz. Bazı kullanım için hata ayıklama ve uygulama uyumluluğu belgelenmiştir.

C++ standardı uygulamaya genel ad alanında altı çizili ile başlayan adları ayırır. POSIX işlevleri genel ad alanında, ancak standart C çalışma zamanı kitaplığının bir parçası değil çünkü Microsoft'a özgü bu işlevlerin bir alt çizgi vardır. Taşınabilirlik UCRT varsayılan adlar da destekler, ancak bunları kullanan kodu derlendiğinde Visual C++ Derleyici kullanımdan kaldırılma uyarısı verir. Yalnızca varsayılan POSIX adları kullanım dışı bırakılmıştır, İşlevler. Bu uyarının gösterilmemesi için tanımladığınız `_CRT_NONSTDC_NO_WARNINGS` özgün POSIX adları kullanan kodu herhangi bir üst bilgiler dahil olmak üzere önce.

Standart C Kitaplığı belirli işlevlerde güvenli kullanım geçmişini yanlış kullanılmış parametreleri ve Denetlenmemiş Arabellekler nedeniyle var. Bu işlevler genellikle kod güvenlik sorunlarını kaynağıdır. Microsoft, bir dizi parametre kullanımı doğrulayın ve çalışma zamanında bir sorun algılandığında, geçersiz parametre işleyicisini çağırır, bu işlevlerin daha güvenli sürümleri oluşturmuştur.  Varsayılan olarak, Visual C++ derleyicisi, bir güvenli değişken kullanılabilir olan bir işlev kullanıldığında bir kullanımdan kaldırma uyarı verir. C++ kodunuzu derlediğinizde, tanımlayabileceğiniz `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` çoğu uyarılarını ortadan kaldırmak için 1 olarak. Bu şablon aşırı yüklemeleri taşınabilir kaynak kodu korurken güvenli çeşitler çağırmak için kullanır. Bu uyarının gösterilmemesi için tanımladığınız `_CRT_SECURE_NO_WARNINGS` bu işlevler kullanan kodu herhangi bir üst bilgiler dahil olmak üzere önce. Daha fazla bilgi için [CRT'deki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md).

Belirli işlevler için belge içinde belirtildiği gibi UCRT Windows API ile uyumlu olması dışında.  Bazı işlevler, Windows 8 Store uygulamalarında veya Windows 10 Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Bu işlevler listelenir [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md), Windows çalışma zamanı tarafından desteklenmeyen işlevleri numaralandırır ve [UWP](/uwp).

## <a name="related-articles"></a>İlgili Makaleler

|Başlık|Açıklama|
|-----------|-----------------|
|[UWP Uygulamaları, Windows Çalışma Zamanı ve C Çalışma Zamanı](../c-runtime-library/windows-store-apps-the-windows-runtime-and-the-c-run-time.md)|Ne zaman UCRT yordamları Evrensel Windows uygulamaları veya Microsoft Store uygulamaları ile uyumlu olmayan açıklar.|
|[ANSI C Uyumluluğu](../c-runtime-library/ansi-c-compliance.md)|Standart uyumlu UCRT adlandırma açıklar.|
|[UNIX](../c-runtime-library/unix.md)|UNIX programlar taşıma için kılavuz bilgiler verilmektedir.|
|[Windows Platformları (CRT)](../c-runtime-library/windows-platforms-crt.md)|CRT destekleyen işletim sistemlerini listeler.|
|[Geriye Dönük Uyumluluk](../c-runtime-library/backward-compatibility.md)|Yeni bir tane eski CRT adlarını eşleştirmek açıklar.|
|[CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)|CRT kitaplık (.lib) dosyaları ve ilgili derleme seçeneklerini genel bir bakış sağlar.|