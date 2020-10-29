---
title: Windows XP için programları yapılandırma
description: Visual Studio 'da C++ Windows XP araç kümelerini yüklemek ve kullanmak.
ms.date: 03/16/2020
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
ms.openlocfilehash: 09fe1a511c92f999e02646b9e606a3631a175215
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919377"
---
# <a name="configuring-programs-for-windows-xp"></a>Windows XP için programları yapılandırma

Visual Studio birden çok platform araç kümesini destekler. Bu, varsayılan araç takımı tarafından desteklenmeyen işletim sistemlerini ve çalışma zamanı kitaplıklarını hedeflemek mümkün hale gelir. Örneğin, platform araç takımını değiştirerek, Windows XP ve Windows Server 2003 ' i hedefleyen uygulamalar oluşturmak için Visual Studio 2017 C++ derleyicisini kullanabilirsiniz. Ayrıca, ikili uyumlu eski kodu korumak ve Visual Studio IDE 'nin en son özelliklerinden yararlanmak için eski platform araç kümelerini de kullanabilirsiniz.

::: moniker range="msvc-160"

Visual Studio 2019 ' de sağlanan v142 araç takımı, Windows XP için kod oluşturmaya yönelik destek içermez. Visual Studio 2017 v141_xp araç takımını kullanarak Windows XP geliştirme desteği Visual Studio Yükleyicisi tek bir bileşen seçeneği olarak sunulmaktadır.

::: moniker-end

## <a name="install-the-windows-xp-platform-toolset"></a>Windows XP platformu araç takımını 'nı yükler

::: moniker range="<=msvc-150"

Windows XP ve Windows Server 2003 ' i hedeflemek için Visual Studio 2017 platform araç takımını ve bileşenlerini almak üzere Visual Studio Yükleyicisi çalıştırın. Visual Studio 'Yu ilk yüklediğinizde veya var olan bir yüklemeyi değiştirirken, C++ iş yüküyle **masaüstü geliştirme** 'nın seçildiğinden emin olun. Bu iş yükü için isteğe bağlı bileşenler listesinde, **C++ Için WINDOWS XP desteği** ' ni seçin ve ardından **Install** veya **Modify** ' ı seçin.

::: moniker-end

::: moniker range="msvc-160"

Windows XP ve Windows Server 2003 ' i hedeflemek için v141_xp platform araç takımını ve bileşenlerini almak üzere Visual Studio Yükleyicisi çalıştırın. Visual Studio 'Yu ilk yüklediğinizde veya var olan bir yüklemeyi değiştirirken, C++ iş yüküyle **masaüstü geliştirme** 'nın seçildiğinden emin olun. **Ayrı bileşenler** sekmesinde, **derleyiciler, derleme araçları ve çalışma zamanları** altında, **vs 2017 (V141) araçları için C++ Windows XP desteği \[ kullanım dışı** ' yı seçin ve ardından **Install** veya **Modify** ' ı seçin.

::: moniker-end

## <a name="windows-xp-targeting-experience"></a>Windows XP hedefleme deneyimi

Visual Studio 'ya dahil olan Windows XP platformu araç takımı, Windows 7 SDK 'sının bir sürümüdür, ancak Visual Studio 2017 C++ derleyicisini kullanır. Ayrıca, proje özelliklerini uygun varsayılan değerlere (örneğin, alt düzey hedefleme için uyumlu bir bağlayıcı belirtimi) yapılandırır. Yalnızca Windows XP platformu araç takımı kullanılarak oluşturulan Windows Masaüstü uygulamaları, Windows XP ve Windows Server 2003 ' de çalıştırılabilir. Bu uygulamalar, daha yeni Windows işletim sistemlerinde da çalıştırılabilir.

### <a name="to-target-windows-xp"></a>Windows XP 'yi hedeflemek için

1. **Çözüm Gezgini** ' de, projeniz için kısayol menüsünü açın ve ardından **Özellikler** ' i seçin.

1. Projenin **Özellik sayfaları** iletişim kutusunda, **yapılandırma özellikleri**  >  **genel** ' i seçin. **Platform araç takımı** özelliğini tercih ETTIĞINIZ Windows XP araç takımı olarak ayarlayın. Örneğin, Visual Studio 2017 ' de Microsoft C++ derleyicisini kullanarak Windows XP ve Windows Server 2003 için kod oluşturmak üzere **Visual studio 2017-WINDOWS XP (v141_xp)** öğesini seçin.

### <a name="c-runtime-support"></a>C++ çalışma zamanı desteği

Windows XP platformu araç takımının yanı sıra, çeşitli kitaplıklar Windows XP ve Windows Server 2003 için çalışma zamanı desteği içerir. Bu kitaplıklar şunlardır: C çalışma zamanı kitaplığı (CRT), C++ standart kitaplığı, etkin şablon kitaplığı (ATL), Eşzamanlılık Çalışma Zamanı Kitaplığı (ConCRT), paralel Desenler kitaplığı (PPL), Microsoft Foundation Class Kitaplığı (MFC) ve C++ AMP (C++ hızlandırılmış büyük programlama) kitaplığı. Bu işletim sistemleri için desteklenen en düşük sürümler şunlardır: x86 için Windows XP Service Pack 3 (SP3), x64 için Windows XP Service Pack 2 (SP2) ve x86 ve x64 için Windows Server 2003 Service Pack 2 (SP2).

Bu kitaplıklar, hedefe bağlı olarak Visual Studio tarafından yüklenen platform araç kümeleri tarafından desteklenir:

|Kitaplık|Windows masaüstü uygulamalarını hedefleyen varsayılan platform araç takımı|Mağaza uygulamalarını hedefleyen varsayılan platform araç takımı|Windows XP, Windows Server 2003 ' i hedefleyen Windows XP platformu araç takımı|
|---|---|---|---|
|CRT|X|X|X|
|C++ Standart Kitaplığı|X|X|X|
|ATL|X|X|X|
|ConCRT/PPL|X|X|X|
|MFC|X||X|
|C++ AMP|X|X||

> [!NOTE]
> C++/CLı ' da yazılmış ve .NET Framework 4 ' ü hedefleyen uygulamalar Windows XP ve Windows Server 2003 ' de çalışır.

### <a name="differences-between-the-toolsets"></a>Araç kümeleri arasındaki farklar

Platform ve kitaplık desteğinin farklılığı nedeniyle, bir Windows XP platformu araç takımını kullanan uygulamalar için geliştirme deneyimi, varsayılan Visual Studio platform araç takımını kullanan uygulamalar için değildir.

- **C++ dil özellikleri**

   V110 XP platform araç takımını kullanan uygulamalarda yalnızca Visual Studio 2012 ' de uygulanan C++ dil özellikleri desteklenir \_ . V120 XP platform araç takımını kullanan uygulamalarda yalnızca Visual Studio 2013 uygulanan C++ dil özellikleri desteklenir \_ . V140 XP platform araç takımını kullanan uygulamalarda yalnızca Visual Studio 2015 ' de uygulanan C++ dil özellikleri desteklenir \_ . V141 XP platform araç takımını kullanan uygulamalarda yalnızca Visual Studio 2017 ' de uygulanan C++ dil özellikleri desteklenir \_ . Visual Studio, eski platform araç kümelerini kullanarak derleme yaparken karşılık gelen derleyiciyi kullanır. Derleyicinin bu sürümünde uygulanan ek C++ dil özelliklerinden yararlanmak için en son Windows XP platformu araç takımını kullanın.

- **Uzaktan hata ayıklama**

   Visual Studio için Uzak Araçlar, Windows XP veya Windows Server 2003 ' de uzaktan hata ayıklamayı desteklemez. Windows XP veya Windows Server 2003 üzerinde yerel olarak veya uzaktan bir uygulamada hata ayıklamak için, Visual Studio 'nun eski bir sürümünden bir hata ayıklayıcı kullanın. Platform araç takımının çalışma zamanı hedefi olan ancak uzak hata ayıklama hedefi olmayan Windows Vista 'da uygulamanın hatalarını ayıklamaya benzer.

- **Statik analiz**

   Windows 7 SDK ve çalışma zamanı kitaplıkları için SAL ek açıklamaları uyumsuz olduğundan, Windows XP platformu araç kümeleri statik analizi desteklemez. Windows XP veya Windows Server 2003 ' i destekleyen bir uygulama için hala statik analiz gerçekleştirebilirsiniz. Çözümleme için varsayılan platform araç takımını hedeflemek üzere çözümü geçici olarak değiştirin ve ardından uygulamayı derlemek için Windows XP platformu araç takımı 'na geri dönün.

- **DirectX grafiklerinde hata ayıklama**

   Grafik hata ayıklayıcısı Direct3D 9 API 'yi desteklemediğinden, Windows XP veya Windows Server 2003 ' de Direct3D kullanan uygulamalarda hata ayıklamak için kullanılamaz. Ancak, uygulama Direct3D 10 veya Direct3D 11 API 'Lerine dayalı alternatif bir işleyici uygularsa, sorunları tanılamak için grafik hata ayıklayıcısını kullanabilirsiniz.

- **HLSL oluşturma**

   Windows XP araç takımı varsayılan olarak HLSL kaynak kodu dosyalarını derlemez. HLSL dosyalarını derlemek için Haziran 2010 DirectX SDK 'sını indirip yükleyin ve ardından projenin VC dizinlerini dahil etmek için ayarlayın. Daha fazla bilgi için, [haziran 2010 DIRECTX SDK indirme sayfasının](https://www.microsoft.com/download/details.aspx?displaylang=en&id=6812)"DirectX SDK 'Sı Visual Studio 2010 Ile birlikte dahil etme/kitaplık yollarını kaydetme" bölümüne bakın.
