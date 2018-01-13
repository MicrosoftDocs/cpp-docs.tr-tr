---
title: "ATL projenizdeki CRT bağlanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DllMainCRTStartup
- wWinMainCRTStartup
- WinMainCRTStartup
dev_langs: C++
helpviewer_keywords:
- CRT, linking with ATL
- WinMainCRTStartup method
- DllMainCRTStartup method
- wWinMainCRTStartup method
- ATL, C Run-Time library (CRT)
ms.assetid: 650957ae-362c-4ecf-8b03-5d49138e8b5b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 631426fece3960303d67d8929e99c404beaab998
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linking-to-the-crt-in-your-atl-project"></a>ATL projenizdeki CRT bağlantılandırma
[C çalışma zamanı kitaplıkları](../c-runtime-library/crt-library-features.md) (CRT) programlama çok ATL geliştirme sırasında kolaylaştırabilir pek çok yararlı işlevleri sağlar. CRT kitaplık tüm ATL projeleri bağlantısı. Olumlu ve olumsuz yönlerini yönteminde bağlama görebilirsiniz [avantajları ve bileşim CRT bağlamak için kullanılan yöntem](../atl/benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt.md).  
  
## <a name="effects-of-linking-to-the-crt-on-your-program-image"></a>CRT Program görüntüye bağlantılandırma etkileri  
 CRT statik olarak bağlarsanız, CRT koddan yürütülebilir yansımanıza yerleştirilir ve görüntünüzü çalıştırmak için bir sistemde mevcut CRT DLL olması gerekmez. CRT dinamik olarak bağlantı varsa, CRT DLL kodda başvurular görüntünüzü, ancak kod kendisini yerleştirilir. Belirli bir sistemde çalıştırmak, görüntü için sırayla CRT DLL bu sistemde mevcut olmalıdır. Hatta dinamik olarak CRT bağladığınızda, biraz kod statik olarak bağlı olduğunu bulabilirsiniz (örneğin, **DllMainCRTStartup**).  
  
 Açıkça veya örtük görüntünüzü bağladığınızda, işletim sistemi görüntü yüklendikten sonra çağırmak bir giriş noktası belirtin. Bir DLL için varsayılan giriş noktası olduğunu **DllMainCRTStartup**. Bir EXE için olmasından **WinMainCRTStartup**. / Entry bağlayıcı seçeneği ile Varsayılanı geçersiz kılabilirsiniz. Bir uygulama için CRT sağlar **DllMainCRTStartup**, **WinMainCRTStartup**, ve **wWinMainCRTStartup** (Unicode giriş noktası için bir EXE). Bu sağlanan CRT giriş noktaları oluşturucular genel nesnelerde çağırın ve bazı CRT işlevleri tarafından kullanılan diğer veri yapılarını başlatılamıyor. Statik olarak bağlıysa bu başlangıç kod yansımanıza yaklaşık 25 K ekler. Dinamik olarak bağlı kodu çoğunu varsa, DLL, görüntü boyutunuz küçük kalması.  
  
 Daha fazla bilgi için bağlayıcı konusuna [/Entry (giriş noktası simgesi)](../build/reference/entry-entry-point-symbol.md).  
  
## <a name="optimization-options"></a>En iyi duruma getirme seçenekleri  
 /OPT:NOWIN98 bağlayıcı seçeneğini kullanarak daha fazla 10 K bir varsayılan ATL Denetim sırasında expense, Windows 98 sistemlerine yüklenmesini artan azaltabilir. Bağlantı seçenekleri hakkında daha fazla bilgi için bkz: [OPT (iyileştirmeler)](../build/reference/opt-optimizations.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL ve C çalışma zamanı koduyla programlama](../atl/programming-with-atl-and-c-run-time-code.md)   
 [DLL’ler ve Visual C++ çalışma zamanı kitaplığı davranışı](../build/run-time-library-behavior.md)

