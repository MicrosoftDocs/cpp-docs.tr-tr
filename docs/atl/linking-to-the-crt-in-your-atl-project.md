---
title: ATL projenizde CRT bağlanma
ms.date: 11/04/2016
helpviewer_keywords:
- CRT, linking with ATL
- WinMainCRTStartup method
- DllMainCRTStartup method
- wWinMainCRTStartup method
- ATL, C Run-Time library (CRT)
ms.assetid: 650957ae-362c-4ecf-8b03-5d49138e8b5b
ms.openlocfilehash: e247897f42eea5b4ced5bc40b556137a1a5cd228
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820188"
---
# <a name="linking-to-the-crt-in-your-atl-project"></a>ATL projenizde CRT bağlanma

[C çalışma zamanı kitaplıkları](../c-runtime-library/crt-library-features.md) (CRT) programlama çok daha kolay ATL geliştirme sırasında yapabileceğiniz birçok kullanışlı işlevi sağlar. CRT kitaplığının tüm ATL projeleri bağlantısı. Olumlu ve olumsuz yöntemine bağlama gördüğünüz [avantajlı ve Avantajsız yönleri CRT bağlantı için kullanılan yöntem](../atl/benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt.md).

## <a name="effects-of-linking-to-the-crt-on-your-program-image"></a>CRT Program resminize bağlanma etkileri

CRT'ye statik olarak bağlarsanız, yürütülebilir bir görüntüde CRT koddan yerleştirilir ve görüntünüzü çalıştırılacak bir sistemde CRT DLL mevcut olması gerekmez. CRT'ye dinamik olarak bağlarsanız, kod CRT DLL başvurularını görüntünüzü, ancak kodunun kendisi yerleştirilir. Belirli bir sistemde çalıştırmak resmi sırayla CRT DLL bu sistemde mevcut olması gerekir. Hatta dinamik olarak CRT'ye bağladığınızda, bazı kodlar statik olarak bağlı olduğunu bulabilirsiniz (örneğin, `DllMainCRTStartup`).

Açıkça veya örtülü olarak görüntünüzü bağladığınızda, işletim sistemi görüntüsü yüklendikten sonra çağırmak bir giriş noktası belirtin. Bir DLL için varsayılan giriş noktasıdır `DllMainCRTStartup`. Bir EXE olduğu `WinMainCRTStartup`. / Entry bağlayıcı seçeneği ile Varsayılanı geçersiz kılabilirsiniz. CRT bir uygulamasını sağlar `DllMainCRTStartup`, `WinMainCRTStartup`, ve `wWinMainCRTStartup` (Unicode giriş noktası için bir EXE). Bu CRT tarafından sağlanan giriş noktaları, Oluşturucular, genel nesneler üzerinde çağırmak ve bazı CRT işlevleri tarafından kullanılan diğer veri yapılarını başlatamıyor. Statik olarak bağlı olduğunda bu başlatma kodunu yaklaşık 25 K görüntüye ekler. Dinamik olarak bağlı kod çoğunu varsa, DLL içinde görüntü boyutunuz küçük kalması.

Daha fazla bilgi için bağlayıcı konusuna [/Entry (giriş noktası simgesi)](../build/reference/entry-entry-point-symbol.md).

## <a name="optimization-options"></a>En iyi duruma getirme seçenekleri

Nowın98 bağlayıcı seçeneğini kullanarak daha fazla varsayılan ATL denetimi tarafından 10 bin adresindeki expense, yüklenme zamanı Windows 98 sistemlerinde artırılmış azaltabilir. Bağlantı seçenekleri ile ilgili daha fazla bilgi için bkz: [OPT (iyileştirmeler)](../build/reference/opt-optimizations.md).

## <a name="see-also"></a>Ayrıca bkz.

[ATL ve C Çalışma Zamanı Koduyla Programlama](../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[DLL’ler ve Visual C++ çalışma zamanı kitaplığı davranışı](../build/run-time-library-behavior.md)
