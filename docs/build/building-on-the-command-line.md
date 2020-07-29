---
title: Komut satırından Microsoft C++ araç takımını kullanın
description: Visual Studio IDE 'nin dışında, komut satırından Microsoft C++ (MSVC) derleyicisi araç takımını kullanın.
ms.custom: conceptual
ms.date: 04/21/2020
helpviewer_keywords:
- command-line builds [C++]
- compiling source code [C++], command line
- builds [C++], command-line
- command line [C++], building from
- command line [C++], compilers
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
ms.openlocfilehash: f729947e4d798e5817ff8d4e5abe09eaca090e01
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229902"
---
# <a name="use-the-microsoft-c-toolset-from-the-command-line"></a>Komut satırından Microsoft C++ araç takımını kullanın

Visual Studio 'da bulunan araçları kullanarak komut satırında C ve C++ uygulamaları oluşturabilirsiniz. Microsoft C++ (MSVC) derleyicisi araç takımı Ayrıca tek başına bir paket olarak indirilebilir. Kullanmayı planlamıyorsanız, Visual Studio IDE 'yi yüklemeniz gerekmez.

> [!NOTE]
> Bu makalede, bireysel derleyicileri, Linler, kütüphaneian ve diğer temel araçları kullanmak için bir ortam ayarlama hakkında bilgi sağlanır. Yerel proje derleme sistemi, MSBuild, bu makalede açıklandığı gibi ortamı kullanmaz. MSBuild 'i komut satırından kullanma hakkında daha fazla bilgi için bkz. [komut satırı-C++ üzerinde MSBuild](msbuild-visual-cpp.md).

## <a name="download-and-install-the-tools"></a>Araçları indirme ve yükleme

Visual Studio ve bir C++ iş yükü yüklediyseniz, tüm komut satırı araçlarına sahip olursunuz. C++ ve Visual Studio 'Nun nasıl yükleneceği hakkında bilgi için bkz. [Visual Studio 'Da c++ desteğini yüklemek](vscpp-step-0-installation.md). Yalnızca komut satırı araç takımını istiyorsanız, [Visual Studio Için derleme araçları](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019)' nı indirin. İndirilen çalıştırılabiliri çalıştırdığınızda Visual Studio Yükleyicisi güncelleştirir ve çalıştırır. Yalnızca C++ geliştirme için ihtiyacınız olan araçları yüklemek için, **C++ derleme araçları** iş yükünü seçin. **Yükleme ayrıntıları**altına dahil etmek için isteğe bağlı kitaplıkları ve araç kümelerini seçebilirsiniz. Visual Studio 2015 veya 2017 Toolsets 'i kullanarak kod derlemek için isteğe bağlı MSVC v140 veya MSVC v141 derleme araçlarını seçin. Seçimlerinizden memnun kaldığınızda, **yüklensin**' i seçin.

## <a name="how-to-use-the-command-line-tools"></a>Komut satırı araçlarını kullanma

Visual Studio Yükleyicisi C++ iş yüklerinden birini seçtiğinizde, Visual Studio *platform araç takımını*yüklenir. Platform araç takımı, belirli bir Visual Studio sürümü için tüm C ve C++ araçlarına sahiptir. Araçlar, C/C++ derleyicileri, Linler, birleştiriciler ve diğer derleme araçlarını ve eşleşen kitaplıkları içerir. Bu araçların tümünü komut satırında kullanabilirsiniz. Bunlar, Visual Studio IDE tarafından dahili olarak da kullanılır. X86, x64, ARM ve ARM64 hedefleri için kod oluşturmaya yönelik ayrı x86 barındırılan ve x64 'de barındırılan derleyiciler ve araçlar vardır. Belirli bir konak ve hedef yapı mimarisi için her bir araç kümesi kendi dizininde saklanır.

Doğru çalışmak için, araçların ayarlanması için birkaç belirli ortam değişkeni gerekir. Bu değişkenler, araçları yola eklemek ve içerme dosyası, kitaplık dosyası ve SDK konumlarını ayarlamak için kullanılır. Bu ortam değişkenlerini ayarlamayı kolaylaştırmak için yükleyici, yükleme sırasında özelleştirilmiş *komut dosyaları*veya toplu iş dosyaları oluşturur. Belirli bir konak ve hedef yapı mimarisini, Windows SDK sürümünü ve platform araç takımını ayarlamak için bu komut dosyalarından birini çalıştırabilirsiniz. Kolaylık sağlamak için yükleyici, başlangıç menüsünde kısayollar da oluşturur. Kısayollar, geliştirici komut istemi ' ni, konak ve hedefin belirli birleşimleri için bu komut dosyalarını kullanarak başlatır. Bu kısayollar, tüm gerekli ortam değişkenlerinin ayarlanmış ve kullanıma hazırsa emin olmanızı sağlar.

Gerekli ortam değişkenleri, yüklemenize ve seçtiğiniz yapı mimarisine özgüdür. Bunlar, ürün güncelleştirmeleri veya yükseltmeleri tarafından da değiştirilebilir. Bu nedenle, ortam değişkenlerini kendiniz ayarlamak yerine, yüklü bir komut istemi kısayolunu veya komut dosyasını kullanmanızı öneririz. Daha fazla bilgi için bkz. [komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlama](setting-the-path-and-environment-variables-for-command-line-builds.md).

Araç kümeleri, komut dosyaları ve kısayollar, bilgisayar işlemcinize ve yükleme sırasında seçtiğiniz seçeneklere bağlıdır. X86 ve x64 kod oluşturan x86 barındırılan araçlar ve çapraz Araçlar her zaman yüklenir. 64 bit Windows sürümü varsa, x86 ve x64 kodu oluşturan x64 tarafından barındırılan araçlar ve çapraz araçlar da yüklenir. İsteğe bağlı C++ Evrensel Windows Platformu Araçları ' nı seçerseniz, ARM ve ARM64 kodu oluşturan x86 ve x64 araçları da yüklenir. Diğer iş yükleri ek araçlar yükleyebiliriz.

## <a name="developer-command-prompt-shortcuts"></a><a name="developer_command_prompt_shortcuts"></a>Geliştirici komut istemi kısayolları

Komut istemi kısayolları, başlangıç menünüzde sürüme özgü bir Visual Studio klasörüne yüklenir. Temel komut istemi kısayollarının ve destekledikleri yapı mimarilerinin listesi aşağıda verilmiştir:

- **Geliştirici komut istemi** -ortamı, 32 bit, x86 yerel kodu derlemek için 32 bitlik, x86 yerel araçları kullanacak şekilde ayarlar.
- **x86 yerel araçları komut istemi** -ortamı, 32 bit, x86 yerel kodu derlemek için 32 bitlik, x86 yerel araçları kullanacak şekilde ayarlar.
- **x64 yerel araçları komut istemi** -ortamı, 64 bit, x64 yerel kodu derlemek için 64 bit, x64-yerel araçları kullanacak şekilde ayarlar.
- **x86_x64 çapraz araçları komut istemi** -ortamı, 64 bit, x64 yerel kodu derlemek için 32 bitlik, x86 yerel araçları kullanacak şekilde ayarlar.
- **x64_x86 çapraz araçları komut istemi** -ortamı, 32 bit, x86 yerel kodu derlemek için 64 bit, x64-yerel araçları kullanacak şekilde ayarlar.

::: moniker range=">= vs-2019"

Başlat menüsü klasörü ve kısayol adları, Visual Studio 'nun yüklü sürümüne bağlı olarak farklılık gösterir. Bir tane ayarlarsanız, yükleme **takma**adına de bağlıdır. Örneğin, Visual Studio 2019 ' i yüklediğinizi ve size *en son*bir takma ad verdiğinizi varsayalım. Geliştirici komut istemi kısayolu, **VS 2019 (en son) için geliştirici komut istemi**, **Visual Studio 2019**adlı bir klasörde adlandırılır.

::: moniker-end
::: moniker range="= vs-2017"

Başlat menüsü klasörü ve kısayol adları, Visual Studio 'nun yüklü sürümüne bağlı olarak farklılık gösterir. Bir tane ayarlarsanız, yükleme **takma**adına de bağlıdır. Örneğin, Visual Studio 2017 ' i yüklediğinizi ve size *en son*bir takma ad verdiğinizi varsayalım. Geliştirici komut istemi kısayolu, **VS 2017 (en son) için geliştirici komut istemi**, **Visual Studio 2017**adlı bir klasörde adlandırılır.

::: moniker-end
::: moniker range="< vs-2017"

Başlat menüsü klasörü ve kısayol adları, Visual Studio 'nun yüklü sürümüne bağlı olarak farklılık gösterir. Örneğin, Visual Studio 2015 ' i yüklediğinizi varsayalım. Geliştirici komut istemi kısayolunun **VS 2015 için geliştirici komut istemi**adı verilir.

::: moniker-end

### <a name="to-open-a-developer-command-prompt-window"></a><a name="developer_command_prompt"></a>Bir geliştirici komut istemi penceresi açmak için

1. Masaüstünde, Windows **Başlat** menüsünü açın ve ardından Visual Studio sürümünüz için klasörü bulun ve açın. Örneğin, **Visual Studio 2019**.

1. Klasöründe, Visual Studio sürümünüz için **Geliştirici komut istemi** seçin. Bu kısayol, 32 bit, x86 yerel kodu derlemek için 32 bitlik, x86 yerel araçların varsayılan yapı mimarisini kullanan bir geliştirici komut istemi penceresi başlatır. Varsayılan olmayan bir yapı mimarisini tercih ediyorsanız, konak ve hedef mimariyi belirtmek için yerel veya çapraz Araçlar komut istemlerinin birini seçin.

Bir geliştirici komut istemi açmak için daha hızlı bir yol için, masaüstü arama kutusuna *Geliştirici komut istemi* ' ni girin. Ardından istediğiniz sonucu seçin.

## <a name="developer-command-file-locations"></a><a name="developer_command_file_locations"></a>Geliştirici komut dosyası konumları

Yapı ortamını varolan bir komut istemi penceresinde ayarlamayı tercih ediyorsanız, yükleyici tarafından oluşturulan komut dosyalarından birini kullanabilirsiniz. Yeni bir komut istemi penceresinde ortamı ayarlamanızı öneririz. Aynı komut penceresindeki ortamları daha sonra geçmeniz önerilmez.

::: moniker range=">= vs-2019"

Komut dosyası konumu, yüklediğiniz Visual Studio sürümüne ve yükleme sırasında yaptığınız seçimlere bağlı olarak değişir. Visual Studio 2019 için, 64 bit sistemdeki tipik yükleme konumu \\ Program Files (x86) \\ Microsoft Visual Studio \\ 2019 \\ *Edition*' dır. *Sürüm* Community, Professional, Enterprise, buildtools veya sağladığınız başka bir takma ad olabilir.

::: moniker-end
::: moniker range="= vs-2017"

Komut dosyası konumu, yüklediğiniz Visual Studio sürümüne ve yükleme sırasında yaptığınız seçimlere bağlı olarak değişir. Visual Studio 2017 için, 64 bit sistemdeki tipik yükleme konumu \\ Program Files (x86) \\ Microsoft Visual Studio \\ 2017 \\ *Edition*' dır. *Sürüm* Community, Professional, Enterprise, buildtools veya sağladığınız başka bir takma ad olabilir.

::: moniker-end
::: moniker range="< vs-2017"

Komut dosyası konumu, Visual Studio sürümüne ve yükleme dizinine göre değişir. Visual Studio 2015 için, tipik yükleme konumu \\ Program Files (x86) \\ Microsoft Visual Studio 14,0 ' dir.

::: moniker-end

Birincil Geliştirici komut istemi komut dosyası VsDevCmd.bat, Common7 \\ araçları alt dizininde bulunur. Hiçbir parametre belirtilmediğinde, ortamı, 32 bit x86 kodu oluşturmak için x86 yerel araçları kullanacak şekilde ayarlar.

::: moniker range=">= vs-2017"

Belirli derleme mimarilerini ayarlamak için daha fazla komut dosyası kullanılabilir. Kullanılabilen komut dosyaları, Visual Studio iş yüklerine ve yüklediğiniz seçeneklere bağlıdır. Visual Studio 2017 ve Visual Studio 2019 ' de, bunları VC \\ yardımcı \\ derleme alt dizininde bulabilirsiniz.

::: moniker-end
::: moniker range="< vs-2017"

Belirli derleme mimarilerini ayarlamak için daha fazla komut dosyası kullanılabilir. Kullanılabilen komut dosyaları, Visual Studio iş yüklerine ve yüklediğiniz seçeneklere bağlıdır. Visual Studio 2015 ' de, mimari, VC \\ bin veya VC \\ bin \\ *mimari* alt dizinlerinde bulunur, bu, *mimarinin* yerel veya çapraz derleyici seçeneklerinden biridir.

::: moniker-end

Bu komut dosyaları varsayılan parametreleri ayarlar ve belirtilen yapı mimarisi ortamını ayarlamak için VsDevCmd.bat çağırır. Tipik bir yükleme, şu komut dosyalarını içerebilir:

|Komut dosyası|Konak ve hedef mimarileri|
|---|---|
|**vcvars32.bat**| 32 bit x86 yerel araçlarını kullanarak 32 bit x86 kodu oluşturun.|
|**vcvars64.bat**| 64 bit x64-yerel araçlarını kullanarak 64 bit x64 kodu oluşturun.|
|**vcvarsx86_amd64.bat**| 32-bit x86 yerel çapraz araçlarını kullanarak 64 bit x64 kodu oluşturun.|
|**vcvarsamd64_x86.bat**| 64-bit x64-yerel çapraz araçlarını kullanarak 32 bit x86 kodu oluşturun.|
|**vcvarsx86_arm.bat**| ARM kodu oluşturmak için 32 bitlik x86 yerel çapraz araçları kullanın.|
|**vcvarsamd64_arm.bat**| ARM kodu oluşturmak için 64 bitlik x64 yerel çapraz araçları kullanın.|
|**vcvarsall.bat**| Konak ve hedef mimarileri, Windows SDK ve platform seçeneklerini belirtmek için parametreleri kullanın. Desteklenen seçeneklerin listesi için, **/help** parametresini kullanarak çağırın.|

> [!CAUTION]
> vcvarsall.bat dosyası ve diğer Visual Studio komut dosyaları bilgisayardan bilgisayara farklılık gösterebilir. Eksik veya hasarlı bir vcvarsall.bat dosyasını başka bir bilgisayardaki bir dosya kullanarak değiştirmeyin. Eksik dosyayı değiştirmek için Visual Studio yükleyicisini yeniden çalıştırın.
>
> vcvarsall.bat dosyası sürümden sürüme de değişir. Visual Studio 'nun geçerli sürümü, Visual Studio 'nun önceki bir sürümüne de sahip olan bir bilgisayarda yüklüyse, aynı komut istemi penceresinde farklı sürümlerden vcvarsall.bat veya başka bir Visual Studio komut dosyası çalıştırmayın.

## <a name="use-the-developer-tools-in-an-existing-command-window"></a>Varolan bir komut penceresinde geliştirici araçlarını kullanma

Varolan bir komut penceresinde belirli bir yapı mimarisini belirtmenin en kolay yolu vcvarsall.bat dosyasını kullanmaktır. Yerel 32-bit veya 64 bit derleme için komut satırını yapılandırmak üzere ortam değişkenlerini ayarlamak için vcvarsall.bat kullanın. Bağımsız değişkenler, x86, x64, ARM veya ARM64 işlemcilerde çapraz derleme belirtmenize olanak tanır. Microsoft Store, Evrensel Windows Platformu veya Windows Masaüstü platformlarını hedefleyebilirsiniz. Hangi Windows SDK kullanacağınızı bile belirtebilir ve platform araç takımı sürümünü seçebilirsiniz.

Bağımsız değişken olmadan kullanıldığında vcvarsall.bat, ortam değişkenlerini 32 bitlik Windows Masaüstü hedefleri için geçerli x86 yerel derleyicisini kullanacak şekilde yapılandırır. Ortamı yerel veya çapraz derleyici araçlarından birini kullanacak şekilde yapılandırmak için bağımsız değişken ekleyebilirsiniz. vcvarsall.bat, bilgisayarınızda yüklü olmayan veya kullanılamayan bir yapılandırma belirtirseniz bir hata iletisi görüntüler.

### <a name="vcvarsall-syntax"></a>vcvarsall sözdizimi

> **vcvarsall.bat** [*mimari*] [*platform_type*] [*winsdk_version*] [**-vcvars_ver =**_vcversion_]

*mimarisini*<br/>
Bu isteğe bağlı bağımsız değişken kullanılacak konak ve hedef mimarisini belirtir. *Mimari* belirtilmemişse, varsayılan derleme ortamı kullanılır. Bu bağımsız değişkenler desteklenir:

|*mimarisini*|Derleyici|Konak bilgisayar mimarisi|Derleme çıkışı (hedef) mimarisi|
|----------------------------|--------------|----------------------------------|-------------------------------|
|**x86**|x86 32 bit yerel|x86, x64|x86|
|**x86 \_ AMD64** veya **x86 \_ x64**|x86 çapraz üzerinde x64|x86, x64|x64|
|**x86_arm**|X86 çapraz üzerinde ARM|x86, x64|ARM|
|**x86_arm64**|ARM64 üzerinde x86 çapraz|x86, x64|ARM64|
|**AMD64** veya **x64**|x64 64-bit yerel|x64|x64|
|**AMD64 \_ x86** veya **x64 \_ x86**|x64 üzerinde x86 çapraz|x64|x86|
|**AMD64 \_ ARM** veya **x64 \_ ARM**|X64 çapraz ARM|x64|ARM|
|**AMD64 \_ arm64** veya **x64 \_ arm64**|X64 çapraz ARM64|x64|ARM64|

*platform_type*<br/>
Bu isteğe bağlı bağımsız değişken platform türü olarak **Store** veya **UWP** belirtmenize olanak tanır. Varsayılan olarak, ortam masaüstü veya konsol uygulamaları oluşturmak üzere ayarlanır.

*winsdk_version*<br/>
İsteğe bağlı olarak, kullanılacak Windows SDK sürümünü belirtir. Varsayılan olarak, en son yüklenen Windows SDK kullanılır. Windows SDK sürümünü belirtmek için, **10.0.10240.0**gibi tam bir WINDOWS 10 SDK numarası kullanabilir veya Windows 8.1 SDK 'sını kullanmak için **8,1** belirtebilirsiniz.

*vcversion*<br/>
İsteğe bağlı olarak, kullanılacak Visual Studio derleyici araç takımını belirtir. Varsayılan olarak, ortam, geçerli Visual Studio derleyicisi araç takımını kullanacak şekilde ayarlanır.

::: moniker range=">= vs-2019"

Visual Studio 2019 derleyici araç takımının belirli bir sürümünü belirtmek için **-vcvars_ver = 14.2 x. yyyyy** kullanın.

Visual Studio 2017 derleyici araç takımının en son sürümünü belirtmek için **-vcvars_ver = 14.16** kullanın.

::: moniker-end
::: moniker range="= vs-2017"

Visual Studio 2017 derleyici araç takımının en son sürümünü belirtmek için **-vcvars_ver = 14.16** kullanın.

Visual Studio 2017 derleyici araç takımının belirli bir sürümünü belirtmek için **-vcvars_ver = 14,1 x. yyyyy** kullanın.

::: moniker-end

Visual Studio 2015 derleyici araç takımını belirtmek için **-vcvars_ver = 14.0** kullanın.

#### <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a><a name="vcvarsall"></a>Derleme ortamını varolan bir komut istemi penceresinde ayarlamak için

1. Komut isteminde, Visual Studio yükleme dizinine geçmek için CD komutunu kullanın. Ardından, yapılandırmaya özgü komut dosyalarını içeren alt dizine geçmek için CD 'yi yeniden kullanın. Visual Studio 2019 ve Visual Studio 2017 için, *VC \\ yardımcı \\ derleme* alt dizinini kullanın. Visual Studio 2015 için *VC* alt dizinini kullanın.

1. Tercih ettiğiniz geliştirici ortamınız için komutunu girin. Örneğin, 64 bitlik bir platformda UWP için ARM kodu oluşturmak için, en son Windows SDK ve Visual Studio derleyicisi araç takımını kullanarak şu komut satırını kullanın:

   `vcvarsall.bat amd64_arm uwp`

## <a name="create-your-own-command-prompt-shortcut"></a>Kendi komut istemi kısayolunuzu oluşturun

::: moniker range=">= vs-2019"

Kullanılan komut hedefini görmek için geliştirici komut istemi kısayolunun Özellikler iletişim kutusunu açın. Örneğin, **VS 2019 kısayolunun x64 yerel araçları komut istemi** hedefi şuna benzer bir şeydir:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvars64.bat"`

::: moniker-end
::: moniker range="= vs-2017"

Kullanılan komut hedefini görmek için geliştirici komut istemi kısayolunun Özellikler iletişim kutusunu açın. Örneğin, **VS 2017 kısayolunun x64 yerel araçları komut istemi** hedefi şuna benzer bir şeydir:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvars64.bat"`

::: moniker-end
::: moniker range="< vs-2017"

Kullanılan komut hedefini görmek için geliştirici komut istemi kısayolunun Özellikler iletişim kutusunu açın. Örneğin, **VS2015 x64 yerel araçları komut istemi** kısayolunun hedefi şuna benzer bir şeydir:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\vcvarsall.bat" amd64`

::: moniker-end

Mimariye özgü toplu iş dosyaları *mimari* parametresini ayarlar ve vcvarsall.bat çağırır. Aynı seçenekleri, vcvarsall.bat geçirdiğiniz gibi bu toplu iş dosyalarına geçirebilirsiniz veya doğrudan vcvarsall.bat çağırabilirsiniz. Kendi komut kısayolunuzun parametrelerini belirtmek için bunları çift tırnaklı komutun sonuna ekleyin. Örneğin, en son Windows SDK kullanarak 64 bitlik bir platformda UWP için ARM kodu oluşturmaya yönelik bir kısayol aşağıda verilmiştir. Önceki bir derleyici araç takımını kullanmak için sürüm numarasını belirtin. Kısayolunuzun bu komut hedefi gibi bir şey kullanın:

::: moniker range=">= vs-2019"

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvarsall.bat" amd64_arm uwp -vcvars_ver=14.16`

::: moniker-end
::: moniker range="= vs-2017"

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvarsall.bat" amd64_arm uwp -vcvars_ver=14.0`

::: moniker-end
::: moniker range="< vs-2017"

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\vcvarsall.bat" amd64 -vcvars_ver=12.0`

::: moniker-end

Yolu, Visual Studio yükleme dizininizi yansıtacak şekilde ayarlayın. vcvarsall.bat dosyası belirli sürüm numaraları hakkında ek bilgiler içerir.

## <a name="command-line-tools"></a>Komut satırı araçları

Bir komut isteminde C/C++ projesi oluşturmak için, Visual Studio şu komut satırı araçlarını sağlar:

[CL](reference/compiling-a-c-cpp-program.md)<br/>
Kaynak kodu dosyalarını derlemek ve uygulamalar, kitaplıklar ve DLL 'Lerde bağlamak için derleyicisini (cl.exe) kullanın.

[Bağlantı](reference/linking.md)<br/>
Derlenen nesne dosyalarını ve kitaplıklarını uygulamalar ve DLL 'Lere bağlamak için bağlayıcı (link.exe) kullanın.

[NMAKE](reference/nmake-reference.md)<br/>
Geleneksel derleme görevleri dosyasını temel alan C++ projeleri oluşturmak için Windows 'ta NMAKE (nmake.exe) kullanın.

Komut satırında oluşturduğunuzda F1 komutu anında yardım için kullanılamaz. Bunun yerine, uyarılar, hatalar ve iletilerle ilgili bilgi almak için bir arama motoru kullanabilirsiniz. Ayrıca çevrimdışı Yardım dosyalarını indirebilir ve kullanabilirsiniz. Arama 'yı [docs.Microsoft.com](https://docs.microsoft.com/cpp/)içinde kullanmak için, herhangi bir makalenin üst kısmındaki arama kutusuna sorgunuzu girin.

## <a name="command-line-project-management-tools"></a>Komut satırı proje yönetimi araçları

Visual Studio IDE, MSBuild 'e göre yerel bir proje yapı sistemi kullanır. Doğrudan MSBuild 'i çağırabilir veya IDE 'yi kullanmadan yerel proje sistemini kullanabilirsiniz:

[MSBuild](msbuild-visual-cpp.md)<br/>
Bir derlemeyi yapılandırmak ve araç takımını dolaylı olarak çağırmak için MSBuild (msbuild.exe) ve proje dosyası (. vcxproj) kullanın. Visual Studio IDE 'de **Build** Project veya **Build Solution** komutunu çalıştırmaya eşdeğerdir. Komut satırından MSBuild çalıştırmak, gelişmiş bir senaryodur ve sık önerilmez. Visual Studio sürüm 16,5 ' den başlayarak MSBuild, kullanılan araç takımını ve kitaplıkları denetlemek için komut satırı ortamını kullanmaz.

[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)<br/>
Visual Studio IDE 'yi görüntülemeden belirli derleme komutlarını yürütmek için **/Build** veya **/Clean** gibi bir komut satırı anahtarıyla birleştirilmiş devenv (devenv.exe) kullanın. Genel olarak, Visual Studio 'nun MSBuild 'in karmaşıklıklarını işleyebilmesine izin vermek için doğrudan MSBuild kullanılarak DEVENV tercih edilir. Visual Studio sürüm 16,5 ' den başlayarak DEVENV, kullanılan araç takımını ve kitaplıkları denetlemek için komut satırı ortamını kullanmaz.

## <a name="in-this-section"></a>Bu bölümde

Bu makalelerde, komut satırında uygulama oluşturma ve komut satırı derleme ortamının nasıl özelleştirileceği açıklanır. Bazıları, 64-bit araç kümelerinin nasıl kullanılacağını ve x86, x64, ARM ve ARM64 platformlarını hedef alan bir şekilde gösterir. Ayrıca, komut satırı derleme araçları MSBuild ve NMAKE kullanımını da anlatmaktadır.

[İzlenecek yol: komut satırında yerel C++ programını derleme](walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>
Komut satırında C++ programını oluşturmayı ve derlemeyi gösteren bir örnek sağlar.

[İzlenecek yol: Komut satırında C programı derleme](walkthrough-compile-a-c-program-on-the-command-line.md)<br/>
C programlama dilinde yazılmış bir programın nasıl derleneceğini açıklar.

[İzlenecek yol: Komut satırında C++/CLI programı derleme](walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)<br/>
.NET Framework kullanan bir C++/CLı programını oluşturmayı ve derlemeyi açıklar.

[İzlenecek yol: Komut satırında C++/CX programı derleme](walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)<br/>
Windows Çalışma Zamanı kullanan bir C++/CX programını oluşturmayı ve derlemeyi açıklar.

[Komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlama](setting-the-path-and-environment-variables-for-command-line-builds.md)<br/>
X86, x64, ARM ve ARM64 platformlarını hedeflemek için ortam değişkenlerini 32-bit veya 64 bit araç takımını kullanacak şekilde ayarlama.

[NMAKE başvurusu](reference/nmake-reference.md)<br/>
Microsoft program bakım yardımcı programını (NMAKE.EXE) tanımlayan makalelere bağlantılar sağlar.

[Komut satırında MSBuild-C++](msbuild-visual-cpp.md)<br/>
Komut satırından msbuild.exe kullanmayı tartışan makalelere bağlantılar sağlar.

## <a name="related-sections"></a>İlgili bölümler

[/MD,/MT,/LD (çalışma zamanı kitaplığını kullan)](reference/md-mt-ld-use-run-time-library.md)<br/>
Bu derleyici seçeneklerinin bir hata ayıklama veya sürüm çalışma zamanı kitaplığı kullanmak için nasıl kullanılacağını açıklar.

[C/C++ derleyici seçenekleri](reference/compiler-options.md)<br/>
C ve C++ derleyici seçeneklerini ve CL.exe tartışan makalelere bağlantılar sağlar.

[MSVC bağlayıcı seçenekleri](reference/linker-options.md)<br/>
Bağlayıcı seçeneklerini ve LINK.exe tartışan makalelere bağlantılar sağlar.

[Ek MSVC derleme araçları](reference/c-cpp-build-tools.md)<br/>
Visual Studio 'da bulunan C/C++ derleme araçlarına bağlantılar sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Projeler ve derleme sistemleri](projects-and-build-systems-cpp.md)
