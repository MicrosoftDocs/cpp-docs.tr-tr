---
title: "-Gs (Denetim yığını denetim çağrıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /GS
dev_langs: C++
helpviewer_keywords:
- disabling stack probes
- GS compiler option [C++]
- /GS compiler option [C++]
- stack, stack probes
- stack probes
- -GS compiler option [C++]
- stack checking calls
ms.assetid: 40daed7c-f942-4085-b872-01e12b37729e
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ff02465b4e1b1a727a2367c8d5e038f30854ecc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="gs-control-stack-checking-calls"></a>/Gs (Denetim Yığını Denetim Çağrıları)
Denetimleri yığın yoklamaları.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Gs[size]  
```  
  
## <a name="arguments"></a>Arguments  
 `size`  
 (İsteğe bağlı) Yerel değişkenler bir yığın araştırma önce kaplar bayt sayısı başlatılır. Varsa **/Gs** seçeneği olmadan belirtildiğinde bir `size` bağımsız değişkeni, belirtme ile aynı olan **/Gs0**,  
  
## <a name="remarks"></a>Açıklamalar  
 Bir yığın araştırma derleyici her işlev çağrısı ekleyen kodu dizisidir. Başlatıldığında bir yığın araştırma benignly işlevin yerel değişkenler depolamak için gereken alanı miktarına göre belleğe ulaşır.  
  
 Bir işlev gerektiriyorsa birden fazla `size` bayt yığınının alan yerel değişkenler için kendi yığını araştırma başlatılır. Varsayılan olarak, derleyici işlevi birden fazla sayfa yığın alanı gerektirdiğinde yığını araştırma başlatan kodu oluşturur. Bu derleyici seçeneğine eşdeğerdir **/Gs4096** x86 için [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]ve ARM platformlar. Bu değer bir uygulama ve Windows Bellek Yöneticisi program yığına çalışma zamanında dinamik olarak kaydedilen bellek miktarını artırmak sağlar.  
  
> [!NOTE]
>  Varsayılan değer olan **/Gs4096** çalışma zamanında doğru büyümeye Windows uygulamaları program yığınını sağlar. Tam olarak neden değiştirmek kullandığınız bilmiyorsanız varsayılan değer değiştirmemenizi öneririz.  
  
 Bazı programlar — Örneğin, sanal cihaz sürücüleri — bu varsayılan yığın büyümenin mekanizması gerektirmez. Böyle durumlarda, yığın yoklamalarını gerekli değildir ve ayarlayarak oluşturma gelen derleyici durdurabilirsiniz `size` herhangi bir işlev için yerel değişken depolama gerektirecektir boyutundan daha büyük bir değer. Arasında boşluk bulunmamalıdır **/Gs** ve `size`.  
  
 **/ Gs0** yığın yoklamalarını yerel değişkenler için depolama gerektiren her işlev çağrısı için etkinleştirir. Bu performans üzerinde olumsuz bir etkisi olabilir.  
  
 Kullanarak yığın yoklamalarını üzerinde veya devre dışı bırakabilir [check_stack](../../preprocessor/check-stack.md). **/GS** ve `check_stack` pragma standart C Kitaplık yordamları üzerinde hiçbir etkisi yoktur; yalnızca, derleme işlevleri etkiler.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **C/C++** klasör.  
  
3.  Seçin **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)