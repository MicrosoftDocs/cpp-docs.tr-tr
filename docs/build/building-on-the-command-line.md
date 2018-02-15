---
title: "Komut satırında C/C++ kod derleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f613c20e0cab45a8eaa802c4c7ba0c6ac391357
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="build-cc-code-on-the-command-line"></a>Komut satırında C/C++ kodu derleme

Dahil edilen araçları kullanarak komut satırında C ve C++ uygulamaları oluşturabilirsiniz [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].

Seçtiğinizde C++ iş yüklerini birini [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] yükleyici, linkers, C/C++ Derleyicileri içeren bir araç takımı yükler ve diğer yapı araçları. Bu araçları tarafından kullanılan [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] IDE ve komut satırında de kullanılabilir. Ayrı x86 barındırılan ve x64 barındırılan derleyicileri ve x86, x64 ve ARM hedefleri için kod oluşturmak için araçlar vardır. Belirli bir ana bilgisayar ve hedef yapı mimarisi için araçları her kümesinin, kendi dizininde depolanır. Doğru çalışması için bu araçları birkaç gerektiren belirli ortam değişkenleri yoluna ekleyin ve ayarlamak için dosya, kitaplık dosyasını ve SDK konumları içerir. Bu ortam değişkenlerini ayarlama kolaylaştırmak için yükleyici yüklenirken özelleştirilmiş komut dosyaları, toplu iş dosyaları olarak da bilinir oluşturur. Bu komut dosyaları birini belirli yapı mimarisi ayarlamak için bir komut istemi penceresinde çalıştırabilirsiniz. Kolaylık olması için yükleyici da kısayollar Başlat menüde oluşturur (veya başlangıç sayfasında Windows 8.x) yönelik başlangıç Geliştirici komut istemi penceresi tüm gerekli ortam değişkenlerini ayarlayın ve hazır kullanın; Bu nedenle bu komut dosyaları kullanarak. 

Gerekli ortam değişkenleri, yüklemenizi ve seçin ve ürün güncelleştirmeleri veya yükseltmeleri tarafından değiştirilebilir yapı mimarisi için özeldir. Bu nedenle, ortam değişkenleri Windows kendiniz ayarlamak yerine yüklü bir komut istemi kısayolları veya komut dosyaları birini kullanmanız önerilir. Daha fazla bilgi için bkz: [komut satırı derlemeleri için yolu ve ortam değişkenlerini ayarlama](../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  

Komut satırı toolsets, komut dosyaları ve yüklü olan bir komut istemi kısayolları bilgisayar işlemcinizin ve yükleme sırasında seçilen seçeneklere bağlıdır. En az 32 bit x86 yerel kod yapı ve 64-bit x64 yerel kodu derleme araçları çapraz 32-bit x86 barındırılan Araçları yüklenir. 64 bit Windows varsa, 64-bit yerel kod yapı ve 32-bit yerel kodu derleme araçları çapraz 64-bit x64 barındırılan araçları da yüklenir. İsteğe bağlı C++ Evrensel Windows platformu Araçları'nı yükleme seçerseniz, ARM kod derleme 32-bit ve 64-bit yerel araçlarını da yüklenir. Diğer iş yükleri, ek araçlar yükleyebilir.

<a name="developer_command_prompt_shortcuts"></a>
## <a name="developer-command-prompt-shortcuts"></a>Geliştirici komut istemi kısayolları

Komut istemi kısayolları sürüme özgü yüklü olan [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Başlat menüsü klasöründe. Temel bir komut istemi kısayolları ve destekledikleri yapı mimarileri listesi aşağıdadır:

- **Geliştirici komut istemi** 32-bit, x86 yerel kodu derleme için 32-bit, x86 yerel araçlarını kullanma ortamını ayarlar.  
- **x86 yerel Araçları Komut İstemi** 32-bit, x86 yerel kodu derleme için 32-bit, x86 yerel araçlarını kullanma ortamını ayarlar.  
- **x64 yerel Araçları Komut İstemi** 64-bit, x64 yerel kodu derleme için 64-bit, x64 yerel araçlarını kullanma ortamını ayarlar.  
- **x86_x64 arası Araçları Komut İstemi** 64-bit, x64 yerel kodu derleme için 32-bit, x86 yerel araçlarını kullanma ortamını ayarlar.  
- **x64_x86 arası Araçları Komut İstemi** 32-bit, x86 yerel kodu derleme için 64-bit, x64 yerel araçlarını kullanma ortamını ayarlar.  

Gerçek başlangıç menüsünde klasörü ve kısayol adları sürümüne bağlı olarak farklılık gösterir [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] yüklü olduğunu ve yükleme ayarladıysanız takma adı. Örneğin, geliştirici komut istemi kısayoluna yüklü Visual Studio 2017 varsa ve 15.3 takma ad yüklemesini verdiniz adlı **VS 2017 (15.3) için geliştirici komut istemi**, adlı bir klasörde  **Visual Studio 2017**. 

Uygulamasını yüklediyseniz [derleme araçları Visual Studio 2017 için](https://go.microsoft.com/fwlink/p/?linkid=840931) veya [Visual C++ 2015 derleme Araçları](http://landinghub.visualstudio.com/visual-cpp-build-tools) edition, ayrıca belirli yerel yalnızca olabilir veya geçici araçları Geliştirici komut istemi seçenekleri. 

<a name="developer_command_prompt"></a>
## <a name="to-open-a-developer-command-prompt-window"></a>Bir geliştirici komut istemi penceresi açmak için  
  
1.  Windows masaüstünde, açık **Başlat** menü ve bulmak ve örneğin, Visual Studio sürümünüze klasörü açmak için kaydırma yapın **Visual Studio 2017**. Visual Studio bazı eski sürümlerinde kısayolları adlı alt klasörde olan **Visual Studio Araçları**.  
  
2.  Klasöründe seçin **Geliştirici komut istemi** Visual Studio sürümünüze. Bu kısayol 32-bit, x86 yerel kodu oluşturmak için 32-bit, x86 yerel Araçlar Varsayılan yapı mimarisi kullanan bir geliştirici komut istemi penceresi başlatır. Varsayılan olmayan yapı mimarisi tercih ederseniz, yerel birini seçin veya ana bilgisayar ve hedef mimarisi belirtmek için komut istemleri arası araçları. 

Bir geliştirici komut istemi penceresi açmak için daha hızlı bir şekilde girmektir *Geliştirici komut istemi* masaüstü arama kutusuna, ardından istenen sonucu seçin.

<a name="developer_command_files"></a>
## <a name="developer-command-files-and-locations"></a>Geliştirici komut dosyaları ve konumları

Varolan bir komut istemi penceresinde yapı mimarisi ortamını ayarlamak tercih ederseniz yükleyici tarafından oluşturulan komut dosyalarından birini kullanabilirsiniz. Bu dosyaların konumunu sürümüne bağlıdır [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] yüklü olduğunu ve konumunu ve adlandırma seçenekleriyle yükleme sırasında yapılan. Visual Studio 2017 için tipik yükleme 64-bit bilgisayarda \Program dosyaları (x86) \Microsoft Visual Studio\2017 konumdur\\*edition*, burada *edition* topluluk olabilir Professional, Enterprise, BuildTools veya başka bir ad sağladığınız. Visual Studio 2015 için tipik yükleme konumu \Program Files (x86) \Microsoft Visual Studio 14.0 şeklindedir. 

Birincil geliştirici komut istemi komut dosyası, VsDevCmd.bat, Common7\Tools alt yükleme dizininde bulunur. Hiç parametresi belirtildiğinde, bunun 32 bit x86 oluşturmak için 32-bit x86 yerel araçlarını kullanmak için ortamı ve yapı mimarisi ayarlar kodu.

İşlemci mimariniz bağlı olarak belirli yapı mimarileri ayarlamak ek komut dosyaları kullanılabilir ve [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] iş yükleri ve yüklü olan seçenekleri. Visual Studio 2017 ' Bu VC\Auxiliary\Build alt dizininde bulunan [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] yükleme dizini. Visual Studio 2015'te bu VC, VC\bin veya VC\bin bulunan\\*mimarileri* yükleme dizininin alt dizinleri nerede *mimarileri* yerel veya çapraz biridir Derleyici Seçenekleri. Bu komut dosyaları parametrelerini ayarlamak ve belirtilen yapı mimarisi ortamını ayarlamak için VsDevCmd.bat çağırın. Tipik bir yüklemede, bu komut dosyaları içerebilir:

- **vcvars32.bat** 32-bit x86 oluşturmak için 32-bit x86 yerel araçlarını kullanın kodu.  
- **vcvars64.bat** 64-bit x64 oluşturmak için 64-bit x64 yerel araçları kullanmak kodu.  
- **vcvarsx86_amd64.bat** 64-bit x64 oluşturmak için 32-bit x86 yerel çapraz araçlarını kullanın kodu.  
- **vcvarsamd64_x86.bat** 32-bit x86 oluşturmak için 64-bit x64 yerel çapraz araçları kullanın kodu.  
- **vcvarsx86_arm.bat** ARM kodu oluşturmak için 32-bit x86 yerel çapraz araçlarını kullanın.  
- **vcvarsamd64_arm.bat** ARM kodu oluşturmak için 64-bit x64 yerel çapraz araçlarını kullanın.  
- **Vcvarsall.bat** parametreleri ana bilgisayar ve hedef mimarilerinin yanı SDK ve platform seçeneklerini belirtmek için kullanın. Kullanarak çağırma bir `/help` seçeneklerinin bir listesi için parametre.  

> [!CAUTION]
>  Vcvarsall.bat dosya ve diğer komut dosyaları bilgisayardan diğerine farklılık gösterebilir. Eksik veya zarar görmüş vcvarsall.bat dosya başka bir bilgisayardan dosya kullanarak değiştirmeyin. Yeniden çalıştırılan [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] yükleyici dosyası eksik değiştirin.  
>   
> Vcvarsall.bat dosya sürümü başka bir sürümü de değişir. Geçerli sürümü Visual C++, Visual C++'ın önceki bir sürümünü de olan bir bilgisayara yüklediyseniz, aynı komut istemi penceresinde farklı sürümlerdeki vcvarsall.bat veya başka bir komut dosyası çalıştırmayın.  
 
Varolan bir komut penceresinde belirli yapı mimarisi belirtmek için en basit yolu vcvarsall.bat dosya kullanmaktır. Komut satırı yerel 32 bit veya 64-bit derleme ya da çapraz derleme x86, x64 veya ARM işlemcileri için yapılandırma için ortam değişkenlerini ayarlamak için vcvarsall.bat kullanabilirsiniz; Hedef Microsoft Store, Evrensel Windows platformu veya Windows Masaüstü platformları için; kullanmak için hangi Windows SDK belirtmek için; ve platform araç takımı sürümü belirtin. Bağımsız değişkenler verdiyse, geçerli 32-bit yerel derleyici x86 için kullanmak için ortam değişkenleri vcvarsall.bat yapılandırır Windows Masaüstü hedefler. Ancak, herhangi bir yerel veya derleyici araçları çapraz yapılandırmak için kullanabilirsiniz. Yüklü değil veya yapı bilgisayar Mimarinizi üzerinde kullanılabilir olmayan bir derleyici yapılandırma belirtirseniz, bir hata iletisi görüntülenir. Bu tabloda, desteklenen mimari bağımsız değişkenleri gösterilmektedir:  
  
|Vcvarsall.bat mimarisi bağımsız değişkeni|Derleyici|Ana bilgisayar mimarisi|Derleme çıktı mimarisi|  
|----------------------------|--------------|----------------------------------|-------------------------------|  
|x86|x86 32-bit yerel|x86, x64|x86|  
|x86\_amd64 veya x86\_x64|x86 üzerinde x64 arası|x86, x64|X64|  
|x86_arm|X86 ARM|x86, x64|ARM|  
|AMD64 veya x64|x64 64-bit yerel|X64|X64|  
|AMD64\_x86 veya x64\_x86|x64 üzerinde x86 arası|X64|x86|  
|AMD64\_arm veya x64\_arm|X64 ARM|X64|ARM|  
  
Kullanabileceğiniz **depolamak** veya **uwp** platform türünü veya hiçbiri bir masaüstü uygulamasının belirtmek için belirtmek için Seçenekler. Windows SDK sürüm belirtmek için tam bir Windows 10 SDK numarası 10.0.10240.0 gibi kullanın veya Windows 8.1 SDK'yı kullanmak için 8.1 belirtin. Visual Studio 2015 derleyici araç setini belirtmek için 14.0 kullanın; Varsayılan olarak, ortamın Visual Studio 2017 derleyici araç setini kullanmak üzere ayarlanmış.

<a name="vcvarsall"></a>
## <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a>Varolan bir komut istemi penceresinde yapı ortamını ayarlamak için  
  
1.  Komut isteminde, Visual Studio yükleme dizini değiştirmek için CD komutunu kullanın. Ardından, CD, özel yapılandırma komut dosyaları içeren alt dizini değiştirmek için yeniden kullanın. Visual Studio 2017 VC\Auxiliary\Build alt budur. Visual Studio 2015 için VC alt kullanın.  
  
1.  Bu komut istemi penceresi x86 için kod oluşturmak için 32-bit araçları kullanmak üzere yapılandırmak için komut isteminde platformları girin:  
  
     `vcvarsall`  

1.  Bu komut istemi penceresi x64 için kod oluşturmak için 32-bit araçları kullanmak üzere yapılandırmak için komut isteminde platformları girin:  
  
     `vcvarsall x86_amd64`  
  
1.  Komut isteminde, ARM platformlar için kod oluşturmak için 32-bit araçları kullanmak için bu komut istemi penceresi yapılandırmak için aşağıdakileri girin:  
  
     `vcvarsall x86_arm`  
  
1.  Bu komut istemi penceresi x64 için kod oluşturmak için 64-bit araçları kullanmak üzere yapılandırmak için komut isteminde platformları girin:  
  
     `vcvarsall amd64`  
  
1.  Bu komut istemi penceresi x86 için kod oluşturmak için 64-bit araçları kullanmak üzere yapılandırmak için komut isteminde platformları girin:  
  
     `vcvarsall amd64_x86`  
  
1.  Komut isteminde, ARM platformlar için kod oluşturmak için 64-bit araçları kullanmak için bu komut istemi penceresi yapılandırmak için aşağıdakileri girin:  
  
     `vcvarsall amd64_arm`  

Komut dosyası yolları için gerekli ortam değişkenleri derleme araçlarını, kitaplıklarını ve üstbilgileri ayarlar. Bu komut istemi penceresi artık komut satırı derleyicisi ve araçları çalıştırmak için de kullanabilirsiniz.  
  
Kullanıyorsanız [DEVENV](/visualstudio/ide/reference/devenv-command-line-switches) de belirtilmedikçe komut satırı derlemeleri için vcvarsall.bat veya diğer komut dosyaları tarafından ayarlanan ortam derlemeleriniz, etkilemez **/useenv** seçeneği.  

## <a name="command-line-tools"></a>Komut satırı araçları
  
Komut satırında C/C++ projesi oluşturmak için bu Visual C++ komut satırı araçları kullanabilirsiniz:  
  
[CL](../build/reference/compiling-a-c-cpp-program.md)  
Derleme ve kaynak kodu dosyaları bağlantı uygulamaları, kitaplıklar ve DLL'ler derleyici (cl.exe) kullanın.  
  
[Bağlantı](../build/reference/linking.md)  
Uygulamalar ve DLL'ler bağlantı derlenen nesne dosyaları ve kitaplıkları için bağlayıcı (link.exe) kullanın.  
  
[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)  
Visual C++ projeleri oluşturmak için MSBuild (msbuild.exe) kullanın ve [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] çözümler. Bu çalışması için eşdeğerdir **yapı** proje veya **yapı çözümü** komutunu [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] IDE.  
  
[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)  
Kullanım DEVENV (devenv.exe) komut satırı anahtarıyla birlikte — Örneğin, **/Build** veya **/Clean**— gerçekleştirmek için belirli komutları görüntülemeden yapı [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] IDE.  
  
[NMAKE](../build/nmake-reference.md)  
NMAKE (nmake.exe), geleneksel bir derleme görevleri dosyası kullanarak Visual C++ projeleri derleme görevleri otomatikleştirmek için kullanın.  
  
Komut satırında yapılandırdığınızda, uyarılar, hatalar ve iletileri hakkında bilgi alabilirsiniz. Başlat [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] ve menü çubuğunda, ardından **yardımcı**, **arama**.  
  
## <a name="in-this-section"></a>Bu Bölümde  

Bu bölümdeki makaleleri belgelerinin uygulamalar komut satırında derleme, 64-bit toolsets ve hedef x86, x64, kullanın ve platformlar ARM ve komut satırı derleme kullanmayı göstermek için komut satırı derleme ortamı özelleştirmeyi açıklayan gösterir MSBuild ve NMAKE araçları.  
  
[İzlenecek Yol: Komut Satırında Yerel C++ Programı Derleme](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)  
Oluşturma ve basit bir C++ program komut satırında derleme gösteren bir örnek sağlar.  
  
[İzlenecek yol: komut satırında C programı derleme](../build/walkthrough-compile-a-c-program-on-the-command-line.md)  
C programlama dilinde yazılmış bir program derleyebilir açıklar.  
  
[İzlenecek Yol: Komut Satırında C++/CLI Programını Derleme](../build/walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)  
Oluşturma ve derleme C + açıklar +/ .NET Framework kullanan CLI program.  
  
[İzlenecek Yol: Komut Satırında C++/CX Programı Derleme](../build/walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)  
Oluşturma ve derleme C + açıklar +/ CX programı, Windows çalışma zamanı kullanır.  
  
[Komut Satırı Derlemeleri için Yolu ve Ortam Değişkenlerini Ayarlama](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)  
Gerekli ortam değişkenleri, hedef x86, x64, komut satırı derlemeleri için ayarlanmış ve platformlar 32 bit veya 64-bit bir araç setini kullanarak ARM sahip bir komut istemi penceresi başlangıç açıklar.  
  
[NMAKE Başvurusu](../build/nmake-reference.md)  
Microsoft Program Bakımı yardımcı programı (NMAKE. açıklamak makalelerinin bağlantıları sağlar EXE).  
  
[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)  
MSBuild.EXE kullanmak nasıl ele makalelerinin bağlantıları sağlar.  
  
## <a name="related-sections"></a>İlgili Bölümler  

[/MD, /MT, /LD (Çalışma Zamanı Kitaplığını Kullan)](../build/reference/md-mt-ld-use-run-time-library.md)  
Hata ayıklama veya yayın çalışma zamanı kitaplığı kullanmak için bu derleyici seçenekleri kullanmayı açıklar.  
  
[C/C++ Derleyici Seçenekleri](../build/reference/compiler-options.md)  
C ve C++ derleyici seçenekleri ve CL.exe ele makalelerinin bağlantıları sağlar.  
  
[Bağlayıcı Seçenekleri](../build/reference/linker-options.md)  
Bağlayıcı seçenekleri ve LINK.exe ele makalelerinin bağlantıları sağlar.  
  
[C/C++ Derleme Araçları](../build/reference/c-cpp-build-tools.md)  
C/C++ için bağlantılar yapı içinde yer alan araçlar sağlayan [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)