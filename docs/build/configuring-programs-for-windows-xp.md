---
title: Programları Windows XP için yapılandırma
ms.date: 05/16/2019
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
ms.openlocfilehash: 55753737b4868f33487ed980eaf37a8801f59638
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450695"
---
# <a name="configuring-programs-for-windows-xp"></a>Programları Windows XP için yapılandırma

Visual Studio, birden çok platform araç takımları desteklediğinden, işletim sistemleri ve varsayılan araç takımı tarafından desteklenmez çalışma zamanı kitaplıklarını hedefleyebilir. Örneğin, platform araç takımını geçerek, C ++ 11, C ++ 14 ve C ++ 17 dil geliştirmelerini Visual Studio'da MSVC derleyicisi tarafından desteklenen Windows XP ve Windows Server 2003 hedefleyen uygulamalar oluşturmak için kullanabilirsiniz. Ayrıca ikili ile uyumlu eski kod korumak için eski platform araç takımları kullanacak ve yine de Visual Studio IDE'nin en son özelliklerden yararlanın.

Visual Studio 2019 ve üzeri v142 araç setini kullanarak, Windows XP için kod oluşturmak için destek içermez. Visual Studio 2017'de sevk v141 Araç Takımı'nı kullanarak Windows XP geliştirme desteği için Visual Studio Yükleyicisi'nde isteğe bağlı bir bileşen olarak kullanılabilir.

## <a name="install-the-windows-xp-platform-toolset"></a>Windows XP platform araç takımını yükleyin

Visual Studio 2017'deki bileşenleri hedef Windows XP ve Windows Server 2003 ve platform araç kümesini almak için Visual Studio Yükleyicisi'ni çalıştırın. Visual Studio'yu ilk kez yüklediğinizde veya seçtiğinizde **Değiştir** var olan bir yüklemesini değiştirmek için emin olun **C++ ile masaüstü geliştirme** iş yükü seçilidir. Bu iş yükü için isteğe bağlı bileşenler listesinde seçin **C++ için Windows XP desteği**ve ardından **yükleme** veya **Değiştir**.

## <a name="windows-xp-targeting-experience"></a>Windows XP hedefleme deneyimi

Visual Studio'ya dahil Windows XP platform araç takımını, Windows 7 SDK sürümüdür, ancak geçerli C++ derleyicisini kullanır. Ayrıca, uygun varsayılan değerleri, örneğin, alt düzey hedeflemek için uyumlu bir bağlayıcı belirtimi için proje özellikleri yapılandırır. Windows XP ve Windows Server 2003 çalışan bir Windows XP platform araç kümesi kullanılarak oluşturulan yalnızca Windows Masaüstü uygulamaları, ancak bu uygulamaları daha yeni Windows işletim sistemlerinde de çalıştırabilirsiniz.

#### <a name="to-target-windows-xp"></a>Windows XP hedeflemek için

1. İçinde **Çözüm Gezgini**, projeniz için kısayol menüsünü açın ve ardından **özellikleri**.

1. İçinde **özellik sayfaları** iletişim kutusuna proje için altında **yapılandırma özellikleri** > **genel**ayarlayın **Platform araç takımını** özelliğini istenen Windows XP araç. Örneğin, **Visual Studio 2017 - Windows XP (v141_xp)** kullanarak Microsoft Windows XP ve Windows Server 2003 için kod oluşturmak için C++ Visual Studio 2017'de derleyici.

### <a name="c-runtime-support"></a>C++ çalışma zamanı desteği

Windows XP platform araç takımını, C çalışma zamanı kitaplığı (CRT), C++ Standart Kitaplığı, Etkin Şablon kitaplığı (ATL), eşzamanlılık çalışma zamanı kitaplığı (ConCRT), paralel Desen kitaplığı (PPL), Microsoft Foundation Class Kitaplığı'nı (MFC) ve C++ AMP (C++ ile birlikte Çok büyük programlama Hızlandırılmış) kitaplığı, Windows XP ve Windows Server 2003 için çalışma zamanı desteği içerir. Bu işletim sistemleri için en düşük desteklenen x86, Windows XP Service Pack 2 (SP2) x64 için ve x86 hem x64 için Windows Server 2003 Service Pack 2 (SP2) için Windows XP Service Pack 3 (SP3) sürümleridir.

Bu kitaplıklar, Visual Studio tarafından yüklenmiş bağlı olarak hedef platform araç takımları tarafından desteklenir:

|Kitaplığı|Varsayılan platform araç takımı hedefleme Windows Masaüstü uygulamaları|Varsayılan Platform araç takımı hedefleme Store uygulaması|Windows XP, Windows Server 2003 hedefleyen Windows XP platform araç takımı|
|---|---|---|---|
|CRT|X|X|X|
|C++ Standart Kitaplığı|X|X|X|
|ATL|X|X|X|
|ConCRT/PPL|X|X|X|
|MFC|X||X|
|C++ AMP|X|X||

> [!NOTE]
> C +'da yazılmış uygulamalar +/ CLI ve .NET Framework 4 hedef Windows XP ve Windows Server 2003'te Çalıştır.

### <a name="differences-between-the-toolsets"></a>Araç takımları arasındaki farklar

Platform ve kitaplık desteği farklılıkları nedeniyle, bir Windows XP platform Araç Takımı'nı kullanan uygulamalar için geliştirme deneyimi tamamlandı olarak varsayılan Visual Studio platform araç takımını kullanan uygulamalar için değil.

- **C++ dili uygulama özellikleri**

   Visual Studio 2012'de uygulanan C++ dil özellikleri v110 kullanan uygulamalarda desteklenen\_xp platform araç takımı. Visual Studio 2013'te uygulanan C++ dil özellikleri v120 kullanan uygulamalarda desteklenen\_xp platform araç takımı. Visual Studio 2015'te uygulanan C++ dil özellikleri v140 kullanan uygulamalarda desteklenen\_xp platform araç takımı. Visual Studio, eski platform araç takımları kullanarak oluşturduğunda karşılık gelen derleyici kullanır. Derleyicinin bu sürümünde ek C++ dil özelliklerinden yararlanmak için en son Windows XP platform araç kümesini kullanın.

- **Uzaktan hata ayıklama**

   Visual Studio için Uzak Araçlar, Windows XP veya Windows Server 2003 üzerinde uzaktan hata ayıklamayı desteklemiyor. Windows XP veya Windows Server 2003 üzerinde çalışırken, bir uygulamanın hatalarını ayıklamak için Visual Studio'nun daha eski bir sürümden bir hata ayıklayıcı yerel olarak veya uzaktan hata ayıklamak için kullanabilirsiniz. Bu uygulama bir çalışma zamanı hedef platform araç takımını, ancak uzak bir hata ayıklama hedefi değil Windows Vista hata ayıklama deneyimini benzer.

- **Statik analiz**

   Windows 7 SDK ve çalışma zamanı kitaplıkları için SAL ek açıklamaları uyumsuz olduğu için Windows XP platform araç takımları statik analiz desteklemez. Windows XP veya Windows Server 2003 destekleyen bir uygulama üzerinde statik analiz gerçekleştirmek istediğinizde, geçici analiz gerçekleştirmek için varsayılan platform araç takımını hedefleyecek şekilde çözüme geçiş ve ardından oluşturmak için geri Windows XP platform araç takımını geçiş uygulama.

- **DirectX grafiklerinde hata ayıklama**

   Grafik hata ayıklayıcı Direct3D 9 API desteklemediği için Windows XP veya Windows Server 2003 üzerinde Direct3D kullanan uygulamalarında hata ayıklamak için kullanılamaz. Ancak, uygulama Direct3D 10 veya Direct3D 11 API'leri kullanan alternatif bir oluşturucu uygularsa, grafik hata ayıklayıcı bu API'leri kullanarak sorunları tanılamak için kullanılabilir.

- **HLSL oluşturma**

   Varsayılan olarak, Windows XP araç HLSL kaynak kodu dosyaları için derlenmiyor. HLSL dosyalarını derlemek, indirip Haziran 2010 DirectX SDK'yı ve ardından projeyi kullanıcının VC, dahil etmek için dizinler. Daha fazla bilgi için "DirectX SDK kaydetmiyor Ekle/kitaplık yollarını Visual Studio 2010 ile" bölümünü [Haziran 2010 DirectX SDK indirme sayfası](https://www.microsoft.com/download/details.aspx?displaylang=en&id=6812).
