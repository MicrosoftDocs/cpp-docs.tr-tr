---
title: Komut satırında C/C++ kod derleme | Microsoft Docs
ms.custom: ''
ms.date: 03/29/2018
ms.technology:
- cpp-tools
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- command-line builds [C++]
- compiling source code [C++], command line
- builds [C++], command-line
- command line [C++], building from
- command line [C++], compilers
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fc4ec1034d4d77542df4a4241ad3ba5c087602ae
ms.sourcegitcommit: 78e5e5cdbafd29e2a6ccf68d4cce215136952907
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/03/2018
---
# <a name="build-cc-code-on-the-command-line"></a>Komut satırında C/C++ kodu derleme

Visual Studio'da bulunan araçları kullanarak komut satırında C ve C++ uygulamaları oluşturabilirsiniz.

## <a name="how-to-get-the-command-line-tools"></a>Komut satırı araçları alma

Visual Studio yükleyicisinde C++ iş yükleri birini seçtiğinizde, Visual Studio yükler *platform araç takımı*. Platform araç takımı C/C++ Derleyicileri, linkers, birleştiricileri ve diğer derleme araçları yanı sıra eşleşen kitaplıkları da dahil olmak üzere belirli bir Visual Studio sürümü için C ve C++ araçları vardır. Bu araçların komut satırında kullanabilirsiniz ve de Visual Studio IDE tarafından dahili olarak kullanılır. Ayrı x86 barındırılan ve x64 barındırılan derleyicileri ve x 64, x86 ARM için kod oluşturmak için Araçlar ve ARM64 hedefleri vardır. Belirli bir ana bilgisayar ve hedef yapı mimarisi için araçları her kümesinin, kendi dizininde depolanır.

Doğru çalışması için ayarlanacak birkaç belirli ortam değişkenleri araçları gerektirir. Bu yolu eklemek ve ayarlamak için kullanılan dosya, kitaplık dosyasını ve SDK konumları içerir. Bu ortam değişkenlerini ayarlama kolaylaştırmak için yükleyici özelleştirilmiş oluşturur *komut dosyaları*, veya toplu iş dosyaları, yükleme sırasında. Bu komut dosyaları biri belirli bir ana bilgisayarı ve hedef yapı mimarisi, Windows SDK sürümü, hedef platformu ve platform araç takımı ayarlamak için bir komut istemi penceresinde çalıştırabilirsiniz. Kolaylık olması için yükleyici da kısayollar Başlat menüde oluşturur (veya başlangıç sayfasında Windows 8.x) yönelik başlangıç Geliştirici komut istemi penceresi tüm gerekli ortam değişkenlerini ayarlayın ve hazır kullanın; Bu nedenle bu komut dosyaları kullanarak.

Gerekli ortam değişkenleri, yüklemenizi ve seçin ve ürün güncelleştirmeleri veya yükseltmeleri tarafından değiştirilebilir yapı mimarisi için özeldir. Bu nedenle, ortam değişkenleri Windows kendiniz ayarlamak yerine yüklü bir komut istemi kısayolları veya komut dosyaları birini kullanmanız önerilir. Daha fazla bilgi için bkz: [komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlama](../build/setting-the-path-and-environment-variables-for-command-line-builds.md).

Komut satırı toolsets, komut dosyaları ve yüklü olan bir komut istemi kısayolları bilgisayar işlemcinizin ve yükleme sırasında seçilen seçeneklere bağlıdır. En az 32 bit x86 yerel kod yapı ve 64-bit x64 yerel kodu derleme araçları çapraz 32-bit x86 barındırılan Araçları yüklenir. 64 bit Windows varsa, 64-bit yerel kod yapı ve 32-bit yerel kodu derleme araçları çapraz 64-bit x64 barındırılan araçları da yüklenir. İsteğe bağlı C++ Evrensel Windows platformu Araçları'nı yükleme seçerseniz, ARM kod derleme 32-bit ve 64-bit yerel araçlarını da yüklenir. Diğer iş yükleri, ek araçlar yükleyebilir.

## <a name="developer-command-prompt-shortcuts"></a>Geliştirici komut istemi kısayolları

Komut istemi kısayolları Başlat menüsü bir sürüme özgü Visual Studio klasöre yüklenir. Temel bir komut istemi kısayolları ve destekledikleri yapı mimarileri listesi aşağıdadır:

- **Geliştirici komut istemi** -32-bit, x86 yerel kodu derleme için 32-bit, x86 yerel araçlarını kullanma ortamını ayarlar.
- **x86 yerel Araçları Komut İstemi** -32-bit, x86 yerel kodu derleme için 32-bit, x86 yerel araçlarını kullanma ortamını ayarlar.
- **x64 yerel Araçları Komut İstemi** -64-bit, x64 yerel kodu derleme için 64-bit, x64 yerel araçlarını kullanma ortamını ayarlar.
- **x86_x64 arası Araçları Komut İstemi** -64-bit, x64 yerel kodu derleme için 32-bit, x86 yerel araçlarını kullanma ortamını ayarlar.
- **x64_x86 arası Araçları Komut İstemi** -32-bit, x86 yerel kodu derleme için 64-bit, x64 yerel araçlarını kullanma ortamını ayarlar.

Bir ayarlarsanız gerçek başlangıç menüsünde klasörü ve kısayol adları yüklediğiniz Visual Studio sürümü ve yükleme takma ad bağlı olarak farklılık gösterir. Visual Studio yüklü 2017 varsa örnek ve sizin için göre bir yükleme Takmaad *Önizleme*, geliştirici komut istemi kısayoluna adlı **VS 2017 (Önizleme)içingeliştiricikomutistemi**, adlı bir klasörde **Visual Studio 2017**.

Uygulamasını yüklediyseniz [derleme araçları Visual Studio 2017 için](https://go.microsoft.com/fwlink/p/?linkid=840931) (Ayrıca içeren Visual Studio 2015 güncelleştirme 3'ü derleyici araç takımı), yalnızca mimariye özel yerel veya çapraz araçları Geliştirici komut istemi seçenekleri yüklenir ve genel **Geliştirici komut istemi** kısayol.

<a name="developer_command_prompt"></a>
### <a name="to-open-a-developer-command-prompt-window"></a>Bir geliştirici komut istemi penceresi açmak için

1. Windows masaüstünde, açık **Başlat** menü ve bulmak ve örneğin, Visual Studio sürümünüze klasörü açmak için kaydırma yapın **Visual Studio 2017**. Visual Studio bazı eski sürümlerinde kısayolları adlı alt klasörde olan **Visual Studio Araçları**.

1. Klasöründe seçin **Geliştirici komut istemi** Visual Studio sürümünüze. Bu kısayol 32-bit, x86 yerel kodu oluşturmak için 32-bit, x86 yerel Araçlar Varsayılan yapı mimarisi kullanan bir geliştirici komut istemi penceresi başlatır. Varsayılan olmayan yapı mimarisi tercih ederseniz, yerel birini seçin veya ana bilgisayar ve hedef mimarisi belirtmek için komut istemleri arası araçları.

Bir geliştirici komut istemi penceresi açmak için daha hızlı bir şekilde girmektir *Geliştirici komut istemi* masaüstü arama kutusuna, ardından istenen sonucu seçin.

## <a name="developer-command-files-and-locations"></a>Geliştirici komut dosyaları ve konumları

Varolan bir komut istemi penceresinde yapı mimarisi ortamını ayarlamak tercih ederseniz, komut dosyalarından birini (toplu iş dosyaları) yükleyici tarafından oluşturulan gerekli ortam ayarlamak için kullanabilirsiniz. Yalnızca öneririz yeni bir komut istemi penceresi Bunu yapıp, aynı komut penceresinde sonraki anahtar ortamları önermiyoruz. Bu dosyaların konumunu yüklediğiniz Visual Studio sürümünü ve konumunu ve yükleme sırasında yapılan adlandırma seçeneği bağlıdır. Visual Studio 2017 için tipik yükleme 64-bit bilgisayarda \Program dosyaları (x86) \Microsoft Visual Studio\2017 konumdur\\*edition*, burada *edition* topluluk olabilir Professional, Enterprise, BuildTools veya başka bir ad sağladığınız. Visual Studio 2015 için tipik yükleme konumu \Program Files (x86) \Microsoft Visual Studio 14.0 şeklindedir.

Birincil geliştirici komut istemi komut dosyası, VsDevCmd.bat, Common7\Tools alt yükleme dizininde bulunur. Parametre belirtilmezse, bu ortamını ayarlar ve ana bilgisayar ve hedef 32-bit x86 oluşturmak için 32-bit x86 yerel araçlarını kullanma mimarisi derlediğinizde kod.

Ek komut dosyaları, işlemci mimarisi ve Visual Studio iş yükleri ve seçenekler yüklediğiniz bağlı olarak belirli yapı mimarileri ayarlamak kullanılabilir. Visual Studio 2017 ' Bu VC\Auxiliary\Build alt Visual Studio yükleme dizininde bulunur. Visual Studio 2015'te bu VC, VC\bin veya VC\bin bulunan\\*mimarileri* yükleme dizininin alt dizinleri nerede *mimarileri* yerel biri veya çapraz derleyici seçenekleri. Bu komut dosyaları, varsayılan parametreleri ayarlama ve belirtilen yapı mimarisi ortamını ayarlamak için VsDevCmd.bat çağırın. Tipik bir yüklemede, bu komut dosyaları içerebilir:

|Komut dosyası|Ana bilgisayar ve hedef mimarileri|
|---|---|
|**vcvars32.bat**| 32-bit x86 oluşturmak için 32-bit x86 yerel araçlarını kullanın kodu.|
|**vcvars64.bat**| 64-bit x64 oluşturmak için 64-bit x64 yerel araçları kullanmak kodu.|
|**vcvarsx86_amd64.bat**| 64-bit x64 oluşturmak için 32-bit x86 yerel çapraz araçlarını kullanın kodu.|
|**vcvarsamd64_x86.bat**| 32-bit x86 oluşturmak için 64-bit x64 yerel çapraz araçları kullanın kodu.|
|**vcvarsx86_arm.bat**| ARM kodu oluşturmak için 32-bit x86 yerel çapraz araçlarını kullanın.|
|**vcvarsamd64_arm.bat**| ARM kodu oluşturmak için 64-bit x64 yerel çapraz araçlarını kullanın.|
|**vcvarsall.bat**| Parametreler ana bilgisayar ve hedef mimarilerinin yanı SDK ve platform seçeneklerini belirtmek için kullanın. Desteklenen seçeneklerinin listesi için çağrıda bir **/Yardım** parametresi.|

> [!CAUTION]
> Vcvarsall.bat dosya ve diğer Visual Studio komut dosyaları bilgisayardan diğerine farklılık gösterebilir. Eksik veya zarar görmüş vcvarsall.bat dosya başka bir bilgisayardan dosya kullanarak değiştirmeyin. Eksik dosyayı değiştirmek için Visual Studio yükleyicisi yeniden çalıştırın.
>
> Vcvarsall.bat dosya sürümü başka bir sürümü de değişir. Visual Studio'nun geçerli sürümü Visual Studio'nun önceki bir sürümünü de olan bir bilgisayara yüklediyseniz, aynı komut istemi penceresinde farklı sürümlerdeki vcvarsall.bat veya başka bir Visual Studio komut dosyası çalıştırmayın.

## <a name="use-the-developer-tools-in-an-existing-command-window"></a>Varolan bir komut penceresinde geliştirici araçları kullanın

Varolan bir komut penceresinde belirli yapı mimarisi belirtmek için en basit yolu vcvarsall.bat dosya kullanmaktır. Komut satırı yerel 32 bit veya 64-bit derleme ya da çapraz derleme x86, x64 veya ARM işlemcileri için yapılandırma için ortam değişkenlerini ayarlamak için vcvarsall.bat kullanabilirsiniz; Hedef Microsoft Store, Evrensel Windows platformu veya Windows Masaüstü platformları için; kullanmak için hangi Windows SDK belirtmek için; ve platform araç takımı sürümü belirtin. Bağımsız değişkenler verdiyse, geçerli 32-bit yerel derleyici x86 için kullanmak için ortam değişkenleri vcvarsall.bat yapılandırır Windows Masaüstü hedefler. Ancak, herhangi bir yerel veya derleyici araçları çapraz yapılandırmak için kullanabilirsiniz. Yüklü değil veya yapı bilgisayar Mimarinizi üzerinde kullanılabilir olmayan bir derleyici yapılandırma belirtirseniz, bir hata iletisi görüntülenir.

### <a name="vcvarsall-syntax"></a>Vcvarsall sözdizimi

> **Vcvarsall.bat** [*mimarisi*] [*platform_type*] [*winsdk_version*] [**-vcvars_ver =** _vcversion_]

*Mimarisi*<br/>
Bu isteğe bağlı bağımsız değişkeni kullanmak için ana bilgisayarı ve hedef mimarisi belirtir. Varsa *mimarisi* belirtilmezse, varsayılan derleme ortamı kullanılır. Bu bağımsız değişkenleri desteklenir:

|*Mimarisi*|Derleyici|Ana bilgisayar mimarisi|Derleme çıktı (hedef) mimarisi|
|----------------------------|--------------|----------------------------------|-------------------------------|
|**x86**|x86 32-bit yerel|x86, x64|x86|
|**x86\_amd64** veya **x86\_x64**|x86 üzerinde x64 arası|x86, x64|X64|
|**x86_arm**|X86 ARM|x86, x64|ARM|
|**x86_arm64**|X86 üzerinde ARM64|x86, x64|ARM64|
|**AMD64** veya **x64**|x64 64-bit yerel|X64|X64|
|**AMD64\_x86** veya **x64\_x86**|x64 üzerinde x86 arası|X64|x86|
|**AMD64\_arm** veya **x64\_arm**|X64 ARM|X64|ARM|
|**AMD64\_arm64** veya **x64\_arm64**|X64 üzerinde ARM64|X64|ARM64|

*platform_type*<br/>
Bu isteğe bağlı bağımsız değişkeni belirtmenize olanak tanır **depolamak** veya **uwp** platform türü. Varsayılan olarak, masaüstü veya konsol uygulamaları geliştirmek için ortam ayarlanır.

*winsdk_version*<br/>
İsteğe bağlı olarak kullanmak için Windows SDK sürümünü belirtir. Varsayılan olarak, en son yüklenen Windows SDK kullanılır. Windows SDK sürüm belirtmek için tam bir Windows 10 SDK sayı gibi kullanabilir **10.0.10240.0**, veya belirtmek **8.1** Windows 8.1 SDK'yı kullanmak için.

*vcversion*<br/>
İsteğe bağlı olarak kullanmak için Visual Studio derleyici araç setini belirtir. Varsayılan olarak, ortamın geçerli Visual Studio 2017 derleyici araç setini kullanmak üzere ayarlanmış. Kullanım **-vcvars_ver 14.0 =** Visual Studio 2015 derleyici araç setini belirtmek için.

<a name="vcvarsall"></a>
#### <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a>Varolan bir komut istemi penceresinde yapı ortamını ayarlamak için

1. Komut isteminde, Visual Studio yükleme dizini değiştirmek için CD komutunu kullanın. Ardından, CD, özel yapılandırma komut dosyaları içeren alt dizini değiştirmek için yeniden kullanın. Visual Studio 2017 VC\Auxiliary\Build alt budur. Visual Studio 2015 için VC alt kullanın.

1. Tercih edilen geliştirme ortamınız için komutu girin. Örneğin, bir 64-bit platformda UWP için en son Windows SDK'sı ve Visual Studio 2017 RTM derleyici araç setini kullanarak ARM kodu oluşturmak için bu komut satırını kullanın:

   `vcvarsall.bat amd64_arm uwp -vcvars_ver=14.10`

## <a name="create-your-own-command-prompt-shortcut"></a>Kendi komut istemi kısayol oluşturma

Varolan Geliştirici komut istemi kısayolların biri için Özellikler iletişim kutusunu açın, kullanılan komut hedefi görebilirsiniz. Örneğin, hedef **x64 VS 2017 için yerel Araçları Komut İstemi** kısayoludur şuna benzer bir öğe:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvars64.bat"`

Mimariye özel toplu iş dosyaları kümesi *mimarisi* parametre ve çağrı vcvarsall.bat. Bu toplu iş dosyaları aynı ek seçenekler için vcvarsall.bat geçip geçmeyeceğini veya yalnızca vcvarsall.bat doğrudan çağırabilir geçirebilirsiniz. Kendi komut kısayol parametrelerini belirtmek için çift tırnak komutta sonuna ekleyin. Örneğin, bir 64-bit platformda UWP için en son Windows SDK'sı ve Visual Studio 2017 RTM derleyici araç setini kullanarak ARM kodu oluşturmak için bir kısayol ayarlamak için bu komut hedefi şöyle kısayol olarak kullanın:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvarsall.bat amd64_arm uwp -vcvars_ver=14.10"`

Yolun Visual Studio yükleme dizinine yansıtacak şekilde ayarlamanız gerekir.

## <a name="command-line-tools"></a>Komut satırı araçları

Komut satırında C/C++ projesi oluşturmak için Visual Studio bu komut satırı araçları sağlar:

[CL](../build/reference/compiling-a-c-cpp-program.md)<br/>
Derleme ve kaynak kodu dosyaları bağlantı uygulamaları, kitaplıklar ve DLL'ler derleyici (cl.exe) kullanın.

[Bağlantı](../build/reference/linking.md)<br/>
Uygulamalar ve DLL'ler bağlantı derlenen nesne dosyaları ve kitaplıkları için bağlayıcı (link.exe) kullanın.

[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)<br/>
Visual C++ projeleri ve Visual Studio çözümleri oluşturmak için MSBuild (msbuild.exe) kullanın. Bu çalışması için eşdeğerdir **yapı** proje veya **yapı çözümü** Visual Studio IDE içinde komutu.

[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)<br/>
Kullanım DEVENV (devenv.exe) komut satırı anahtarıyla birlikte — Örneğin, **/Build** veya **/Clean**— gerçekleştirmek için belirli komutları Visual Studio IDE görüntülemeden oluşturun.

[NMAKE](../build/nmake-reference.md)<br/>
NMAKE (nmake.exe), geleneksel bir derleme görevleri dosyası kullanarak Visual C++ projeleri derleme görevleri otomatikleştirmek için kullanın.

Komut satırında derlerken F1 komutu anında yardım için kullanılamaz. Bunun yerine, uyarılar, hatalar ve iletileri hakkında bilgi almak için bir arama motoru kullanabilirsiniz veya çevrimdışı Yardım dosyalarını kullanabilirsiniz. Aramada kullanılacak [docs.microsoft.com](https://docs.microsoft.com/cpp/), sayfanın üst kısmındaki arama kutusuna arama dizesini girin.

## <a name="in-this-section"></a>Bu Bölümde

Bu bölümdeki makaleleri belgelerinin uygulamalar komut satırında derleme, 64-bit toolsets ve hedef x86, x64, kullanın ve platformlar ARM ve komut satırı derleme kullanmayı göstermek için komut satırı derleme ortamı özelleştirmeyi açıklayan gösterir MSBuild ve NMAKE araçları.

[İzlenecek Yol: Komut Satırında Yerel C++ Programı Derleme](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>
Oluşturma ve basit bir C++ program komut satırında derleme gösteren bir örnek sağlar.

[İzlenecek yol: komut satırında C programı derleme](../build/walkthrough-compile-a-c-program-on-the-command-line.md)<br/>
C programlama dilinde yazılmış bir program derleyebilir açıklar.

[İzlenecek Yol: Komut Satırında C++/CLI Programını Derleme](../build/walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)<br/>
Oluşturma ve derleme C + açıklar +/ .NET Framework kullanan CLI program.

[İzlenecek Yol: Komut Satırında C++/CX Programı Derleme](../build/walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)<br/>
Oluşturma ve derleme C + açıklar +/ CX programı, Windows çalışma zamanı kullanır.

[Komut Satırı Derlemeleri için Yolu ve Ortam Değişkenlerini Ayarlama](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)<br/>
Gerekli ortam değişkenleri, hedef x86, x64, komut satırı derlemeleri için ayarlanmış ve platformlar 32 bit veya 64-bit bir araç setini kullanarak ARM sahip bir komut istemi penceresi başlangıç açıklar.

[NMAKE Başvurusu](../build/nmake-reference.md)<br/>
Microsoft Program Bakımı yardımcı programı (NMAKE. açıklamak makalelerinin bağlantıları sağlar EXE).

[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)<br/>
MSBuild.EXE kullanmak nasıl ele makalelerinin bağlantıları sağlar.

## <a name="related-sections"></a>İlgili Bölümler

[/MD, /MT, /LD (Çalışma Zamanı Kitaplığını Kullan)](../build/reference/md-mt-ld-use-run-time-library.md)<br/>
Hata ayıklama veya yayın çalışma zamanı kitaplığı kullanmak için bu derleyici seçenekleri kullanmayı açıklar.

[C/C++ Derleyici Seçenekleri](../build/reference/compiler-options.md)<br/>
C ve C++ derleyici seçenekleri ve CL.exe ele makalelerinin bağlantıları sağlar.

[Bağlayıcı Seçenekleri](../build/reference/linker-options.md)<br/>
Bağlayıcı seçenekleri ve LINK.exe ele makalelerinin bağlantıları sağlar.

[C/C++ Derleme Araçları](../build/reference/c-cpp-build-tools.md)<br/>
C/C++ için bağlantılar derleme Visual Studio'ya dahil olan araçları sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)