---
title: "-favor (Mimari özellikleri için iyileştirme) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /favor
dev_langs: C++
helpviewer_keywords:
- -favor compiler option [C++]
- /favor compiler option [C++]
ms.assetid: ad264df2-e30f-4d68-8bd0-10d6bee71a2a
caps.latest.revision: "31"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 58b57183d7976d024a8a9d960f1f56ab438abff9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="favor-optimize-for-architecture-specifics"></a>/favor (Mimari Özellikleri için İyileştirme)
**/ favor:** `option` belirli bir mimari için veya AMD ve Intel mimarileri mikro mimari özellikleri için iyileştirilmiş kod oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/favor:{blend | ATOM | AMD64 | INTEL64}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/favor:Blend**  
 (x86 hem x64) AMD ve Intel mimarileri mikro mimari özellikleri için optimize edilmiştir kodu oluşturur. Sırada **/favor:blend** en iyi performans vermeyebilir, çok çeşitli x86 hem x64 işlemciler arasında en iyi performansı sağlamak üzere tasarlanmıştır olası belirli bir işlemci üzerinde. Varsayılan olarak, **/favor:blend** etkili olur.  
  
 **/favor:Atom**  
 (x86 hem x64) Intel Atom işlemci ve Intel Centrino Atom işlemci teknolojisi ayrıntılarını için en iyi duruma getirilmiş kodu oluşturur. Kullanılarak oluşturulan kod **/favor:ATOM** Intel SSSE3, SSE3, SSE2 ve SSE yönergeler Intel işlemcileri için de üretebilir.  
  
 **/favor:AMD64**  
 (yalnızca x64) AMD Opteron ve 64-bit uzantıları desteği Athlon işlemcileri için oluşturulan kodu en iyi duruma getirir. İyileştirilmiş kod uyumlu platformlar üzerinde tüm x64 çalıştırabilirsiniz. Kullanılarak oluşturulan kod **/favor:AMD64** kötü performans Intel64 destekleyen Intel işlemcileri neden olabilir.  
  
 **/favor:INTEL64**  
 (yalnızca x64) genellikle, platform için daha iyi bir performans verir Intel64 destekleyen Intel işlemcileri için oluşturulan kodu en iyi duruma getirir. Sonuçta elde edilen kod üzerinde hiçbir x64 çalıştırabilir platform. İle oluşturulan kodu **/favor:INTEL64** kötü performans AMD Opteron ve 64-bit uzantıları desteği Athlon işlemciler üzerinde neden olabilir.  
  
> [!NOTE]
>  Intel64 mimarisi daha önce genişletilmiş bellek 64 teknoloji olarak biliniyordu ve karşılık gelen derleyici seçeneği **/favor:EM64T**.  
  
 Program hakkında bilgi için [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] mimarisi, bkz: [x64 yazılım kuralları](../../build/x64-software-conventions.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **C/C++** klasör.  
  
3.  Seçin **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği girin **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)