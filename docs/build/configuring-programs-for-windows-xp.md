---
title: Windows XP için programları yapılandırma
description: Visual Studio 'da C++ Windows XP araç kümelerini yüklemek ve kullanmak.
ms.date: 03/16/2020
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
ms.openlocfilehash: 92364d7fd25ac617baacc125b279fb0ee9c92f62
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440471"
---
# <a name="configuring-programs-for-windows-xp"></a>Windows XP için programları yapılandırma

Visual Studio birden çok platform araç kümesini destekler. Bu, varsayılan araç takımı tarafından desteklenmeyen işletim sistemlerini ve çalışma zamanı kitaplıklarını hedeflemek mümkün hale gelir. Örneğin, platform araç takımını değiştirerek, Windows XP ve Windows Server 2003 ' i hedefleyen C++ uygulamalar oluşturmak Için Visual Studio 2017 derleyicisini kullanabilirsiniz. Ayrıca, ikili uyumlu eski kodu korumak ve Visual Studio IDE 'nin en son özelliklerinden yararlanmak için eski platform araç kümelerini de kullanabilirsiniz.

::: moniker range="vs-2019"

Visual Studio 2019 ' de sağlanan v142 araç takımı, Windows XP için kod oluşturmaya yönelik destek içermez. Visual Studio 2017 v141_xp araç takımını kullanarak Windows XP geliştirme desteği Visual Studio Yükleyicisi tek bir bileşen seçeneği olarak sunulmaktadır.

::: moniker-end

## <a name="install-the-windows-xp-platform-toolset"></a>Windows XP platformu araç takımını 'nı yükler

::: moniker range="<=vs-2017"

Windows XP ve Windows Server 2003 ' i hedeflemek için Visual Studio 2017 platform araç takımını ve bileşenlerini almak üzere Visual Studio Yükleyicisi çalıştırın. Visual Studio 'yu ilk yüklediğinizde veya var olan bir yüklemeyi değiştirirken, iş yüküyle **masaüstü geliştirme C++**  ' nin seçildiğinden emin olun. Bu iş yükü için isteğe bağlı bileşenler listesinde, **Windows XP desteği C++** ' ni seçin ve ardından **Install** veya **Modify**' ı seçin.

::: moniker-end

::: moniker range="vs-2019"

Windows XP ve Windows Server 2003 ' i hedeflemek için v141_xp platform araç takımını ve bileşenlerini almak üzere Visual Studio Yükleyicisi çalıştırın. Visual Studio 'yu ilk yüklediğinizde veya var olan bir yüklemeyi değiştirdiğinizde, iş yüküyle **masaüstü geliştirme C++**  ' nin seçildiğinden emin olun. **Ayrı bileşenler** sekmesinde, **derleyiciler, derleme araçları ve çalışma zamanları**altında,  **C++ vs 2017 (v141) araçları için Windows XP desteği ' ni seçin \[kullanım dışı)** ve ardından **Install** veya **Modify**' ı seçin.

::: moniker-end

## <a name="windows-xp-targeting-experience"></a>Windows XP hedefleme deneyimi

Visual Studio 'ya dahil olan Windows XP platformu araç takımı, Windows 7 SDK 'sının bir sürümüdür, ancak Visual Studio 2017 C++ derleyicisini kullanır. Ayrıca, proje özelliklerini uygun varsayılan değerlere (örneğin, alt düzey hedefleme için uyumlu bir bağlayıcı belirtimi) yapılandırır. Yalnızca Windows XP platformu araç takımı kullanılarak oluşturulan Windows Masaüstü uygulamaları, Windows XP ve Windows Server 2003 ' de çalıştırılabilir. Bu uygulamalar, daha yeni Windows işletim sistemlerinde da çalıştırılabilir.

### <a name="to-target-windows-xp"></a>Windows XP 'yi hedeflemek için

1. **Çözüm Gezgini**' de, projeniz için kısayol menüsünü açın ve ardından **Özellikler**' i seçin.

1. Projenin **Özellik sayfaları** iletişim kutusunda, **genel** > **yapılandırma özellikleri** ' ni seçin. **Platform araç takımı** özelliğini tercih ETTIĞINIZ Windows XP araç takımı olarak ayarlayın. Örneğin, Visual Studio 2017 ' de Microsoft C++ derleyicisini kullanarak Windows XP ve windows Server 2003 için kod oluşturmak üzere **Visual Studio 2017-windows XP (v141_xp)** öğesini seçin.

### <a name="c-runtime-support"></a>C++çalışma zamanı desteği

Windows XP platformu araç takımının yanı sıra, çeşitli kitaplıklar Windows XP ve Windows Server 2003 için çalışma zamanı desteği içerir. Bu kitaplıklar şunlardır: C çalışma zamanı kitaplığı (CRT), C++ standart kitaplık, etkin şablon KITAPLıĞı (ATL), eşzamanlılık çalışma zamanı kitaplığı (ConcRT), paralel Desenler kitaplığı (ppl), MICROSOFT FOUNDATION Class KITAPLıĞı (MFC) ve C++ amp (C++ hızlandırılmış çok programlama) kitaplığı. Bu işletim sistemleri için desteklenen en düşük sürümler şunlardır: x86 için Windows XP Service Pack 3 (SP3), x64 için Windows XP Service Pack 2 (SP2) ve x86 ve x64 için Windows Server 2003 Service Pack 2 (SP2).

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
> /CLI ' da yazılan ve C++.NET Framework 4 ' ü hedefleyen uygulamalar Windows XP ve windows Server 2003 ' de çalışır.

### <a name="differences-between-the-toolsets"></a>Araç kümeleri arasındaki farklar

Platform ve kitaplık desteğinin farklılığı nedeniyle, bir Windows XP platformu araç takımını kullanan uygulamalar için geliştirme deneyimi, varsayılan Visual Studio platform araç takımını kullanan uygulamalar için değildir.

- **C++dil özellikleri**

   V110 C++\_XP platform araç takımını kullanan uygulamalarda yalnızca Visual Studio 2012 ' de uygulanan dil özellikleri desteklenir. V120 C++\_XP platform araç takımını kullanan uygulamalarda yalnızca Visual Studio 2013 uygulanan dil özellikleri desteklenir. V140 C++\_XP platform araç takımını kullanan uygulamalarda yalnızca Visual Studio 2015 ' de uygulanan dil özellikleri desteklenir. V141 C++\_XP platform araç takımını kullanan uygulamalarda yalnızca Visual Studio 2017 ' de uygulanan dil özellikleri desteklenir. Visual Studio, eski platform araç kümelerini kullanarak derleme yaparken karşılık gelen derleyiciyi kullanır. Derleyicinin bu sürümünde uygulanan ek C++ dil özelliklerinden yararlanmak için en son Windows XP platformu araç takımını kullanın.

- **Uzaktan hata ayıklama**

   Visual Studio için Uzak Araçlar, Windows XP veya Windows Server 2003 ' de uzaktan hata ayıklamayı desteklemez. Windows XP veya Windows Server 2003 üzerinde yerel olarak veya uzaktan bir uygulamada hata ayıklamak için, Visual Studio 'nun eski bir sürümünden bir hata ayıklayıcı kullanın. Platform araç takımının çalışma zamanı hedefi olan ancak uzak hata ayıklama hedefi olmayan Windows Vista 'da uygulamanın hatalarını ayıklamaya benzer.

- **Statik analiz**

   Windows 7 SDK ve çalışma zamanı kitaplıkları için SAL ek açıklamaları uyumsuz olduğundan, Windows XP platformu araç kümeleri statik analizi desteklemez. Windows XP veya Windows Server 2003 ' i destekleyen bir uygulama için hala statik analiz gerçekleştirebilirsiniz. Çözümleme için varsayılan platform araç takımını hedeflemek üzere çözümü geçici olarak değiştirin ve ardından uygulamayı derlemek için Windows XP platformu araç takımı 'na geri dönün.

- **DirectX grafiklerinde hata ayıklama**

   Grafik hata ayıklayıcısı Direct3D 9 API 'yi desteklemediğinden, Windows XP veya Windows Server 2003 ' de Direct3D kullanan uygulamalarda hata ayıklamak için kullanılamaz. Ancak, uygulama Direct3D 10 veya Direct3D 11 API 'Lerine dayalı alternatif bir işleyici uygularsa, sorunları tanılamak için grafik hata ayıklayıcısını kullanabilirsiniz.

- **HLSL oluşturma**

   Windows XP araç takımı varsayılan olarak HLSL kaynak kodu dosyalarını derlemez. HLSL dosyalarını derlemek için Haziran 2010 DirectX SDK 'sını indirip yükleyin ve ardından projenin VC dizinlerini dahil etmek için ayarlayın. Daha fazla bilgi için, [haziran 2010 DIRECTX SDK indirme sayfasının](https://www.microsoft.com/download/details.aspx?displaylang=en&id=6812)"DirectX SDK 'Sı Visual Studio 2010 Ile birlikte dahil etme/kitaplık yollarını kaydetme" bölümüne bakın.
