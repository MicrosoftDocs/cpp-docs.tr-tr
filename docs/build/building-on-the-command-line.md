---
title: Komut satırından - Visual Studio MSVC araç takımı kullanın
description: Visual Studio IDE dışında komut satırından Microsoft C++ Derleyici araç zincirini (MSVC) kullanın.
ms.custom: conceptual
ms.date: 05/16/2019
helpviewer_keywords:
- command-line builds [C++]
- compiling source code [C++], command line
- builds [C++], command-line
- command line [C++], building from
- command line [C++], compilers
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
ms.openlocfilehash: 97626455ace0d3ad47b9011594e82c144d7ea27d
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837121"
---
# <a name="use-the-msvc-toolset-from-the-command-line"></a>Komut satırından MSVC araç takımı kullanın

Visual Studio'da bulunan araçları kullanarak, komut satırında C ve C++ uygulamaları oluşturabilirsiniz. Tek başına paket olarak derleyici araç takımı indirebilirsiniz [Visual Studio indirmeleri](https://visualstudio.microsoft.com/downloads/) sayfası. Parçası olan **Visual Studio derleme Araçları** paketini; yalnızca için ihtiyacınız olan araçları indirin seçtiğiniz C++ geliştirme.

## <a name="how-to-use-the-command-line-tools"></a>Komut satırı araçlarını kullanma

Visual Studio Yükleyicisi'nde C++ iş yükleri birini seçtiğinizde, Visual Studio yüklendikten *platform araç takımını*. Bir platform araç takımı C/C++ Derleyicileri, linkers, birleştiricileri ve diğer oluşturma araçlarının yanı sıra eşleşen kitaplıkları dahil olmak üzere belirli bir Visual Studio sürümü C ve C++ araçlarına sahiptir. Tüm bu araçlar komut satırında kullanabilir ve ayrıca Visual Studio IDE tarafından dahili olarak kullanılırlar. Ayrı x86 barındırılan ve x64 barındırılan derleyiciler ve x86, x 64, ARM için kod oluşturmak için Araçlar ve ARM64 hedefleri vardır. Belirli bir ana bilgisayar ve hedef yapı mimarisi için Araçlar'ın her bir kümesi, kendi dizininde depolanır.

Yüklü bir derleyici araç takımları, bilgisayarı işlemcisini ve yükleme sırasında seçilen seçeneklere bağlıdır. En az 32-bit x86-native kodu derleyin ve 64-bit x64 yerel kod yapı araçları çapraz 32-bit x86 barındırılan Araçlar yüklenir. 64 bit Windows varsa, 64-bit yerel kod derleme ve 32 bit yerel kod yapı araçları çapraz 64-bit x64 barındırılan araçları da yüklenir. İsteğe bağlı C++ Evrensel Windows platformu araçları yüklemeyi seçerseniz, ARM kodu derleyin 32-bit ve 64-bit yerel araçlar da yüklenir. Diğer iş yükleri, ek araçlar yükleyebilir.

## <a name="environment-variables-and-developer-command-prompts"></a>Ortam değişkenlerini ve geliştirici komut istemleri

Doğru çalışması için birkaç belirli ortam değişkenlerini ayarlamak için Araçlar gerektirir. Bunlar yoluna eklenecek ve ayarlamak için kullanılan dosya, kitaplık dosyası ve SDK konumları içerir. Bu ortam değişkenlerini ayarlamak kolaylaştırmak için yükleyici özelleştirilmiş oluşturur *komut dosyaları*, toplu iş dosyaları, yükleme sırasında. Bu komut dosyalarından birini belirli bir ana bilgisayarı ve hedef yapı mimarisi, Windows SDK sürümü, hedef platform ve platform araç kümesini ayarlamak için bir komut istemi penceresinde çalıştırabilirsiniz. Kolaylık olması için yükleyici kısayolları tüm gerekli ortam değişkenlerini ayarlayın ve kullanıma hazır olacak şekilde, bu komut dosyaları kullanarak Geliştirici komut istemi windows Başlat, Başlat menüsünde de oluşturur.

Gerekli ortam değişkenlerini, yüklemenizi ve seçin ve ürün güncelleştirmeleri veya yükseltmeleri tarafından değiştirilebilir yapı mimarisi için özeldir. Bu nedenle, ortam değişkenleri Windows kendiniz ayarlamak yerine yüklü bir komut istemi kısayolları ya da komut dosyaları birini kullanmanız önerilir. Daha fazla bilgi için [komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlamak](setting-the-path-and-environment-variables-for-command-line-builds.md).

## <a name="developer_command_prompt_shortcuts"></a> Geliştirici komut istemi kısayolları

Komut istemi kısayolları, Başlat menüsü bir sürüme özgü Visual Studio klasöre yüklenir. Temel bir komut istemi kısayolları ve destekledikleri derleme mimarileri listesini şu şekildedir:

- **Geliştirici komut istemi** -32-bit, x86 yerel kod oluşturmak için 32-bit, yerel x86 araçları kullanacak şekilde ortamı ayarlar.
- **x86 yerel Araçlar komut istemi** -32-bit, x86 yerel kod oluşturmak için 32-bit, yerel x86 araçları kullanacak şekilde ortamı ayarlar.
- **x64 yerel Araçlar komut istemi** -64-bit, x64 yerel kod oluşturmak için 64-bit, yerel x64 araçları kullanacak şekilde ortamı ayarlar.
- **x86_x64 çapraz Araçları Komut İstemi** -64-bit, x64 yerel kod oluşturmak için 32-bit, yerel x86 araçları kullanacak şekilde ortamı ayarlar.
- **x64_x86 çapraz Araçları Komut İstemi** -32-bit, x86 yerel kod oluşturmak için 64-bit, yerel x64 araçları kullanacak şekilde ortamı ayarlar.

Ayarladıysanız gerçek başlangıç menüsünde klasörü ve kısayol adları, yüklediğiniz Visual Studio sürümü ve yükleme takma adı bağlı olarak farklılık gösterir. Örneğin, Visual Studio yüklü 2019 varsa ve sizin için göre bir yükleme Takmaad *Önizleme*, geliştirici komut istemi kısayolunun adlı **VS 2019 için geliştirici komut istemi**, bir adlı bir klasör **Visual Studio 2019**.

## <a name="developer_command_prompt"></a> Bir geliştirici komut istemi penceresi açmak için

1. Windows masaüstünde, açık **Başlat** menü ve örneğin, Visual Studio sürümünüz için klasörü açın, sonra kaydırma **Visual Studio 2019**. Visual Studio bazı eski sürümlerinde adlı alt klasörde kısayollarıdır **Visual Studio Araçları**.

1. Klasörde seçin **Geliştirici komut istemi** Visual Studio sürümünüz için. Bu kısayol, 32-bit, x86 yerel kod oluşturmak için 32-bit, x86 yerel Araçlar Varsayılan yapı mimarisi kullanan bir geliştirici komut istemi penceresi başlatılır. Varsayılan olmayan derleme mimarisi tercih ederseniz, yerel birini seçin veya çapraz Araçları komut istemleri, konak ve hedef mimari belirtmek için.

Bir geliştirici komut istemi penceresi açmak için daha hızlı bir şekilde girmektir *Geliştirici komut istemi* masaüstü arama kutusuna, istenen sonucu seçin.

## <a name="developer_command_file_locations"></a> Geliştirici komut dosyası konumları

Var olan bir komut istemi penceresinde yapı mimarisi ortamı ayarlamak isterseniz, bu komut dosyalarından birine (toplu iş dosyaları) yükleyici tarafından oluşturulan gerekli ortam ayarlamak için kullanabilirsiniz. Yalnızca önerilir bunun yeni bir komut istemi penceresinde ve, daha sonra anahtar ortamları aynı komut penceresinde önermiyoruz. Bu dosyaların konumunu, yüklediğiniz Visual Studio sürümünü ve konumunu ve yükleme sırasında yapılan adlandırma seçenekleri bağlıdır. Visual Studio 2019 için normal yükleme bir 64 bit bilgisayarda \Program dosyaları (x86) \Microsoft Visual Studio\2019 içinde konumdur\*edition * burada *edition* Community, Professional, Enterprise, olabilir BuildTools veya belirttiğiniz başka bir ad. Visual Studio 2017 konumu benzerdir. Visual Studio 2015 için \Program dosyaları (x86) \Microsoft Visual Studio 14.0 Normal Yükleme konumdur.

Birincil geliştirici komut istemi komut dosyası VsDevCmd.bat, Common7\Tools alt yükleme dizininde bulunur. Parametre belirtilmezse, bu ortam ayarlar ve 32-bit x86 oluşturmak için 32-bit x86 yerel araçlarını kullanmayı mimarisi konak ve hedef derleme kodu.

İşlemci mimariniz ve Visual Studio iş yükleri, yüklemiş olduğunuz seçeneklerle bağlı olarak belirli bir derleme mimarileri ayarlamak ek komut dosyaları bulunmaktadır. Visual Studio 2017 ve Visual Studio 2019'de, bu Visual Studio yükleme dizini VC\Auxiliary\Build alt dizininde yer alır. Visual Studio 2015'te bu VC, VC\bin veya VC\bin bulunan\\*mimarileri* yükleme dizininin alt dizinleri burada *mimarileri* yerel biri veya çapraz derleyici seçenekleri. Bu komut dosyaları varsayılan parametreleri ayarlama ve belirtilen yapı mimarisi ortamı ayarlamak için VsDevCmd.bat çağırın. Tipik bir yükleme, bu komut dosyaları şunları içerebilir:

|Komut dosyası|Konak ve hedef mimariler|
|---|---|
|**vcvars32.bat**| 32-bit x86 oluşturmak için 32-bit x86 özgü araçları kullanın. kod.|
|**vcvars64.bat**| 64-bit x64 oluşturmak için 64-bit x64 özgü araçları kullanın. kod.|
|**vcvarsx86_amd64.bat**| 64-bit x64 oluşturmak için 32 bit yerel x86 çapraz araçları kullanmak kod.|
|**vcvarsamd64_x86.bat**| 32-bit x86 oluşturmak için 64-bit x64 yerel çapraz araçları kullanmak kod.|
|**vcvarsx86_arm.bat**| ARM Kodu derlemek için 32-bit x86 yerel çapraz araçları kullanın.|
|**vcvarsamd64_arm.bat**| ARM Kodu derlemek için 64-bit x64 yerel çapraz araçları kullanın.|
|**vcvarsall.bat**| Konak ve hedef mimariler, hem de SDK'sı ve platform seçeneklerini belirtmek için parametreleri kullanın. Çağrıda tarafından desteklenen seçeneklerin bir listesi için bir **/help** parametresi.|

> [!CAUTION]
> Vcvarsall.bat dosyasının ve diğer Visual Studio komut dosyalarının bilgisayardan diğerine farklılık gösterebilir. Vcvarsall.bat dosyasının eksik veya hasarlı bir dosyayı başka bir bilgisayardan kullanarak değiştirmeyin. Eksik dosyayı değiştirmek için Visual Studio yükleyiciyi yeniden çalıştırın.
>
> Vcvarsall.bat dosya sürümü başka bir sürümü de değişir. Visual Studio'nun geçerli sürümü Visual Studio'nun önceki bir sürümü olan bir bilgisayarda yüklüyse, aynı komut istemi penceresinde farklı sürümlerine ait vcvarsall.bat veya başka bir Visual Studio komut dosyası çalıştırmayın.

## <a name="use-the-developer-tools-in-an-existing-command-window"></a>Var olan bir komut penceresinde geliştirici araçlarını kullanın

Var olan bir komut penceresinde belirli bir yapı mimarisi belirtmek için en basit yolu, vcvarsall.bat dosyası kullanmaktır. Yerel 32 bit veya 64 bit derleme veya çapraz derleme x86 x64 ya da ARM işlemcileri için komut satırından yapılandırmak için ortam değişkenlerini ayarlamak için vcvarsall.bat kullanabilirsiniz; Microsoft Store, Evrensel Windows platformu ve Windows Masaüstü platformları hedeflemek için; Hangi Windows SDK'sını kullanmaya belirtmek için; ve platform araç kümesi sürümünü belirtin. Hiçbir değişken sağlanmazsa, vcvarsall.bat için x86 geçerli 32 bit yerel derleyici kullanmak için ortam değişkenlerini yapılandırır. Windows Masaüstü hedefler. Ancak, yerel veya çapraz derleyici araçları yapılandırmak için kullanabilirsiniz. Yüklü değil ya da, bilgisayar mimarisi yapınızda kullanılabilir olmayan bir derleyici yapılandırması belirtirseniz, bir hata iletisi görüntülenir.

### <a name="vcvarsall-syntax"></a>Vcvarsall söz dizimi

> **vcvarsall.bat** [*architecture*] [*platform_type*] [*winsdk_version*] [**-vcvars_ver=**_vcversion_]

*Mimarisi*<br/>
Bu isteğe bağlı bağımsız değişken kullanmak için ana bilgisayarı ve hedef mimari belirtir. Varsa *mimarisi* belirtilmezse, varsayılan yapı ortamı kullanılır. Bu bağımsız değişkenler desteklenir:

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
İsteğe bağlı olarak kullanmak için Visual Studio derleyici araç setini belirtir. Varsayılan olarak, ortam, geçerli Visual Studio derleyici Araç Takımı'nı kullanmak için ayarlanır. Kullanım **-vcvars_ver 14.0 =** Visual Studio 2015 derleyici araç setini belirtmek için veya **-vcvars_ver 15.0 =** Visual Studio 2017 derleyici araç setini belirtmek için.

<a name="vcvarsall"></a>
#### <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a>Var olan bir komut istemi penceresinde yapı ortamı ayarlamak için

1. Komut isteminde için Visual Studio yükleme dizini değiştirmek için CD komutunu kullanın. Ardından, CD, özel yapılandırma komut dosyaları içeren alt dizinine değiştirmek için yeniden kullanın. Visual Studio 2017 ve Visual Studio 2019 için VC\Auxiliary\Build alt budur. Visual Studio 2015 için VC alt kullanın.

1. Tercih edilen geliştirme ortamınız için komutu girin. Örneğin, bir 64-bit platformda UWP için en son Windows SDK'sını ve Visual Studio 2019 derleyici araç setini kullanarak ARM kodu oluşturmak için bu komut satırını kullanın:

   `vcvarsall.bat amd64_arm uwp`

## <a name="create-your-own-command-prompt-shortcut"></a>Kendi komut istemi kısayolunun oluşturma

Var olan Geliştirici komut istemi kısayolları biri için Özellikler iletişim kutusunu açın, kullanılan komut hedefi görebilirsiniz. Örneğin, hedef **x64 yerel Araçlar komut istemi için VS 2019** kısayoldur aşağıdakine benzer:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvars64.bat"`

Mimariye özgü toplu iş dosyaları kümesi *mimarisi* parametresi ve çağrı vcvarsall.bat. Bu toplu iş dosyaları için aynı ek seçenekler için vcvarsall.bat geçecekse veya yalnızca vcvarsall.bat doğrudan çağırabilir geçirebilirsiniz. Kendi komut kısayol parametrelerini belirtmek için çift tırnak içinde komut sonuna ekleyin. Örneğin, bir 64-bit platformda UWP için en son Windows SDK'sı ve geçerli sürümden daha eski bir derleyici araç setini kullanarak ARM Kodu derlemek için bir kısayol ayarlamak için sürüm numarasını belirtmeniz gerekir. Bu komut hedefi gibi kısayolu kullanın:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvarsall.bat amd64_arm uwp -vcvars_ver=15.0"`

Yol, Visual Studio yükleme dizini yansıtacak şekilde ayarlamanız gerekir. Vcvarsall.bat dosyası belirli sürüm numaraları ilgili ek bilgiler bulunur.

## <a name="command-line-tools"></a>Komut satırı araçları

Komut satırında C/C++ projesi oluşturmak için Visual Studio bu komut satırı araçları sağlar:

[CL](reference/compiling-a-c-cpp-program.md)<br/>
Derleme ve bağlantı uygulamaları, kitaplıkları ve DLL'leri kaynak kodu dosyaları için derleyici (cl.exe) kullanın.

[Bağlantı](reference/linking.md)<br/>
Uygulamalar ve DLL'ler derlenmiş nesne dosyaları ve kitaplıkları bağlamak için bağlayıcı (link.exe) kullanın.

[MSBuild](msbuild-visual-cpp.md)<br/>
MSBuild (msbuild.exe) ve bir proje dosyası (.vcxproj), bir derleme yapılandırmak ve araç takımı dolaylı olarak çağırmak için kullanın. Bu çalıştırma için eşdeğerdir **derleme** proje veya **Çözümü Derle** Visual Studio IDE'de komutu. MSBuild komut satırından çalıştırma, Gelişmiş bir senaryodur ve genel olarak önerilmez.

[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)<br/>
Kullanın (devenv.exe) DEVENV komut satırı anahtarıyla birlikte — Örneğin, **/Build** veya **/Clean**— gerçekleştirmek için belirli komutları Visual Studio IDE görüntülemeden oluşturun. Genel olarak bu MSBuild izin verebilir çünkü Visual Studio işlemek doğrudan MSBuild karmaşıklığını yerine tercih edilir.

[NMAKE](reference/nmake-reference.md)<br/>
NMAKE (nmake.exe) üzerinde Windows üzerinde geleneksel bir derleme görevleri dosyası tabanlı C++ projeleri derlemek için kullanın.

Komut satırında oluşturduğunuzda F1 komut anında yardım için kullanılamaz. Bunun yerine, uyarılar, hatalar ve iletiler hakkında bilgi almak için bir arama motoru kullanın veya çevrimdışı Yardım dosyalarını kullanabilirsiniz. Aramada kullanılacak [docs.microsoft.com](https://docs.microsoft.com/cpp/), sayfanın üst kısmındaki arama kutusuna arama dizenizi girin.

## <a name="in-this-section"></a>Bu Bölümde

Belgelerin bu bölümdeki makaleleri komut satırında uygulamalar oluşturmak için komut satırı derleme nasıl kazandırabileceğinizi 64-bit araç takımları ve hedef x86, x64, kullanın ve ARM platformları için komut satırı derleme ortamı özelleştirmek nasıl açıklar nasıl Göster MSBuild ve NMAKE araçları.

[İzlenecek yol: Komut Satırında Yerel C++ Programı Derleme](walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>
Oluşturma ve basit bir C++ programını komut satırında derleme gösteren bir örnek sağlar.

[İzlenecek yol: Komut satırında C programı derleme](walkthrough-compile-a-c-program-on-the-command-line.md)<br/>
C programlama dilinde yazılmış bir program derleyin açıklar.

[İzlenecek yol: Komut Satırında C++/CLI Programı Derleme](walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)<br/>
Oluşturma ve derleme işlemlerini açıklayan bir C++/CLI program, .NET Framework'ü kullanır.

[İzlenecek yol: Komut Satırında C++/CX Programı Derleme](walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)<br/>
Oluşturma ve derleme işlemlerini açıklayan bir C++Windows çalışma zamanı kullanan /CX programı.

[Komut Satırı Derlemeleri için Yolu ve Ortam Değişkenlerini Ayarlama](setting-the-path-and-environment-variables-for-command-line-builds.md)<br/>
Gerekli ortam değişkenlerini hedefleyen x86, x64, komut satırı derlemeleri için ayarlayabilir ve platformları 32 bit veya 64-bit araç setini kullanarak ARM sahip bir komut istemi penceresi başlangıç açıklar.

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