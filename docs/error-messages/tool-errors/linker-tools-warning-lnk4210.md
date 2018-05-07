---
title: Bağlayıcı araçları uyarısı LNK4210 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4210
dev_langs:
- C++
helpviewer_keywords:
- LNK4210
ms.assetid: db48cff8-a2be-4a77-8d03-552b42c228fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2bd34866264fdfea71ba7496ad9c94446fd5726
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4210"></a>Bağlayıcı Araçları Uyarısı LNK4210  
  
> bölüm *bölüm* olduğunu; statik başlatıcıları veya sonlandırıcılar var. işlenmemiş  
  
Biraz kod statik başlatıcıları veya sonlandırıcılar anlatılmıştır, ancak uygulama başladığında VCRuntime kitaplığı başlatma kodunu veya (, statik başlatıcıları veya sonlandırıcılar çalıştırmak için gereken) eşdeğer çalıştırmak değil. Statik başlatıcıları veya sonlandırıcılar gerektiren kod bazı örnekleri şunlardır:  
  
-   Genel sınıf değişkeni oluşturucusu, yıkıcı veya sanal işlev tablosu.  
  
-   Genel değişkeni bir derleme zamanı sabit ile başlatılamadı.  
  
Bu sorunu gidermek için şunlardan birini deneyin:  
  
-   Tüm kodu ile statik başlatıcıları kaldırın.  
  
-   Kullanmayın [/NOENTRY](../../build/reference/noentry-no-entry-point.md). /NOENTRY kaldırdıktan sonra aynı zamanda kaldırmak zorunda kalabilirsiniz [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) bağlayıcı komut satırından.  
  
-   Yapınızın/MT kullanıyorsa, libcmt.lib, libvcruntime.lib ve libucrt.lib, bağlayıcı komut satırı ekleyin. Yapınızın /MTd kullanıyorsa, libcmtd.lib, vcruntimed.lib ve libucrtd.lib ekleyin.  
  
-   / CLR taşırken: / CLR, saf derlemeye kaldırmak [/Entry](../../build/reference/entry-entry-point-symbol.md) bağlayıcı satırından seçeneği. Bu, CRT başlatma sağlar ve uygulama başlangıcında yürütülecek statik başlatıcıları sağlar.  
  
 [/GS](../../build/reference/gs-buffer-security-check.md) derleyici seçeneği gerektirir başlatma tarafından `__security_init_cookie` işlevi. Varsayılan olarak çalıştığı VCRuntime kitaplığı başlangıç kodu bu başlatma sağlanan `_DllMainCRTStartup`.  
  
-   / Entry kullanarak projenize oluşturulduysa ve Entry işlevi dışındaki geçirilirse `_DllMainCRTStartup`, işlevini çağırmanız gerekir `_CRT_INIT` CRT başlatılamadı. DLL /GS kullanıyorsa, statik başlatıcıları gerektirir veya MFC ya da ATL kodu bağlamında adlı bu çağrı başına yeterli değildir. Bkz: [DLL'ler ve Visual C++ çalışma zamanı kitaplığı davranışı](../../build/run-time-library-behavior.md) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)