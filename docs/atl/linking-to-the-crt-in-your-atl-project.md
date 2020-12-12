---
description: "Daha fazla bilgi edinin: ATL projenizde CRT 'ye bağlama"
title: ATL Projenizde CRT’ye Bağlanma
ms.date: 11/04/2016
helpviewer_keywords:
- CRT, linking with ATL
- WinMainCRTStartup method
- DllMainCRTStartup method
- wWinMainCRTStartup method
- ATL, C Run-Time library (CRT)
ms.assetid: 650957ae-362c-4ecf-8b03-5d49138e8b5b
ms.openlocfilehash: e54301332d9a83546e41ab42169f06d305bbc6a2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147634"
---
# <a name="linking-to-the-crt-in-your-atl-project"></a>ATL Projenizde CRT’ye Bağlanma

[C Run-Time kitaplıkları](../c-runtime-library/crt-library-features.md) (CRT), ATL geliştirme sırasında programlamayı çok daha kolay hale getirmek için birçok yararlı işlev sağlar. Tüm ATL projeleri CRT kitaplığına bağlanır. Bağlama yönteminin olumlu ve olumsuz yönlerini, [CRT Ile bağlantı Için kullanılan yöntemin avantajları ve](../atl/benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt.md)avantajları hakkında görebilirsiniz.

## <a name="effects-of-linking-to-the-crt-on-your-program-image"></a>Program Görüntinizdeki CRT 'ya bağlanmanın etkileri

CRT 'ye statik olarak bağlantı oluşturduysanız, CRT 'daki kod, yürütülebilir yansımanıza yerleştirilir ve görüntünüzü çalıştırmak için bir sistemde CRT DLL 'nin mevcut olması gerekmez. CRT 'ye dinamik olarak bağlantı verirseniz, CRT DLL 'deki koda yapılan başvurular resme yerleştirilir, ancak kodun kendisi değildir. Görüntünüzün belirli bir sistemde çalışması için, bu sistemde CRT DLL olması gerekir. CRT 'a dinamik olarak bağlandığınızda, bazı kodların statik olarak bağlantılı olabileceğini (örneğin, `DllMainCRTStartup` ) görebilirsiniz.

Görüntünüzü bağladığınızda, görüntüyü yükledikten sonra işletim sisteminin çağıradığı bir giriş noktasını açıkça veya örtük olarak belirtirsiniz. Bir DLL için varsayılan giriş noktası olur `DllMainCRTStartup` . Bir EXE için, `WinMainCRTStartup` . Varsayılan ayarı/ENTRY bağlayıcı seçeneği ile geçersiz kılabilirsiniz. CRT,, ve için bir uygulama sağlar `DllMainCRTStartup` `WinMainCRTStartup` `wWinMainCRTStartup` (bir exe için Unicode giriş noktası). Bu CRT tarafından sağlanmış giriş noktaları, genel nesnelerde oluşturucular çağırır ve bazı CRT işlevleri tarafından kullanılan diğer veri yapılarını başlatır. Bu başlangıç kodu, statik olarak bağlanmışsa, yansımanıza yaklaşık 25K ekler. Dinamik olarak bağlanmışsa, kodun büyük bir çoğunluğu DLL 'de olduğundan, görüntü boyutunuz küçük kalır.

Daha fazla bilgi için bkz. [/Entry (giriş noktası simgesi)](../build/reference/entry-entry-point-symbol.md)bağlayıcı konusu.

## <a name="optimization-options"></a>İyileştirme seçenekleri

/OPT: NOWıN98 bağlayıcı seçeneğini kullanmak, Windows 98 sistemlerinde daha fazla yükleme süresi masrafına göre varsayılan ATL denetimini 10.000 azaltır. Bağlama seçenekleri hakkında daha fazla bilgi için bkz. [/opt (iyileştirmeler)](../build/reference/opt-optimizations.md).

## <a name="see-also"></a>Ayrıca bkz.

[ATL ve C Run-Time kodla programlama](../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[DLL’ler ve Visual C++ çalışma zamanı kitaplığı davranışı](../build/run-time-library-behavior.md)
