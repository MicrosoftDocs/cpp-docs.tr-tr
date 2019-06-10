---
title: Microsoft kullanım C++ komut satırında araç takımı
description: Visual Studio IDE dışında komut satırından Microsoft C++ Derleyici araç zincirini (MSVC) kullanın.
ms.custom: conceptual
ms.date: 06/06/2019
helpviewer_keywords:
- command-line builds [C++]
- compiling source code [C++], command line
- builds [C++], command-line
- command line [C++], building from
- command line [C++], compilers
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
ms.openlocfilehash: b5e9bf266d79ee86cae84535641a52c7c52be391
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821144"
---
# <a name="use-the-microsoft-c-toolset-from-the-command-line"></a>Microsoft kullanım C++ komut satırında araç takımı

Visual Studio'da bulunan araçları kullanarak, komut satırında C ve C++ uygulamaları oluşturabilirsiniz. Microsoft C++ (MSVC) derleyici araç takımı tek başına paket olarak indirilebilir ayrıca [Visual Studio indirmeleri](https://visualstudio.microsoft.com/downloads/) sayfası. Parçasıdır **Visual Studio derleme Araçları** paket. Yalnızca ihtiyacınız olan kadarını araçları indirmek seçebileceğiniz C++ geliştirme.

## <a name="how-to-use-the-command-line-tools"></a>Komut satırı araçlarını kullanma

Visual Studio Yükleyicisi'nde C++ iş yükleri birini seçtiğinizde, Visual Studio yüklendikten *platform araç takımını*. Tüm C platform araç takımı vardır ve C++ belirli bir Visual Studio sürümü için Araçlar. C araçlarda /C++ derleyicileri, linkers, birleştiricileri ve diğer yapı araçları ve eşleşen kitaplıkları. Komut satırında tüm bu araçları kullanabilirsiniz. Bunlar ayrıca dahili olarak Visual Studio IDE tarafından kullanılır. Ayrı x86 barındırılan ve x64 barındırılan derleyiciler vardır ve hedefleri x86, x 64, ARM ve ARM64 için kod oluşturmak için Araçlar. Belirli bir ana bilgisayar ve hedef yapı mimarisi için Araçlar'ın her bir kümesi, kendi dizininde depolanır.

Doğru çalışması için birkaç belirli ortam değişkenlerini ayarlamak için Araçlar gerektirir. Bu değişkenler yoluna ve ayarlamak için dosya, kitaplık dosyası ve SDK konumları araçlarda eklemek için kullanılır. Bu ortam değişkenlerini ayarlamak kolaylaştırmak için yükleyici özelleştirilmiş oluşturur *komut dosyaları*, toplu iş dosyaları, yükleme sırasında. Belirli bir ana bilgisayarı ve hedef yapı mimarisi, Windows SDK sürümünü ve platform araç kümesini ayarlamak için bu komut dosyalarını çalıştırabilirsiniz. Kolaylık olması için yükleyici başlangıç menünüzde kısayolları da oluşturur. Kısayollar şahit ana bilgisayarı ve hedef için bu komut dosyaları kullanarak Geliştirici komut istemi penceresi başlatın. Bu kısayollar, tüm gerekli ortam değişkenlerini ayarlayın ve kullanılmaya hazır olun.

Gerekli ortam değişkenlerini, yüklemenizi ve seçtiğiniz yapı mimarisi için özeldir. Bunlar ayrıca ürün güncelleştirmeleri veya yükseltmeleri tarafından değiştirilebilir. İşte bu ortam değişkenlerini kendiniz ayarlamak yerine yüklü bir komut istemi kısayoluna veya komut dosyası kullanmanızı öneririz. Daha fazla bilgi için [komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlamak](setting-the-path-and-environment-variables-for-command-line-builds.md).

Araç takımları, komut dosyaları ve yüklü kısayolları, bilgisayarı işlemcisini ve yükleme sırasında seçilen seçeneklere bağlıdır. Derlemede kod x86 ve x64 çapraz araçları ve x86 barındırılan Araçlar her zaman yüklenir. 64 bit Windows varsa x86 ve x64 kod derleme çapraz araçları ve x64 barındırılan araçlar da yüklenir. İsteğe bağlı seçerseniz C++ Evrensel Windows platformu Araçları'nı ve sonra da ARM ve ARM64 kod derleme x86 ve x64 araçları ayrıca yüklü. Diğer iş yükleri, ek araçlar yükleyebilir.

## <a name="developer_command_prompt_shortcuts"></a> Geliştirici komut istemi kısayolları

Komut istemi kısayolları, Başlat menüsü bir sürüme özgü Visual Studio klasöre yüklenir. Temel bir komut istemi kısayolları ve destekledikleri derleme mimarileri listesini şu şekildedir:

- **Geliştirici komut istemi** -32-bit, x86 yerel kod oluşturmak için 32-bit, yerel x86 araçları kullanacak şekilde ortamı ayarlar.
- **x86 yerel Araçlar komut istemi** -32-bit, x86 yerel kod oluşturmak için 32-bit, yerel x86 araçları kullanacak şekilde ortamı ayarlar.
- **x64 yerel Araçlar komut istemi** -64-bit, x64 yerel kod oluşturmak için 64-bit, yerel x64 araçları kullanacak şekilde ortamı ayarlar.
- **x86_x64 çapraz Araçları Komut İstemi** -64-bit, x64 yerel kod oluşturmak için 32-bit, yerel x86 araçları kullanacak şekilde ortamı ayarlar.
- **x64_x86 çapraz Araçları Komut İstemi** -32-bit, x86 yerel kod oluşturmak için 64-bit, yerel x64 araçları kullanacak şekilde ortamı ayarlar.

::: moniker range=">= vs-2019"

Başlangıç menüsünde klasörü ve kısayol adları yüklü Visual Studio sürümüne bağlı olarak farklılık gösterir. Ayarladıysanız, ayrıca yükleme bağımlı oldukları **takma ad**. Örneğin, Visual Studio 2019 yüklediğiniz ve bir takma ad, verdiğiniz varsayalım *son*. Geliştirici komut istemi kısayolunun adlı **VS 2019 (son sürüm) için geliştirici komut istemi**, adlı bir klasörde **Visual Studio 2019**.

::: moniker-end
::: moniker range="= vs-2017"

Başlangıç menüsünde klasörü ve kısayol adları yüklü Visual Studio sürümüne bağlı olarak farklılık gösterir. Ayarladıysanız, ayrıca yükleme bağımlı oldukları **takma ad**. Örneğin, Visual Studio 2017'yi yüklediğiniz ve bir takma ad, verdiğiniz varsayalım *son*. Geliştirici komut istemi kısayolunun adlı **(son sürüm) VS 2017 için geliştirici komut istemi**, adlı bir klasörde **Visual Studio 2017**.

::: moniker-end
::: moniker range="< vs-2017"

Başlangıç menüsünde klasörü ve kısayol adları yüklü Visual Studio sürümüne bağlı olarak farklılık gösterir. Örneğin, Visual Studio 2015 yüklü olduğunu varsayalım. Geliştirici komut istemi kısayolunun adlı **VS 2015 için geliştirici komut istemi**.

::: moniker-end

## <a name="developer_command_prompt"></a> Bir geliştirici komut istemi penceresi açmak için

1. Windows masaüstünde, açık **Başlat** menü ve örneğin, Visual Studio sürümünüz için klasörü açın, sonra kaydırma **Visual Studio 2019**.

1. Klasörde seçin **Geliştirici komut istemi** Visual Studio sürümünüz için. Bu kısayol, 32-bit, x86 yerel kod oluşturmak için 32-bit, x86 yerel Araçlar Varsayılan yapı mimarisi kullanan bir geliştirici komut istemi penceresi başlatılır. Varsayılan olmayan derleme mimarisi tercih ederseniz, yerel birini seçin veya çapraz Araçları komut istemleri, konak ve hedef mimari belirtmek için.

Daha hızlı bir şekilde bir geliştirici komut istemi açmak bilgi için girin *Geliştirici komut istemi* masaüstü arama kutusuna. İstediğiniz sonucu seçin.

## <a name="developer_command_file_locations"></a> Geliştirici komut dosyası konumları

Var olan bir komut istemi penceresinde yapı ortamı ayarlamak isterseniz yükleyici tarafından oluşturulan komut dosyalarını kullanabilirsiniz. Yeni bir komut istemi penceresinde ortamı ayarlamanızı öneririz. Daha sonra anahtar ortamları aynı komut penceresinde önerilmemektedir.

::: moniker range=">= vs-2019"

Komut dosyası, yüklediğiniz Visual Studio sürümü ve yükleme sırasında yapılan seçimlere bağlıdır. Visual Studio 2019 için tipik yükleme konumunu 64-bit sistemde yer \\Program dosyaları (x86)\\Microsoft Visual Studio\\2019\\*edition*. *Sürüm* Community, Professional, Enterprise, BuildTools veya temin ettiğiniz başka bir takma ad olabilir.

::: moniker-end
::: moniker range="= vs-2017"

Komut dosyası, yüklediğiniz Visual Studio sürümü ve yükleme sırasında yapılan seçimlere bağlıdır. Visual Studio 2017 için tipik yükleme konumunu 64-bit sistemde yer \\Program dosyaları (x86)\\Microsoft Visual Studio\\2017\\*edition*. *Sürüm* Community, Professional, Enterprise, BuildTools veya temin ettiğiniz başka bir takma ad olabilir.

::: moniker-end
::: moniker range="< vs-2017"

Komut dosyası, Visual Studio sürümü ve yükleme dizini bağlıdır. Visual Studio 2015 için tipik yükleme konumunu bulunduğu \\Program dosyaları (x86)\\Microsoft Visual Studio 14.0.

::: moniker-end

Birincil geliştirici komut istemi komut dosyası VsDevCmd.bat, Common7 içinde bulunan\\Tools alt dizininde. Parametre belirtilmezse, 32-bit x86 oluşturmak için yerel x86 Araçları'nı kullanacak şekilde ortamı ayarlar kod.

::: moniker range=">= vs-2017"

Daha fazla komut dosyaları, belirli yapı mimarilerine kullanılabilir. Kullanılabilir komut dosyaları, Visual Studio iş yükleri ve yüklediğiniz seçenekler bağlıdır. Visual Studio 2017 ve Visual Studio 2019'de, bunları VC bulabilirsiniz\\yardımcı\\alt yapı.

::: moniker-end
::: moniker range="< vs-2017"

Daha fazla komut dosyaları, belirli yapı mimarilerine kullanılabilir. Kullanılabilir komut dosyaları, Visual Studio iş yükleri ve yüklediğiniz seçenekler bağlıdır. Visual Studio 2015'te oldukları VC, VC yerleşime\\depo veya VC\\bin\\*mimarisi* alt dizinler, burada *mimarisi* yerel biri veya çapraz derleyici seçenekleri.

::: moniker-end

Bu komut dosyaları varsayılan parametreleri ayarlama ve belirtilen yapı mimarisi ortamı ayarlamak için VsDevCmd.bat çağırın. Tipik bir yükleme, bu komut dosyaları şunları içerebilir:

|Komut dosyası|Konak ve hedef mimariler|
|---|---|
|**vcvars32.bat**| 32-bit x86 oluşturmak için 32-bit x86 özgü araçları kullanın. kod.|
|**vcvars64.bat**| 64-bit x64 oluşturmak için 64-bit x64 özgü araçları kullanın. kod.|
|**vcvarsx86_amd64.bat**| 64-bit x64 oluşturmak için 32 bit yerel x86 çapraz araçları kullanmak kod.|
|**vcvarsamd64_x86.bat**| 32-bit x86 oluşturmak için 64-bit x64 yerel çapraz araçları kullanmak kod.|
|**vcvarsx86_arm.bat**| ARM Kodu derlemek için 32-bit x86 yerel çapraz araçları kullanın.|
|**vcvarsamd64_arm.bat**| ARM Kodu derlemek için 64-bit x64 yerel çapraz araçları kullanın.|
|**vcvarsall.bat**| Konak ve hedef mimariler, Windows SDK'sı ve platform seçenekleri belirtmek için parametreleri kullanın. Çağrıda tarafından desteklenen seçeneklerin bir listesi için bir **/help** parametresi.|

> [!CAUTION]
> Vcvarsall.bat dosyasının ve diğer Visual Studio komut dosyalarının bilgisayardan diğerine farklılık gösterebilir. Vcvarsall.bat dosyasının eksik veya hasarlı bir dosyayı başka bir bilgisayardan kullanarak değiştirmeyin. Eksik dosyayı değiştirmek için Visual Studio yükleyiciyi yeniden çalıştırın.
>
> Vcvarsall.bat dosya sürümü başka bir sürümü de değişir. Visual Studio'nun geçerli sürümü Visual Studio'nun önceki bir sürümü olan bir bilgisayarda yüklüyse, aynı komut istemi penceresinde farklı sürümlerine ait vcvarsall.bat veya başka bir Visual Studio komut dosyası çalıştırmayın.

## <a name="use-the-developer-tools-in-an-existing-command-window"></a>Var olan bir komut penceresinde geliştirici araçlarını kullanın

Var olan bir komut penceresinde belirli bir yapı mimarisi belirtmek için en basit yolu, vcvarsall.bat dosyası kullanmaktır. Vcvarsall.bat yerel 32 bit veya 64 bit derleme komut satırı yapılandırmak için ortam değişkenlerini ayarlamak için kullanın. Bağımsız değişkenler için x 64, ARM, x86 çapraz derleme belirtmenize olanak tanır veya ARM64 işlemci. Microsoft Store, Evrensel Windows platformu ve Windows Masaüstü platformları hedefleyebilir. Hatta, hangi Windows SDK'sını kullanmaya belirtin ve platform araç kümesi sürümünü seçin.

Bağımsız değişken olmadan kullanıldığında, vcvarsall.bat için 32-bit Windows Masaüstü hedefleri geçerli x86 yerel derleyici kullanmak için ortam değişkenlerini yapılandırır. Yerel veya çapraz derleyici araçları kullanmak için ortamı yapılandırmak için bağımsız değişken ekleyebilirsiniz. Vcvarsall.bat'ı, yüklü olmayan bir yapılandırması belirtirseniz bir hata iletisi görüntüler veya bilgisayarınızdaki kullanılabilir.

### <a name="vcvarsall-syntax"></a>Vcvarsall söz dizimi

> **vcvarsall.bat** [*architecture*] [*platform_type*] [*winsdk_version*] [ **-vcvars_ver=** _vcversion_]

*Mimarisi*<br/>
Bu isteğe bağlı bağımsız değişken kullanmak için ana bilgisayarı ve hedef mimari belirtir. Varsa *mimarisi* belirtilmediyse, varsayılan yapı ortamı kullanılır. Bu bağımsız değişkenler desteklenir:

|*Mimarisi*|Derleyici|Ana bilgisayar mimarisi|(Hedef) çıkış mimarisini oluşturun|
|----------------------------|--------------|----------------------------------|-------------------------------|
|**x86**|x86 32 bit yerel|x86, x64|x86|
|**x86\_amd64** veya **x86\_x64**|x86 x64 çapraz|x86, x64|X64|
|**x86_arm**|Platformlar arası x86 ARM|x86, x64|ARM|
|**x86_arm64**|Platformlar arası x86 ARM64|x86, x64|ARM64|
|**AMD64** veya **x64**|x64 64 bit yerel|X64|X64|
|**AMD64\_x86** veya **x64\_x86**|x64 x86 çapraz|X64|x86|
|**AMD64\_arm** veya **x64\_arm**|Platformlar arası x64 ARM|X64|ARM|
|**AMD64\_arm64** veya **x64\_arm64**|Platformlar arası x64 ARM64|X64|ARM64|

*platform_type*<br/>
Bu isteğe bağlı bağımsız değişkeni belirtmenize olanak tanır **depolamak** veya **uwp** platform türü. Varsayılan olarak, ortam, masaüstü veya konsol uygulamaları oluşturmak için ayarlanır.

*winsdk_version*<br/>
İsteğe bağlı olarak kullanmak için Windows SDK'sı sürümünü belirtir. Varsayılan olarak, en son yüklenen Windows SDK'sı kullanılır. Windows SDK sürümünü belirtmek için tam bir Windows 10 SDK'sı sayı gibi kullanabilirsiniz **10.0.10240.0**, veya belirtin **8.1** Windows 8.1 SDK'sını kullanma.

*vcversion*<br/>
İsteğe bağlı olarak kullanmak için Visual Studio derleyici araç setini belirtir. Varsayılan olarak, ortam, geçerli Visual Studio derleyici Araç Takımı'nı kullanmak için ayarlanır.

::: moniker range=">= vs-2019"

Kullanım **-vcvars_ver 14,2 = x .yyyyy** belirli bir Visual Studio 2019 derleyici araç takımı sürümünü belirtmek için.

Kullanım **-vcvars_ver 14.16 =** Visual Studio 2017 derleyici araç takımı en son sürümünü belirtmek için.

::: moniker-end
::: moniker range="= vs-2017"

Kullanım **-vcvars_ver 14.16 =** Visual Studio 2017 derleyici araç takımı en son sürümünü belirtmek için.

Kullanım **-vcvars_ver 14.1 = x .yyyyy** belirli bir Visual Studio 2017 derleyici araç takımı sürümünü belirtmek için.

::: moniker-end

Kullanım **-vcvars_ver 14.0 =** Visual Studio 2015 derleyici araç setini belirtmek için.

<a name="vcvarsall"></a>
#### <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a>Var olan bir komut istemi penceresinde yapı ortamı ayarlamak için

1. Komut isteminde için Visual Studio yükleme dizini değiştirmek için CD komutunu kullanın. Ardından, CD, özel yapılandırma komut dosyaları içeren alt dizinine değiştirmek için yeniden kullanın. Visual Studio 2019 ve Visual Studio 2017 için *VC\\yardımcı\\derleme* alt. Visual Studio 2015 kullanmaya *VC* alt.

1. Tercih edilen geliştirme ortamınız için komutu girin. Örneğin, ARM kodu UWP için en son Windows SDK'sını ve Visual Studio derleyici araç takımı, kullanarak bir 64-bit platformda derlemek için bu komut satırını kullanın:

   `vcvarsall.bat amd64_arm uwp`

## <a name="create-your-own-command-prompt-shortcut"></a>Kendi komut istemi kısayolunun oluşturma

::: moniker range=">= vs-2019"

Kullanılan komut hedefi görmek Geliştirici komut istemi kısayolunun için Özellikler iletişim kutusunu açın. Örneğin, hedef **x64 yerel Araçlar komut istemi için VS 2019** kısayoldur aşağıdakine benzer:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvars64.bat"`

::: moniker-end
::: moniker range="= vs-2017"

Kullanılan komut hedefi görmek Geliştirici komut istemi kısayolunun için Özellikler iletişim kutusunu açın. Örneğin, hedef **x64 VS 2017 için yerel Araçlar komut istemi** kısayoldur aşağıdakine benzer:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvars64.bat"`

::: moniker-end
::: moniker range="< vs-2017"

Kullanılan komut hedefi görmek Geliştirici komut istemi kısayolunun için Özellikler iletişim kutusunu açın. Örneğin, hedef **VS2015 x64 yerel Araçlar komut istemi** kısayoldur aşağıdakine benzer:

`%comspec% /k ""C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\vcvarsall.bat"" amd64`

::: moniker-end

Mimariye özgü toplu iş dosyaları kümesi *mimarisi* parametresi ve çağrı vcvarsall.bat. Bu toplu iş dosyaları için aynı seçenekleri için vcvarsall.bat geçecekse veya yalnızca vcvarsall.bat doğrudan çağırabilir geçirebilirsiniz. Kendi komut kısayol parametrelerini belirtmek için çift tırnak içinde komut sonuna ekleyin. Örneğin, ARM kodu UWP için en son Windows SDK'sını kullanarak bir 64-bit platformda derlemek için bir kısayol aşağıdadır. Önceki bir derleyici Araç Takımı'nı kullanmak için sürüm numarasını belirtin. Bu komut hedefi gibi kısayolu kullanın:

::: moniker range=">= vs-2019"

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvarsall.bat amd64_arm uwp -vcvars_ver=14.16"`

::: moniker-end
::: moniker range="= vs-2017"

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvarsall.bat amd64_arm uwp -vcvars_ver=14.0"`

::: moniker-end
::: moniker range="< vs-2017"

`%comspec% /k ""C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\vcvarsall.bat"" amd64 -vcvars_ver=12.0`

::: moniker-end

Yol, Visual Studio yükleme dizini gösterecek şekilde ayarlayın. Vcvarsall.bat dosyası belirli sürüm numaraları ilgili ek bilgiler bulunur.

## <a name="command-line-tools"></a>Komut satırı araçları

Bir C oluşturmak için /C++ bir komut isteminde, Visual Studio projesi bu komut satırı araçları sağlar:

[CL](reference/compiling-a-c-cpp-program.md)<br/>
Derleme ve bağlantı uygulamaları, kitaplıkları ve DLL'leri kaynak kodu dosyaları için derleyici (cl.exe) kullanın.

[Bağlantı](reference/linking.md)<br/>
Uygulamalar ve DLL'ler derlenmiş nesne dosyaları ve kitaplıkları bağlamak için bağlayıcı (link.exe) kullanın.

[MSBuild](msbuild-visual-cpp.md)<br/>
MSBuild (msbuild.exe) ve bir proje dosyası (.vcxproj), bir derleme yapılandırmak ve araç takımı dolaylı olarak çağırmak için kullanın. Çalışan eşdeğerdir **derleme** proje veya **Çözümü Derle** Visual Studio IDE'de komutu. MSBuild komut satırından çalıştırma, Gelişmiş bir senaryodur ve değil, yaygın olarak önerilir.

[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)<br/>
Kullanın (devenv.exe) DEVENV komut satırı anahtarıyla gibi birleştirilmiş **/Build** veya **/Clean** yürütmek için belirli komutları Visual Studio IDE görüntülemeden oluşturun. Visual Studio MSBuild karmaşıklığını işlemek olduğun genel olarak, DEVENV MSBuild kullanarak üzerinden doğrudan, tercih edilir.

[NMAKE](reference/nmake-reference.md)<br/>
NMAKE (nmake.exe) üzerinde Windows üzerinde geleneksel bir derleme görevleri dosyası tabanlı C++ projeleri derlemek için kullanın.

Komut satırında oluşturduğunuzda, anında yardım için F1 komut kullanılamaz. Bunun yerine, uyarılar, hatalar ve iletiler hakkında bilgi almak için bir arama motoru kullanın veya çevrimdışı Yardım dosyalarını kullanabilirsiniz. Aramada kullanılacak [docs.microsoft.com](https://docs.microsoft.com/cpp/), sayfanın en üstündeki arama kutusunu kullanın.

## <a name="in-this-section"></a>Bu Bölümde

Bu makaleler, komut satırında uygulamalar oluşturmak nasıl gösterir ve komut satırı derleme ortamı özelleştirmek nasıl açıklar. Bazı 64-bit araç takımları kullanacak ve x86, x 64, ARM, hedef işlemini gösteren ve ARM64 platformlar. Bunlar ayrıca, MSBuild ve NMAKE derleme komut satırı araçlarının kullanımı açıklanmaktadır.

[İzlenecek yol: Komut Satırında Yerel C++ Programı Derleme](walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>
Oluşturma ve derleme gösteren bir örnek sağlar bir C++ komut satırındaki program.

[İzlenecek yol: Komut satırında C programı derleme](walkthrough-compile-a-c-program-on-the-command-line.md)<br/>
C programlama dilinde yazılmış bir program derleyin açıklar.

[İzlenecek yol: Komut Satırında C++/CLI Programı Derleme](walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)<br/>
Oluşturma ve derleme işlemlerini açıklayan bir C++/CLI program, .NET Framework'ü kullanır.

[İzlenecek yol: Komut Satırında C++/CX Programı Derleme](walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)<br/>
Oluşturma ve derleme işlemlerini açıklayan bir C++Windows çalışma zamanı kullanan /CX programı.

[Komut Satırı Derlemeleri için Yolu ve Ortam Değişkenlerini Ayarlama](setting-the-path-and-environment-variables-for-command-line-builds.md)<br/>
Hedef x86, x64, ARM, 32 bit veya 64-bit bir araç kullanmak için ortam değişkenlerini ayarlama ve ARM64 platformlar.

[NMAKE Başvurusu](reference/nmake-reference.md)<br/>
Microsoft Program Bakımı yardımcı programı (NMAKE. açıklayan makalelerin bağlantıları sağlar EXE).

[MSBuild komut satırında - C++](msbuild-visual-cpp.md)<br/>
Komut satırında msbuild.exe kullanmayı açıklayan makalelerin bağlantıları sağlar.

## <a name="related-sections"></a>İlgili Bölümler

[/MD, /MT, /LD (Çalışma Zamanı Kitaplığını Kullan)](reference/md-mt-ld-use-run-time-library.md)<br/>
Bu derleyici seçeneklerinin bir hata ayıklama veya sürüm çalışma zamanı kitaplığı kullanmayı açıklar.

[C/C++ Derleyici Seçenekleri](reference/compiler-options.md)<br/>
C ve C++ derleyici seçenekleri ve CL.exe açıklayan makalelerin bağlantıları sağlar.

[MSVC Bağlayıcı Seçenekleri](reference/linker-options.md)<br/>
Bağlayıcı seçenekleri ve LINK.exe açıklayan makalelerin bağlantıları sağlar.

[Ek MSVC derleme araçları](reference/c-cpp-build-tools.md)<br/>
C/C++ bağlantılar derleme Visual Studio'ya dahil olan araçları sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Projeler ve derleme sistemleri](projects-and-build-systems-cpp.md)
