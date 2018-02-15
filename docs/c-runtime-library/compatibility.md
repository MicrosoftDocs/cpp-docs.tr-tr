---
title: Uyumluluk | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- CRT, compatibility
- compatibility, C run-time libraries
- compatibility
ms.assetid: 346709cb-edda-4909-9a19-3d253eddb6b7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bed3ebc3723bfe6af8e3d12fc3702ecb0dda7b4f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="compatibility"></a>Uyumluluk
Evrensel C çalışma zamanı kitaplığı (UCRT) C++ uyum için gereken C Standart Kitaplığı çoğunu destekler. C99 (ISO/IEC 9899:1999) kitaplıkla tanımlanan türü genel makroları özel durumları uygulayan \<tgmath.h > ve katı türü uyumluluğu \<complex.h >. UCRT de büyük bir alt kümesini POSIX.1 uygular (ISO/IEC 9945-1:1996, POSIX sistem uygulama programı arabirimi) C Kitaplığı, ancak değil tam olarak belirli bir POSIX standart uyumluluğunu.  Ayrıca, çeşitli Microsoft özgü işlevler ve standart bir parçası olmayan makroları UCRT uygular.  
  
 Visual C++ Microsoft uyarlamasını belirli işlevler vcruntime Kitaplığı'nda bulunur.  Bu işlevlerin birçoğunu dahili kullanım içindir ve kullanıcı kodu tarafından çağrılamaz. Bazı kullanım için hata ayıklama ve uygulama uyumluluğu belgelenmiştir.  
  
 Standart C++ uygulamasına genel ad alanında bir alt çizgi ile başlayan adları ayırır. POSIX işlevleri genel ad alanında, ancak standart C çalışma zamanı kitaplığı parçası olduğundan, bu işlevlerin Microsoft'a özgü uygulamaları önde gelen bir alt çizgi ' var. Taşınabilirlik, UCRT varsayılan adlarını da destekler, ancak bunları kullanan kodu derlendiğinde Visual C++ derleyicisi bir kullanımdan kaldırma uyarısı verir. Yalnızca varsayılan POSIX adlarını kullanım dışı bırakılmıştır, işlevleri. Uyarıyı gizlemek için tanımlamak `_CRT_NONSTDC_NO_WARNINGS` özgün POSIX adlarını kullanan kodu tüm üstbilgileri eklemeden önce.  
  
 Standart C Kitaplığı'nda belirli işlevleri güvenli olmayan kullanım geçmişini yanlış kullanılmış parametreleri ve denetlenmeyen arabellekler nedeniyle vardır. Bu işlevler genellikle kodda güvenlik sorunları kaynağıdır. Microsoft, bir dizi parametre kullanımı doğrulayın ve çalışma zamanında bir sorun algılandığında geçersiz parametre işleyicisi çağırma bu işlevlerin daha güvenli sürümleri oluşturmuştur.  Varsayılan olarak, bir işlev kullanılabilir daha güvenli bir değişken sahip kullanıldığında bir kullanımdan kaldırma uyarısı Visual C++ derleyicisi verir. C++ olarak kodunuzu derlerken tanımlayabilirsiniz `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` çoğu uyarılarını kaldırmak için 1 olarak. Bu şablon aşırı yüklemeleri taşınabilir kaynak kodu koruyarak daha güvenli çeşitleri çağırmak için kullanır. Uyarıyı gizlemek için tanımlamak `_CRT_SECURE_NO_WARNINGS` bu işlevlerini kullanan kodu tüm üstbilgileri eklemeden önce. Daha fazla bilgi için bkz: [CRT'deki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md).  
  
 Belirli işlevleri için belgelere içinde belirtildiği gibi UCRT Windows API ile uyumlu olması dışında.  Belirli İşlevler, Windows 8 Mağazası uygulamaları veya Windows 10 Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Bu işlevler listelenen [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md), Windows çalışma zamanı tarafından desteklenmeyen işlevler numaralandırır ve [UWP](/uwp).  
  
## <a name="related-articles"></a>İlgili Makaleler  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[UWP Uygulamaları, Windows Çalışma Zamanı ve C Çalışma Zamanı](../c-runtime-library/windows-store-apps-the-windows-runtime-and-the-c-run-time.md)|Ne zaman UCRT yordamları Evrensel Windows uygulamaları veya Microsoft Store uygulamaları ile uyumlu olmayan açıklar.|  
|[ANSI C Uyumluluğu](../c-runtime-library/ansi-c-compliance.md)|Standart uyumlu UCRT adlandırma açıklar.|  
|[UNIX](../c-runtime-library/unix.md)|UNIX programlar taşıma için kılavuz bilgiler verilmektedir.|  
|[Windows Platformları (CRT)](../c-runtime-library/windows-platforms-crt.md)|CRT desteklediği işletim sistemleri listelenmektedir.|  
|[Geriye Dönük Uyumluluk](../c-runtime-library/backward-compatibility.md)|Yenilerini eski CRT adlarını eşleştirmek açıklar.|  
|[CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)|CRT kitaplık (.lib) dosyaları ve ilişkili derleyici seçenekleri genel bir bakış sağlar.|