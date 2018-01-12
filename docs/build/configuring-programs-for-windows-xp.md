---
title: "Programları Windows XP için yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ff80109c1f3a5e03ecb85406cdaea24804f96783
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="configuring-programs-for-windows-xp"></a>Programları Windows XP için yapılandırma
Visual Studio birden çok platform toolsets desteklediğinden, işletim sistemleri ve varsayılan araç takımı tarafından desteklenmez çalışma zamanı kitaplıkları hedefleyebilirsiniz. Örneğin, platform araç takımı geçerek, C ++ 11, C ++ 14 ve C ++ 17 dil geliştirmeleri Visual Studio için Visual C++ derleyicisi tarafından desteklenen hedefleyen uygulamalar oluşturmak için kullanabileceğiniz [!INCLUDE[winxp](../build/includes/winxp_md.md)] ve [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Ayrıca ikili uyumlu eski kod korumak için eski platform toolsets kullanabilir ve hala en son Visual Studio IDE özelliklerini yararlanın.  
  
> [!NOTE]
>  Kullanıyorsanız [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)], yüklemeniz gereken [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] güncelleştirme platform araç takımı desteği eklemek için 4 [!INCLUDE[winxp](../build/includes/winxp_md.md)] ve [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Bir kopyasını karşıdan yükleyip [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] güncelleştirme 4 bkz [Microsoft Visual Studio Express 2012 için Windows Masaüstü](http://go.microsoft.com/fwlink/p/?linkid=265464) Microsoft Download Center'da. Daha sonra yüklemek [Visual Studio 2012 Update 4](http://go.microsoft.com/fwlink/p/?linkid=335900) v110_xp platform araç takımı alınamıyor. Yükleme işleminden sonra en son yazılım güncelleştirmelerini almak için Windows Update'i kullanın.  
  
## <a name="windows-xp-targeting-experience"></a>Windows XP deneyimi hedefleme  
 Visual Studio'da bulunan Windows XP platform araç takımı sürümüdür [!INCLUDE[win7](../build/includes/win7_md.md)] dahil SDK [!INCLUDE[vs_dev10_long](../build/includes/vs_dev10_long_md.md)], ancak geçerli C++ derleyicisi kullanır. Ayrıca uygun varsayılan değerlere proje özelliklerini yapılandırır — Örneğin, alt düzey hedefleme için uyumlu bir bağlayıcı belirtimi. Yalnızca Windows XP platform araç takımı kullanılarak oluşturulan Masaüstü uygulamaları çalıştıracağınız Windows [!INCLUDE[winxp](../build/includes/winxp_md.md)] ve [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], ancak bu uygulamaları daha yeni Windows işletim sistemlerinde de çalıştırabilirsiniz.  
  
#### <a name="to-target-windows-xp"></a>Hedef Windows XP  
  
1.  İçinde **Çözüm Gezgini**projeniz için kısayol menüsünü açın ve ardından **özellikleri**.  
  
2.  İçinde **özellik sayfaları** iletişim kutusunda proje için altında **yapılandırma özellikleri**, **genel**ayarlayın **Platform araç takımı** İstenen Windows XP araç takımı özelliğine. Örneğin, tercih **Visual Studio 2015 - Windows XP (v140_xp)** için kod oluşturmak için [!INCLUDE[winxp](../build/includes/winxp_md.md)] ve [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] Microsoft Visual C++ 2015 derleyici kullanarak.  
  
### <a name="c-runtime-support"></a>C++ çalışma zamanı desteği  
 Windows XP platform araç takımı, C çalışma zamanı kitaplığı (CRT), C++ Standart Kitaplığı, Etkin Şablon kitaplığı (ATL), eşzamanlılık çalışma zamanı kitaplığı (ConCRT), paralel Desen kitaplığı (PPL), Microsoft Foundation Class Kitaplığı (MFC) ve C++ AMP (C++ ile birlikte Yoğun programlama Hızlandırılmış) kitaplığı için çalışma zamanı desteği dahil [!INCLUDE[winxp](../build/includes/winxp_md.md)] ve [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Bu işletim sistemleri için en düşük desteklenen sürümler: [!INCLUDE[winxp](../build/includes/winxp_md.md)] x86, Service Pack 3 (SP3) [!INCLUDE[winxp](../build/includes/winxp_md.md)] x64, Service Pack 2 (SP2) ve [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] x86 hem x64 için Service Pack 2 (SP2).  
  
 Bu kitaplıklar, Visual Studio tarafından bağlı olarak hedef yüklü platform toolsets tarafından desteklenir:  
  
|Kitaplığı|Varsayılan platform araç takımı hedefleme Windows Masaüstü uygulamaları|Platform araç takımı hedefleme varsayılan [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] uygulamalar|Windows XP platform araç takımı hedefleme [!INCLUDE[winxp](../build/includes/winxp_md.md)],[!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]|  
|-------------|-------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|  
|CRT|X|X|X|  
|C++ Standart Kitaplığı|X|X|X|  
|ATL|X|X|X|  
|ConCRT/PPL|X|X|X|  
|MFC|X||X|  
|C++ AMP|X|X||  
  
> [!NOTE]
>  C + yazılmış uygulamalar +/ CLI ve hedef .NET Framework 4 çalıştıracağınız [!INCLUDE[winxp](../build/includes/winxp_md.md)] ve [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)].  
  
### <a name="differences-between-the-toolsets"></a>Toolsets arasındaki farklar  
 Platform ve kitaplık desteği farklılıkları nedeniyle, bir Windows XP platform araç takımı kullanan uygulamalar için geliştirme deneyimi için olduğu gibi varsayılan Visual Studio platform araç takımı kullanan uygulamalar olarak tam değil.  
  
-   **C++ dil özellikleri**  
  
     C++ dil özellikleri uygulanan [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] v110_xp platform araç takımı kullanan uygulamalar desteklenir. C++ dil özellikleri uygulanan [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] v120_xp platform araç takımı kullanan uygulamalar desteklenir. Eski platform toolsets kullanarak oluşturduğunda visual Studio karşılık gelen derleyici kullanır. En son Windows XP platform araç takımı derleyici bu sürümünde ek C++ dili özelliklerden yararlanmak için kullanın.  
  
-   **Uzaktan hata ayıklama**  
  
     Uzak araçlar Visual Studio uzaktan hata ayıklama desteklemiyor [!INCLUDE[winxp](../build/includes/winxp_md.md)] veya [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Çalıştığı sırada bir uygulama hata ayıklamak için [!INCLUDE[winxp](../build/includes/winxp_md.md)] veya [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], yerel olarak veya uzaktan hata ayıklama için Visual Studio'nun önceki bir sürümden bir hata ayıklayıcısı kullanabilirsiniz. Bir uygulama çalışma zamanı hedef platform araç takımı, ancak uzak bir hata ayıklama hedefi değil Windows Vista hata ayıklama deneyimini benzer.  
  
-   **Statik çözümleme**  
  
     Windows XP platform toolsets statik çözümleme için desteği için SAL ek açıklamaları [!INCLUDE[win7](../build/includes/win7_md.md)] SDK ve çalışma zamanı kitaplıkları uyumsuzdur. Destekleyen bir uygulama üzerinde statik analizi yapmak istediğinizde [!INCLUDE[winxp](../build/includes/winxp_md.md)] veya [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], geçici olarak analiz gerçekleştirmek için varsayılan platform araç takımı hedeflemek için çözüm geçin ve oluşturmak için geri Windows XP platform araç takımı için geçiş uygulama.  
  
-   **DirectX grafikleri hata ayıklama**  
  
     Grafik hata ayıklayıcı Direct3D 9 API desteklemediğinden, bu üzerinde Direct3D kullanan uygulamalarda hata ayıklamak için kullanılamaz [!INCLUDE[winxp](../build/includes/winxp_md.md)] veya [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Ancak, uygulama Direct3D 10 veya Direct3D 11 API'lerini kullanan alternatif bir oluşturucu uygularsa, grafik hata ayıklayıcı bu API'leri kullanarak sorunları tanılamak için kullanılabilir.  
  
-   **Yapı HLSL**  
  
     Varsayılan olarak, Windows XP araç takımı HLSL kaynak kodu dosyaları derlenmiyor. HLSL dosyalarını derlemek indirin ve Haziran 2010'u yüklemek için DirectX SDK ayarlayın ve ardından Proje kullanıcının VC, dahil etmek için dizinler. Daha fazla bilgi için bkz: "kaydettirilemedi DirectX SDK Ekle/kitaplık yolları Visual Studio 2010 ile" bölümünü [Haziran 2010 DirectX SDK indirme sayfası](http://www.microsoft.com/download/details.aspx?displaylang=en&id=6812).