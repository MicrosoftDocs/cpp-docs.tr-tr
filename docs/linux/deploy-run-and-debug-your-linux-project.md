---
title: Dağıtma, çalıştırma ve C++ Linux projenizi Visual Studio'da hata ayıklama
description: Derleme, yürütün ve hata ayıklama kodu Visual Studio'da Linux C++ projesi içinde uzak hedefte açıklar.
ms.date: 06/07/2019
ms.assetid: f7084cdb-17b1-4960-b522-f84981bea879
ms.openlocfilehash: 70770385bde859d47532b130463a1cc54e32a570
ms.sourcegitcommit: fde637f823494532314790602c2819f889706ff6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67042757"
---
# <a name="deploy-run-and-debug-your-linux-project"></a>Linux projenizi dağıtma, çalıştırma ve projenizin hatalarını ayıklama

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ile kullanılabilir ve üzerinde desteklenir.

::: moniker-end

Visual Studio'da Linux C++ projesi oluşturduktan sonra proje kullanarak bağlantı kurduğunuz [Linux Bağlantı Yöneticisi](connect-to-your-remote-linux-computer.md), çalıştırın ve proje hata ayıklama. Derleme, yürütün ve uzak hedef kodunda hata ayıklayın.

::: moniker range="vs-2019"

**Visual Studio 2019 sürüm 16.1** hata ayıklama ve oluşturmak için farklı Linux sistemleri hedefleyebilirsiniz. Örneğin, x64 üzerinde çapraz-derleme ve ARM cihazına IOT senaryoları hedeflenirken dağıtın. Daha fazla bilgi için [derleme ve hata ayıklama için farklı makineler belirten](#separate_build_debug) bu makalenin ilerleyen bölümlerinde.

::: moniker-end

Linux projenizin hatalarını ayıklama ve etkileşim için birkaç yol vardır.

- Kesme noktaları, Gözcü pencerelerini ve bir değişkenin geldiğinizde gibi geleneksel Visual Studio özellikleri kullanarak hata ayıklama. Diğer proje türleri için normalde yaptığınız gibi bu yöntemleri kullanarak hata ayıklama.

- Linux konsol penceresinde hedef bilgisayardan çıktısını görüntüleyin. Konsolu, hedef bilgisayara giriş göndermek için de kullanabilirsiniz.

## <a name="debug-your-linux-project"></a>Linux projenizin hatalarını ayıklama

1. Select hata ayıklama modunda **hata ayıklama** özellik sayfası.
   
   ::: moniker range="vs-2019"

   GDB, Linux üzerinde çalışan uygulamalarda hata ayıklama için kullanılır. Uzak bir sistemde (WSL değil) hata ayıklama sırasında GDB öğesinden seçilebilir iki farklı modda çalıştırabilirsiniz **mod hata ayıklaması** seçeneği projenin **hata ayıklama** özellik sayfası:

   ![GDB seçenekleri](media/vs2019-debugger-settings.png)

   ::: moniker-end

   ::: moniker range="vs-2017"

   GDB, Linux üzerinde çalışan uygulamalarda hata ayıklama için kullanılır. GDB öğesinden seçilebilir iki farklı modda çalışabilir **mod hata ayıklaması** seçeneği projenin **hata ayıklama** özellik sayfası:

   ![GDB seçenekleri](media/vs2017-debugger-settings.png)

   ::: moniker-end


   - İçinde **gdbserver** modunda, GDB çalıştırın yerel olarak uzak sistemdeki gdbserver bağlanır.  Bu Linux konsol penceresinde destekleyen tek mod olduğunu unutmayın.

   - İçinde **gdb** modu, Visual Studio hata ayıklayıcı, uzak sistemde GDB sürücüler. Bu, GDB yerel sürümünü hedef bilgisayarda yüklü sürümüyle uyumlu değilse, daha iyi bir seçenektir. |

   > [!NOTE]
   > İsabet kesme noktaları hata ayıklama gdbserver modunda, gdb modunda deneyin. GDB ilk olmalıdır [yüklü](download-install-and-setup-the-linux-development-workload.md) uzak hedef.

1. Standart kullanarak uzak hedef seçin **hata ayıklama** Visual Studio'da araç çubuğu.

   Uzak hedef kullanılabilir olduğunda, ad veya IP adresine göre listelenen görürsünüz.

   ![Uzak hedef](media/remote_target.png)

   Uzak hedef henüz bağlanmadıysanız, kullanılacak bir yönerge göreceğiniz [Linux Bağlantı Yöneticisi](connect-to-your-remote-linux-computer.md) uzak hedef bağlanmak için.

   ![Uzak mimarisi](media/architecture.png)

1. Bazı kod sol kanalda tıklatarak bir kesme noktası bilmeniz kümesi çalıştırır.

   Kırmızı nokta kod satırında Kesme noktasının ayarlandığı görünür.

1. Tuşuna **F5** (veya **hata ayıklama > hata ayıklamayı Başlat**) hata ayıklama başlatılamıyor.

   Hata ayıklaması başlattığınızda, uygulama başlamadan önce uzak hedef üzerinde derlenir. Derleme hataları görünür **hata listesi** penceresi.

   Herhangi bir hata varsa, uygulama başlatılır ve hata ayıklayıcı kesme noktasında duraklatılır.

   ![Bir kesme noktası isabet](media/hit_breakpoint.png)

   Artık, uygulamanın kendi geçerli durumunda, değişkenleri görüntüle ve kodu adımlayın gibi komut tuşlarına basarak etkileşim kurabileceğiniz **F10** veya **F11**.

1. Uygulamanızı, select etkileşim kurmak için Linux konsolu kullanmak istiyorsanız **hata ayıklama > Linux Konsolu**.

   ![Linux konsolu menü](media/consolemenu.png)

   Bu konsol hedef bilgisayarı tüm konsol çıktısı görüntüler yanı sıra gelenlerin ve hedef bilgisayara gönderin.

   ![Linux konsol penceresi](media/consolewindow.png)

## <a name="configure-other-debugging-options-msbuild-based-projects"></a>Diğer hata ayıklama seçenekleri (MSBuild tabanlı projeler) yapılandırın

- Komut satırı bağımsız değişkenleri yürütülebilir kullanarak geçirilebilir **Program bağımsız değişkenleri** projenin öğesi **hata ayıklama** özellik sayfası.

   ![Program bağımsız değişkenleri](media/settings_programarguments.png)

- Belirli hata ayıklayıcısı seçenekleri geçirilebilir için GDB kullanarak **ek hata ayıklayıcı komutları** girişi.  Örneğin, SIGILL (geçersiz yönerge) sinyalleri yoksaymak isteyebilirsiniz.  Kullanabileceğinizi **işlemek** aşağıdakileri ekleyerek bunu başarmanın komut **ek hata ayıklayıcı komutları** yukarıda da gösterildiği gibi giriş:

   `handle SIGILL nostop noprint`

## <a name="configure-other-debugging-options-cmake-projects"></a>Diğer hata ayıklama seçenekleri (CMake projelerini) yapılandırın

CMake projesi için ek komut satırı bağımsız değişkenleri launch.vs.json dosyasındaki belirtebilirsiniz. Daha fazla bilgi için [CMake proje hata ayıklama](cmake-linux-project.md#debug_cmake_project)

## <a name="debug-with-attach-to-process"></a>İle hata ayıklama iliştirme

[Hata ayıklama](prop-pages/debugging-linux.md) Visual Studio projeleri için özellik sayfası ve **Launch.vs.json** CMake projeleri için ayarlara sahip bir çalışan işleme olanak sağlayan ayarları. Bu ayarları içinde sağlanan ötesinde ek denetim gerekiyorsa, adlı bir dosya yerleştirebilirsiniz `Microsoft.MIEngine.Options.xml` çözümü veya çalışma alanı kökünde. Basit bir örnek aşağıda verilmiştir:

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

**AttachOptionsForConnection** ihtiyacınız olabilecek özniteliklerin çoğu vardır. Yukarıdaki örnekte, ek .so kitaplıkların aranacağı bir konum belirtmek gösterilmektedir. Alt öğe **ServerOptions** gdbserver ile uzak işlem için bunun yerine iliştirmeyi etkinleştirir. Bunu yapmak için (Visual Studio 2017'de sağlanan yukarıda gösterilen) bir yerel gdb istemci ve ikili yerel bir kopya ile belirtmeniz gerekir. **SetupCommands** öğesi gdb komutları doğrudan geçirmenizi sağlar. Kullanılabilir tüm seçenekleri bulabilirsiniz [LaunchOptions.xsd şema](https://github.com/Microsoft/MIEngine/blob/master/src/MICore/LaunchOptions.xsd) GitHub üzerinde.

::: moniker range="vs-2019"

## <a name="separate_build_debug"></a> Derleme ve hata ayıklama için farklı makineler belirtin

Visual Studio 2019 içinde derleme makinesinde uzaktan hata ayıklama makinenizden hem Linux MSBuild tabanlı projeler ve bir uzak Linux makinesinin hedef CMake projelerini sürüm 16.1 uzaktan ayırabilirsiniz. Örneğin, artık x64 üzerinde çapraz-derleme ve IOT senaryoları hedeflenirken ARM cihazına dağıtma.

### <a name="msbuild-based-projects"></a>MSBuild tabanlı projeler

Varsayılan olarak, uzaktan hata ayıklama uzak derleme makinesi ile aynı makinedir (**yapılandırma özellikleri** > **genel** > **uzak derleme makinesi**). Yeni bir uzaktan hata ayıklama makinesi belirtmek için projeyi sağ **Çözüm Gezgini** gidin **yapılandırma özellikleri** > **hata ayıklama**  >  **Uzaktan hata ayıklama makinesi**.  

![Linux uzaktan hata ayıklama makinesi](media/linux-remote-debug-machine.png)

Aşağı açılan menüsünü **uzaktan hata ayıklama makinesi** kurulan tüm uzak bağlantıları doldurulur. Yeni bir uzaktan bağlantı eklemek için gidin **Araçları** > **seçenekleri** > **Çoklu Platform**  >   **Bağlantı Yöneticisi** veya "Bağlantı yöneticisinde" için arama **hızlı başlatma**. Yeni bir uzaktan dağıtma dizini projenin özellik sayfalarındaki belirtebilirsiniz (**yapılandırma özellikleri** > **genel** > **Uzak dizin dağıtma** ).

Varsayılan olarak, yalnızca hata ayıklama işlemi için gerekli dosyaları uzaktan hata ayıklama makineye dağıtılır. Kullanabileceğiniz **Çözüm Gezgini** hangi kaynak yapılandırma dosyaları için uzaktan hata ayıklama makinesi dağıtılır. Kaynak dosyada tıkladığınızda, Çözüm Gezgini'nde hemen altındaki dosya özelliklerini önizlemesini görürsünüz.

![Linux dağıtılabilir dosya](media/linux-deployable-content.png)

**İçerik** özelliği, dosya için uzaktan hata ayıklama makinesi dağıtılan olup olmadığını belirtir. Tamamen giderek dağıtım devre dışı bırakabilirsiniz **özellik sayfaları** > **Configuration Manager** ve işaretini **Dağıt** istenen için yapılandırma.

Bazı durumlarda, projenizin dağıtım hakkında daha fazla denetime gerektirebilir. Örneğin, dağıtmak istediğiniz bazı dosyalar çözümünüzün dışında olabilir veya uzaktan özelleştirmek istediğiniz dosya veya dizini belirten StopFileName başına directory dağıtın. Bu gibi durumlarda, aşağıdaki kod blokları, .vcxproj dosyanıza ekleyin ve "example.cpp" gerçek dosya adlarıyla değiştirin:

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

Bir uzak Linux makinesinin hedef CMake projeleri için yeni bir uzaktan hata ayıklama makinesi launch.vs.json belirtebilirsiniz. Varsayılan olarak, uzak derleme makinenizi karşılık gelen CMakeSettings.json "remoteMachineName" özelliği "remoteMachineName" değerini eşitlenir. Bu özellikler artık eşleşmesi gerekir ve hangi uzak makineye dağıtma ve hata ayıklama için kullanılan launch.vs.json "remoteMachineName" değerini gösterecektir.

![CMake uzaktan hata ayıklama makinesi](media/cmake-remote-debug-machine.png)

IntelliSense, tüm oluşturulmuş tüm uzak bağlantılar listesi önerir. Giderek yeni bir uzaktan bağlantı ekleyebilirsiniz **Araçları** > **seçenekleri** > **Çoklu Platform**  >   **Bağlantı Yöneticisi** veya "İçin Bağlantı Yöneticisi" aranıyor **hızlı başlatma**.

Dağıtımınızı üzerinde tam denetim istiyorsanız, launch.vs.json dosyasına aşağıdaki kod blokları ekleyebilirsiniz. Yer tutucu değerlerini gerçek değerlerle değiştirin unutmayın:

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

- ARM cihazları, Linux üzerinde hata ayıklamak için bu blog gönderisini inceleyin: [Katıştırılmış bir ARM cihazı Visual Studio'da hata ayıklama](https://blogs.msdn.microsoft.com/vcblog/2018/01/10/debugging-an-embedded-arm-device-in-visual-studio/).

## <a name="see-also"></a>Ayrıca bkz.

[C++ hata ayıklama özellikleri (Linux C++)](prop-pages/debugging-linux.md)
