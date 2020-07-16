---
title: Visual Studio 'da C++ Linux projenizi dağıtma, çalıştırma ve hata ayıklama
description: Visual Studio 'da bir Linux C++ projesinin içinden uzak hedef üzerinde kod derlemeyi, yürütmeyi ve hata ayıklamanın nasıl yapılacağını açıklar.
ms.date: 06/07/2019
ms.assetid: f7084cdb-17b1-4960-b522-f84981bea879
ms.openlocfilehash: df095d5561bea6dac94b9faa139c83c197802bbf
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404417"
---
# <a name="deploy-run-and-debug-your-linux-project"></a>Linux projenizi dağıtma, çalıştırma ve projenizin hatalarını ayıklama

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

Visual Studio 'da bir Linux C++ projesi oluşturduktan ve [Linux bağlantı yöneticisini](connect-to-your-remote-linux-computer.md)kullanarak projeye bağlandıktan sonra, projeyi çalıştırabilir ve hata ayıklaması yapabilirsiniz. Uzak hedefte kodu derler, yürütür ve hatalarını ayıklayın.

::: moniker range="vs-2019"

**Visual Studio 2019 sürüm 16,1** Hata ayıklama ve oluşturma için farklı Linux sistemleri hedefleyebilirsiniz. Örneğin, bir x64 üzerinde çapraz derleyip, IoT senaryolarını hedeflerken ARM cihazına dağıtabilirsiniz. Daha fazla bilgi için, bu makalede daha sonra [derleme ve hata ayıklama için farklı makineler belirtme](#separate_build_debug) bölümüne bakın.

::: moniker-end

Linux projenizde etkileşimde bulunmak ve hata ayıklaması yapmak için birkaç yol vardır.

- Kesme noktaları, pencereleri izle ve bir değişken üzerine gelindiğinde geleneksel Visual Studio özelliklerini kullanarak hata ayıklayın. Bu yöntemleri kullanarak, normal olarak diğer proje türleri için yaptığınız gibi hata ayıklaması yapabilirsiniz.

- Linux konsol penceresinde hedef bilgisayardaki çıktıyı görüntüleyin. Ayrıca, hedef bilgisayara giriş göndermek için konsolunu kullanabilirsiniz.

## <a name="debug-your-linux-project"></a>Linux projenizde hata ayıklama

1. **Hata ayıklama** Özellik sayfasında hata ayıklama modu ' nu seçin.

   ::: moniker range="vs-2019"

   GDB, Linux üzerinde çalışan uygulamalarda hata ayıklamak için kullanılır. Uzak sistemde hata ayıklama yapıldığında (WSL değil) GDB, projenin **hata ayıklama** özellik sayfasındaki **hata ayıklama modu** seçeneğinden seçilebilen iki farklı modda çalışabilir:

   ![GDB seçenekleri](media/vs2019-debugger-settings.png)

   ::: moniker-end

   ::: moniker range="vs-2017"

   GDB, Linux üzerinde çalışan uygulamalarda hata ayıklamak için kullanılır. GDB, projenin **hata ayıklama** özellik sayfasındaki **hata ayıklama modu** seçeneğinden seçilebilen iki farklı modda çalışabilir:

   ![GDB seçenekleri](media/vs2017-debugger-settings.png)

   ::: moniker-end

   - **Gdbserver** modunda, gdb yerel olarak çalıştırılır ve bu, uzak sistemdeki gdbserver 'a bağlanır.  Bunun, Linux konsol penceresinin desteklediği tek mod olduğunu unutmayın.

   - **Gdb** modunda, Visual Studio hata ayıklayıcı uzak sistemdeki gdb 'yi yürütür. Bu, GDB 'nin yerel sürümü hedef bilgisayarda yüklü olan sürümle uyumlu değilse daha iyi bir seçenektir. |

   > [!NOTE]
   > Gdbserver hata ayıklama modundaki kesme noktalarına isabet ediyorsanız, gdb modunu deneyin. GDB 'nin öncelikle uzak hedefte [yüklü](download-install-and-setup-the-linux-development-workload.md) olması gerekir.

1. Visual Studio 'da standart **hata ayıklama** araç çubuğunu kullanarak uzak hedefi seçin.

   Uzak hedef kullanılabilir olduğunda, adı veya IP adresine göre listelenmiş olarak görürsünüz.

   ![Uzak hedef](media/remote_target.png)

   Uzak hedefe henüz bağlanmadıysanız, uzak hedefe bağlanmak için [Linux bağlantı yöneticisini](connect-to-your-remote-linux-computer.md) kullanma yönergesini görürsünüz.

   ![Uzak mimari](media/architecture.png)

1. Yürütüleceği bildiğiniz bazı kodların sol Cilt payının tıklanarak bir kesme noktası ayarlayın.

   Kesme noktasını ayarladığınız kod satırında kırmızı bir nokta görünür.

1. Hata ayıklamayı başlatmak için **F5** tuşuna basın (veya hata **ayıklamayı başlatın >**).

   Hata ayıklamayı başlattığınızda, uygulama başlatılmadan önce uzak hedefte derlenir. Tüm derleme hataları **hata listesi** penceresinde görünür.

   Hata yoksa, uygulama başlatılır ve hata ayıklayıcı kesme noktasında duraklatılır.

   ![Kesme noktasına isabet edin](media/hit_breakpoint.png)

   Şimdi, geçerli durumunda uygulamayla etkileşim kurabilir, değişkenleri görüntüleyebilir ve **F10** ya da **F11**gibi komut anahtarlarına basarak koddan gezinebilirsiniz.

1. Uygulama ile etkileşim kurmak için Linux konsolunu kullanmak istiyorsanız, **Linux konsolu > hata ayıkla**' yı seçin.

   ![Linux konsol menüsü](media/consolemenu.png)

   Bu konsol, hedef bilgisayardaki herhangi bir konsol çıkışını gösterir ve giriş alır ve hedef bilgisayara gönderir.

   ![Linux konsol penceresi](media/consolewindow.png)

## <a name="configure-other-debugging-options-msbuild-based-projects"></a>Diğer hata ayıklama seçeneklerini yapılandırma (MSBuild tabanlı projeler)

- Komut satırı bağımsız değişkenleri, projenin **hata ayıklama** özellik sayfasındaki **Program bağımsız değişkenleri** öğesi kullanılarak yürütülebilir dosyaya geçirilebilir.

   ![Program bağımsız değişkenleri](media/settings_programarguments.png)

- Özel hata ayıklayıcı seçenekleri **ek hata ayıklayıcı komutları** girişi kullanılarak gdb 'ye geçirilebilir.  Örneğin, SIGILL (geçersiz yönerge) sinyallerini yoksaymak isteyebilirsiniz.  Yukarıda gösterildiği gibi **ek hata ayıklayıcı komutları** girişine aşağıdakileri ekleyerek bunu gerçekleştirmek için **tanıtıcı** komutunu kullanabilirsiniz:

   `handle SIGILL nostop noprint`

## <a name="configure-other-debugging-options-cmake-projects"></a>Diğer hata ayıklama seçeneklerini yapılandırma (CMake projeleri)

Dosyadaki launch.vs.jsbir CMake projesi için ek komut satırı bağımsız değişkenleri belirtebilirsiniz. Daha fazla bilgi için bkz [. CMake projesinde hata ayıklama](cmake-linux-project.md#debug_cmake_project)

## <a name="debug-with-attach-to-process"></a>Işleme Iliştir ile hata ayıkla

Visual Studio projeleri için [hata ayıklama](prop-pages/debugging-linux.md) Özellik sayfası ve CMake projelerine yönelik ayarların **Launch.vs.js** , çalışan bir işleme iliştirmeyi sağlayan ayarlara sahiptir. Bu ayarlarda sağlananların ötesinde ek denetime ihtiyacınız varsa, `Microsoft.MIEngine.Options.xml` çözümünüzün veya çalışma alanınızın köküne adlı bir dosya yerleştirebilirsiniz. İşte basit bir örnek:

```xml
<?xml version="1.0" encoding="utf-8"?>
<SupplementalLaunchOptions>
    <AttachOptions>
      <AttachOptionsForConnection AdditionalSOLibSearchPath="/home/user/solibs">
        <ServerOptions MIDebuggerPath="C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise\Common7\IDE\VC\Linux\bin\gdb\7.9\x86_64-linux-gnu-gdb.exe"
ExePath="C:\temp\ConsoleApplication17\ConsoleApplication17\bin\x64\Debug\ConsoleApplication17.out"/>
        <SetupCommands>
          <Command IgnoreFailures="true">-enable-pretty-printing</Command>
        </SetupCommands>
      </AttachOptionsForConnection>
    </AttachOptions>
</SupplementalLaunchOptions>
```

**AttachOptions Forconnection** , ihtiyacınız olabilecek özniteliklerin çoğunu içerir. Yukarıdaki örnekte, ek için arama yapmak üzere bir konum belirtme gösterilmektedir. bu nedenle kitaplıklar. Alt öğe **Serveroptions** , bunun yerine gdbserver ile uzak işleme iliştirmeye olanak sağlar. Bunu yapmak için, yerel bir gdb istemcisini (Visual Studio 2017 ' de sunulan bir tane yukarıda gösterilmektedir) ve simgeler içeren bir ikili dosyanın yerel kopyasını belirtmeniz gerekir. **Setupcommands** öğesi komutları doğrudan gdb 'ye geçirmenize olanak sağlar. GitHub 'daki [launchoptions. xsd şemasında](https://github.com/Microsoft/MIEngine/blob/master/src/MICore/LaunchOptions.xsd) bulunan tüm seçenekleri bulabilirsiniz.

::: moniker range="vs-2019"

## <a name="specify-different-machines-for-building-and-debugging"></a><a name="separate_build_debug"></a>Oluşturma ve hata ayıklama için farklı makineler belirtin

Visual Studio 2019 sürüm 16,1 ' de uzak derleme makinenizi hem MSBuild tabanlı Linux projeleri hem de uzak bir Linux makinesini hedefleyen CMake projeleri için uzaktan hata ayıklama makinenizden ayırabilirsiniz. Örneğin, artık x64 üzerinde çapraz derleme yapabilir ve IoT senaryolarını hedeflerken ARM cihazına dağıtabilirsiniz.

### <a name="msbuild-based-projects"></a>MSBuild tabanlı projeler

Varsayılan olarak, uzaktan hata ayıklama makinesi, uzak derleme makinesi (**yapılandırma özellikleri**  >  **genel**  >  **Uzaktan derleme makinesi**) ile aynıdır. Yeni bir uzaktan hata ayıklama makinesi belirtmek için **Çözüm Gezgini** ' de projeye sağ tıklayın ve **Configuration Properties**  >  **Debugging**  >  **Uzaktan hata ayıklama makinesinde**yapılandırma özellikleri ' ne gidin.  

![Linux uzaktan hata ayıklama makinesi](media/linux-remote-debug-machine.png)

**Uzaktan hata ayıklama makinesi** için açılan menü, tüm kurulu uzak bağlantılarla doldurulur. Yeni bir uzak bağlantı eklemek için, **Araçlar**  >  **Seçenekler**  >  **platformlar arası**  >  **Bağlantı Yöneticisi** ' ne gidin veya **Hızlı başlatma**bölümünde "bağlantı Yöneticisi" ni arayın. Projenin özellik sayfalarında (**yapılandırma özellikleri**  >  **genel**  >  **uzaktan dağıtım dizini**) yeni bir uzak dağıtım dizini de belirtebilirsiniz.

Varsayılan olarak, yalnızca hata ayıklama işlemi için gerekli olan dosyalar, uzaktan hata ayıklama makinesine dağıtılır. Uzaktan hata ayıklama makinesine hangi kaynak dosyalarının dağıtılacağını yapılandırmak için **Çözüm Gezgini** kullanabilirsiniz. Bir kaynak dosyaya tıkladığınızda, Çözüm Gezgini dosya özelliklerinin doğrudan bir önizlemesini görürsünüz.

![Linux dağıtılabilir dosyalar](media/linux-deployable-content.png)

**Content** özelliği, dosyanın uzak hata ayıklama makinesine dağıtılıp dağıtılmayacağını belirtir. Dağıtımı tamamen devre dışı bırakabilirsiniz Configuration Manager **özellik sayfalarına**giderek  >  **Configuration Manager** , istenen yapılandırma için **dağıtımı** geri alabilirsiniz.

Bazı durumlarda, projenizin dağıtımı üzerinde daha fazla denetime ihtiyacınız olabilir. Örneğin, dağıtmak istediğiniz bazı dosyalar çözümünüzün dışında olabilir veya uzak dağıtım dizininizi dosya ordizin başına özelleştirmek isteyebilirsiniz. Bu durumlarda, aşağıdaki kod bloğunu. vcxproj dosyanıza ekleyin ve "example. cpp" değerini gerçek dosya adlarıyla değiştirin:

```xml

<ItemGroup>
   <RemoteDeploy Include="__example.cpp">
<!-- This is the source Linux machine, can be empty if DeploymentType is LocalRemote -->
      <SourceMachine>$(RemoteTarget)</SourceMachine>
      <TargetMachine>$(RemoteDebuggingTarget)</TargetMachine>
      <SourcePath>~/example.cpp</SourcePath>
      <TargetPath>~/example.cpp</TargetPath>
<!-- DeploymentType can be LocalRemote, in which case SourceMachine will be empty and SourcePath is a local file on Windows -->
      <DeploymentType>RemoteRemote</DeploymentType>
<!-- Indicates whether the deployment contains executables -->
      <Executable>true</Executable>
   </RemoteDeploy>
</ItemGroup>
```

### <a name="cmake-projects"></a>CMake projeleri

Uzak bir Linux makinesini hedefleyen CMake projeleri için üzerinde launch.vs.jsyeni bir uzaktan hata ayıklama makinesi belirtebilirsiniz. Varsayılan olarak, "remoteMachineName" değeri, uzaktan derleme makinenize karşılık gelen CMakeSettings.jsüzerindeki "remoteMachineName" özelliği ile eşitlenir. Bu özelliklerin artık eşleşmesi gerekmez ve üzerinde launch.vs.js"remoteMachineName" değeri, dağıtım ve hata ayıklama için hangi uzak makinenin kullanılacağını dikte eder.

![CMake uzaktan hata ayıklama makinesi](media/cmake-remote-debug-machine.png)

IntelliSense, tüm kurulu uzak bağlantıların bir listesini önerir. **Araçlar**  >  **Seçenekler**  >  **platformlar arası**  >  **Bağlantı Yöneticisi** ' ne giderek veya **Hızlı başlatma**bölümünde "bağlantı Yöneticisi" ' ni arayarak yeni bir uzak bağlantı ekleyebilirsiniz.

Dağıtımınız üzerinde tamamen denetim istiyorsanız, aşağıdaki kod bloğunu launch.vs.jsdosyasına ekleyebilirsiniz. Yer tutucu değerlerini gerçek değerlerle değiştirmeyi unutmayın:

```json

"disableDeploy": false,
"deployDirectory": "~\foo",
"deploy" : [
   {
      "sourceMachine": "127.0.0.1 (username=example1, port=22, authentication=Password)",
      "targetMachine": "192.0.0.1 (username=example2, port=22, authentication=Password)",
      "sourcePath": "~/example.cpp",
      "targetPath": "~/example.cpp",
      "executable": "false"
   }
]

```

::: moniker-end

## <a name="next-steps"></a>Sonraki adımlar

- Linux 'ta ARM cihazlarda hata ayıklamak için bkz. [Visual Studio 'da KATıŞTıRıLMıŞ ARM cihazında hata ayıklama](https://devblogs.microsoft.com/cppblog/debugging-an-embedded-arm-device-in-visual-studio/).

## <a name="see-also"></a>Ayrıca bkz.

[C++ hata ayıklama özellikleri (Linux C++)](prop-pages/debugging-linux.md)
