---
title: "Programları Windows XP için yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 23e417d9ef316bf72c9606ce2525ff79587e7047
ms.sourcegitcommit: ecf0177ae9d36b1f63c9673a9583e0359107a5cb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/19/2018
---
# <a name="configuring-programs-for-windows-xp"></a>Programları Windows XP için yapılandırma

Visual Studio birden çok platform toolsets desteklediğinden, işletim sistemleri ve varsayılan araç takımı tarafından desteklenmez çalışma zamanı kitaplıkları hedefleyebilirsiniz. Örneğin, platform araç takımı geçerek, C ++ 11, C ++ 14 ve C ++ 17 dil geliştirmeleri Visual Studio için Visual C++ derleyicisi tarafından desteklenen hedefleyen uygulamalar oluşturmak için kullanabileceğiniz [!INCLUDE[winxp](../build/includes/winxp_md.md)] ve [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Ayrıca ikili uyumlu eski kod korumak için eski platform toolsets kullanabilir ve hala en son Visual Studio IDE özelliklerini yararlanın.

## <a name="install-the-windows-xp-platform-toolset"></a>Windows XP platform araç takımı yükleyin
Hedef bileşenleri ve platform araç takımı almak için [!INCLUDE[winxp](../build/includes/winxp_md.md)] ve [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] Visual Studio 2017 ' Visual Studio yükleyiciyi çalıştırın. Visual Studio başlangıçta yüklediğinizde veya seçtiğinizde **Değiştir** varolan bir yüklemeyi değiştirmek için olduğundan emin olun **C++ ile masaüstü geliştirme** iş yükü seçilidir. Bu iş yükü için isteğe bağlı bileşenler listesinden seçip **C++ Windows XP desteği**ve ardından **yükleme** veya **Değiştir**.

## <a name="windows-xp-targeting-experience"></a>Windows XP deneyimi hedefleme

Visual Studio'da bulunan Windows XP platform araç takımı sürümüdür [!INCLUDE[win7](../build/includes/win7_md.md)] SDK, ancak geçerli C++ derleyicisi kullanır. Ayrıca, proje özellikleri uygun varsayılan değerleri, örneğin, alt düzey hedefleme için uyumlu bir bağlayıcı belirtimi için yapılandırır. Yalnızca Windows XP platform araç takımı kullanılarak oluşturulan Masaüstü uygulamaları çalıştıracağınız Windows [!INCLUDE[winxp](../build/includes/winxp_md.md)] ve [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], ancak bu uygulamaları daha yeni Windows işletim sistemlerinde de çalıştırabilirsiniz.

#### <a name="to-target-windows-xp"></a>Hedef Windows XP

1. İçinde **Çözüm Gezgini**projeniz için kısayol menüsünü açın ve ardından **özellikleri**.

1. İçinde **özellik sayfaları** iletişim kutusunda proje için altında **yapılandırma özellikleri** > **genel**ayarlayın **Platform araç takımı** istenen Windows XP araç takımı özelliğine. Örneğin, tercih **Visual Studio 2017 - Windows XP (v141_xp)** için kod oluşturmak için [!INCLUDE[winxp](../build/includes/winxp_md.md)] ve [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] Microsoft Visual C++ 2017 derleyici kullanarak.

### <a name="c-runtime-support"></a>C++ çalışma zamanı desteği

Windows XP platform araç takımı, C çalışma zamanı kitaplığı (CRT), C++ Standart Kitaplığı, Etkin Şablon kitaplığı (ATL), eşzamanlılık çalışma zamanı kitaplığı (ConCRT), paralel Desen kitaplığı (PPL), Microsoft Foundation Class Kitaplığı (MFC) ve C++ AMP (C++ ile birlikte Yoğun programlama Hızlandırılmış) kitaplığı için çalışma zamanı desteği dahil [!INCLUDE[winxp](../build/includes/winxp_md.md)] ve [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Bu işletim sistemleri için en düşük desteklenen sürümler: [!INCLUDE[winxp](../build/includes/winxp_md.md)] x86, Service Pack 3 (SP3) [!INCLUDE[winxp](../build/includes/winxp_md.md)] x64, Service Pack 2 (SP2) ve [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] x86 hem x64 için Service Pack 2 (SP2).

Bu kitaplıklar, Visual Studio tarafından bağlı olarak hedef yüklü platform toolsets tarafından desteklenir:

|Kitaplığı|Varsayılan platform araç takımı hedefleme Windows Masaüstü uygulamaları|Platform araç takımı hedefleme mağazası uygulamaları varsayılan|Windows XP platform araç takımı hedefleme [!INCLUDE[winxp](../build/includes/winxp_md.md)], [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]|
|---|---|---|---|
|CRT|X|X|X|
|C++ Standart Kitaplığı|X|X|X|
|ATL|X|X|X|
|ConCRT/PPL|X|X|X|
|MFC|X||X|
|C++ AMP|X|X||

> [!NOTE]
> C + yazılmış uygulamalar +/ CLI ve hedef .NET Framework 4 çalıştıracağınız [!INCLUDE[winxp](../build/includes/winxp_md.md)] ve [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)].

### <a name="differences-between-the-toolsets"></a>Toolsets arasındaki farklar

Platform ve kitaplık desteği farklılıkları nedeniyle, bir Windows XP platform araç takımı kullanan uygulamalar için geliştirme deneyimi için olduğu gibi varsayılan Visual Studio platform araç takımı kullanan uygulamalar olarak tam değil.

- **C++ dil özellikleri**

   Visual Studio 2012'de uygulanan C++ dil özellikleri v110 kullanan uygulamalar desteklenen\_xp platform araç takımı. Visual Studio 2013'te uygulanan C++ dil özellikleri v120 kullanan uygulamalar desteklenen\_xp platform araç takımı. Visual Studio 2015'te uygulanan C++ dil özellikleri v140 kullanan uygulamalar desteklenen\_xp platform araç takımı. Eski platform toolsets kullanarak oluşturduğunda visual Studio karşılık gelen derleyici kullanır. En son Windows XP platform araç takımı derleyici bu sürümünde ek C++ dili özelliklerden yararlanmak için kullanın.

- **Uzaktan hata ayıklama**

   Uzak araçlar Visual Studio uzaktan hata ayıklama desteklemiyor [!INCLUDE[winxp](../build/includes/winxp_md.md)] veya [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Çalıştığı sırada bir uygulama hata ayıklamak için [!INCLUDE[winxp](../build/includes/winxp_md.md)] veya [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], yerel olarak veya uzaktan hata ayıklama için Visual Studio'nun önceki bir sürümden bir hata ayıklayıcısı kullanabilirsiniz. Bir uygulama çalışma zamanı hedef platform araç takımı, ancak uzak bir hata ayıklama hedefi değil Windows Vista hata ayıklama deneyimini benzer.

- **Statik çözümleme**

   Windows XP platform toolsets statik çözümleme için desteği için SAL ek açıklamaları [!INCLUDE[win7](../build/includes/win7_md.md)] SDK ve çalışma zamanı kitaplıkları uyumsuzdur. Destekleyen bir uygulama üzerinde statik analizi yapmak istediğinizde [!INCLUDE[winxp](../build/includes/winxp_md.md)] veya [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], geçici olarak analiz gerçekleştirmek için varsayılan platform araç takımı hedeflemek için çözüm geçin ve oluşturmak için geri Windows XP platform araç takımı için geçiş uygulama.

- **DirectX grafikleri hata ayıklama**

     Grafik hata ayıklayıcı Direct3D 9 API desteklemediğinden, bu üzerinde Direct3D kullanan uygulamalarda hata ayıklamak için kullanılamaz [!INCLUDE[winxp](../build/includes/winxp_md.md)] veya [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Ancak, uygulama Direct3D 10 veya Direct3D 11 API'lerini kullanan alternatif bir oluşturucu uygularsa, grafik hata ayıklayıcı bu API'leri kullanarak sorunları tanılamak için kullanılabilir.

- **Yapı HLSL**

   Varsayılan olarak, Windows XP araç takımı HLSL kaynak kodu dosyaları derlenmiyor. HLSL dosyalarını derlemek indirin ve Haziran 2010'u yüklemek için DirectX SDK ayarlayın ve ardından Proje kullanıcının VC, dahil etmek için dizinler. Daha fazla bilgi için bkz: "kaydettirilemedi DirectX SDK Ekle/kitaplık yolları Visual Studio 2010 ile" bölümünü [Haziran 2010 DirectX SDK indirme sayfası](http://www.microsoft.com/download/details.aspx?displaylang=en&id=6812).
