---
title: C++Özellik sayfalarında hata ayıklama
ms.date: 07/24/2019
ms.topic: article
ms.assetid: 78115a6b-3799-4515-814e-8566b5bdc55d
f1_keywords:
- VC.Project.IVCLocalDebugPageObject.Command
- VC.Project.IVCLocalDebugPageObject.CommandArguments
- VC.Project.IVCLocalDebugPageObject.WorkingDirectory
- VC.Project.IVCLocalDebugPageObject.Attach
- VC.Project.IVCLocalDebugPageObject.DebuggerType
- VC.Project.IVCLocalDebugPageObject.Environment
- VC.Project.IVCLocalDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCLocalDebugPageObject.GPUBreakOnAllThreads
- VC.Project.IVCLocalDebugPageObject.EnvironmentMerge
- VC.Project.IVCLocalDebugPageObject.SQLDebugging
- VC.Project.IVCLocalDebugPageObject.AmpDefaultAccelerator
- VC.Project.IVCRemoteDebugPageObject.RemoteCommand
- VC.Project.IVCRemoteDebugPageObject.CommandArguments
- VC.Project.IVCRemoteDebugPageObject.WorkingDirectory
- VC.Project.IVCRemoteDebugPageObject.RemoteMachine
- VC.Project.IVCRemoteDebugPageObject.Remote
- VC.Project.IVCRemoteDebugPageObject.DebuggerType
- VC.Project.IVCRemoteDebugPageObject.Environment
- VC.Project.IVCRemoteDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCRemoteDebugPageObject.GPUBreakOnAllThreads
- VC.Project.IVCRemoteDebugPageObject.Attach
- VC.Project.IVCRemoteDebugPageObject.SQLDebugging
- VC.Project.IVCRemoteDebugPageObject.DeploymentDirectory
- VC.Project.IVCRemoteDebugPageObject.AdditionalFiles
- VC.Project.IVCRemoteDebugPageObject.Remote
- VC.Project.IVCRemoteDebugPageObject.AmpDefaultAccelerator
- VC.Project.VCDebugSettings.WebBrowser.WebBrowserDebuggerHttpUrl
- VC.Project.VCDebugSettings.WebBrowser.DebuggerType
- VC.Project.IVCWebSvcDebugPageObject.HttpUrl
- VC.Project.IVCWebSvcDebugPageObject.DebuggerType
- VC.Project.IVCWebSvcDebugPageObject.SQLDebugging
ms.openlocfilehash: 5f7a7bc0e2c696365daa38696fde6f1a480644b4
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927730"
---
# <a name="c-debugging-property-pages"></a>C++Özellik sayfalarında hata ayıklama

Bu özellik sayfaları **Proje** > **özellikleri** > **yapılandırma özellikleri** > **hata ayıklama**altında bulunur. Açılan denetimde hata ayıklayıcı türünü seçin. Hata ayıklama C++ kodu hakkında daha fazla bilgi için [bkz. Öğretici: Visual Studio](/visualstudio/debugger/getting-started-with-the-debugger-cpp) kullanarak C++ kodun hata [ayıklamasını ve yerel kod hatalarını ayıklamayı](/visualstudio/debugger/debugging-native-code)öğrenin.

## <a name="local-windows-debugger-property-page"></a>Yerel Windows hata ayıklayıcısı Özellik sayfası

### <a name="command"></a>Komut

Yürütülecek hata ayıklama komutu.

### <a name="command-arguments"></a>Komut bağımsız değişkenleri

Uygulamaya geçirilecek komut satırı bağımsız değişkenleri.

### <a name="working-directory"></a>Çalışma dizini

Uygulamanın çalışma dizini. Varsayılan olarak, proje dosyasını içeren dizin.

### <a name="attach"></a>İliştir

Hata ayıklama başladığında hata ayıklayıcının varolan bir işleme iliştirmeye çalışıp çalışmadığını belirtir.

### <a name="debugger-type"></a>Hata ayıklayıcı türü

Kullanılacak hata ayıklayıcı türünü belirtir. Auto olarak ayarlandığında, hata ayıklayıcı türü exe dosyasının içeriğine göre seçilir.

**Yapabileceği**

- Yalnızca **Yerel** -yerel
- Yalnızca **yönetilen** -yönetilen
- **Karma** karışık
- **Otomatik** otomatik
- **Betik** betiği
- **Yalnızca GPU (C++ amp)** -yalnızca GPU (C++ amp)

### <a name="environment"></a>Ortam

Hata Ayıklanacak programın ortamını veya mevcut ortamla birleştirilecek değişkenleri belirtir.

### <a name="debugging-accelerator-type"></a>Hata ayıklama Hızlandırıcı türü

GPU kodunda hata ayıklamak için kullanılacak hata ayıklama Hızlandırıcı türü. (GPU hata ayıklayıcısı etkinken kullanılabilir.)

### <a name="gpu-default-breakpoint-behavior"></a>GPU Varsayılan kesme noktası davranışı

GPU hata ayıklayıcının ne sıklıkta bölüneceğini ayarlar.

**Yapabileceği**

- Çarpıt başına her çarpıtma için **bir kez kes**
- Her iş parçacığı için **Kes (CPU davranışı gibi)** -her iş parçacığı için kesme (CPU davranışı gibi)

### <a name="merge-environment"></a>Ortamı Birleştir

Belirtilen ortam değişkenlerini mevcut ortamla birleştirin.

### <a name="sql-debugging"></a>SQL hata ayıklaması

SQL hata ayıklayıcısını iliştirin.

### <a name="amp-default-accelerator"></a>Amp varsayılan Hızlandırıcı

AMP C++ varsayılan Hızlandırıcı seçimini geçersiz kılar. Yönetilen kodda hata ayıklanırken Özellik uygulanmaz.

## <a name="remote-windows-debugger-property-page"></a>Uzak Windows hata ayıklayıcısı Özellik sayfası

Uzaktan hata ayıklama hakkında daha fazla bilgi için bkz. [Visual Studio C++ 'da bir Visual projesinde uzaktan hata ayıklama](/visualstudio/debugger/remote-debugging-cpp).

### <a name="remote-command"></a>Uzak komut

Yürütülecek hata ayıklama komutu.

### <a name="remote-command-arguments"></a>Uzak komut bağımsız değişkenleri

Uygulamaya geçirilecek komut satırı bağımsız değişkenleri.

### <a name="working-directory"></a>Çalışma dizini

Uygulamanın çalışma dizini. Varsayılan olarak, proje dosyasını içeren dizin.

### <a name="remote-server-name"></a>Uzak sunucu adı

Uzak sunucu adını belirtir.

### <a name="connection"></a>Bağlantı

Bağlantı türünü belirtir.

**Yapabileceği**

- Windows [kimlik doğrulaması ile](/windows-server/security/windows-authentication/windows-authentication-overview)uzaktan **Windows kimlik doğrulaması ile** uzaktan.
- Kimlik doğrulaması olmadan uzak uzaktan **kimlik doğrulaması yok** .

### <a name="debugger-type"></a>Hata ayıklayıcı türü

Kullanılacak hata ayıklayıcı türünü belirtir. Auto olarak ayarlandığında, hata ayıklayıcı türü exe dosyasının içeriğine göre seçilir.

**Yapabileceği**

- Yalnızca **Yerel** -yerel
- Yalnızca **yönetilen** -yönetilen
- **Karma** karışık
- **Otomatik** otomatik
- **Betik** betiği
- **Yalnızca GPU (C++ amp)** -yalnızca GPU (C++ amp)

### <a name="environment"></a>Ortam

Hata Ayıklanacak programın ortamını veya mevcut ortamla birleştirilecek değişkenleri belirtir.

### <a name="debugging-accelerator-type"></a>Hata ayıklama Hızlandırıcı türü

GPU kodunda hata ayıklamak için kullanılacak hata ayıklama Hızlandırıcı türü. (GPU hata ayıklayıcısı etkinken kullanılabilir.)

### <a name="gpu-default-breakpoint-behavior"></a>GPU Varsayılan kesme noktası davranışı

GPU hata ayıklayıcının ne sıklıkta bölüneceğini ayarlar.

**Yapabileceği**

- Çarpıt başına her çarpıtma için **bir kez kes**
- Her iş parçacığı için **Kes (CPU davranışı gibi)** -her iş parçacığı için kesme (CPU davranışı gibi)

### <a name="attach"></a>İliştir

Hata ayıklama başladığında hata ayıklayıcının varolan bir işleme iliştirmeye çalışıp çalışmadığını belirtir.

### <a name="sql-debugging"></a>SQL hata ayıklaması

SQL hata ayıklayıcısını iliştirin.

### <a name="deployment-directory"></a>Dağıtım dizini

Uzak makinede hata ayıklarken, proje çıktısı içeriğinin (PDB dosyaları hariç) uzak makineye kopyalanmasını isterseniz yolu burada belirtin.

### <a name="additional-files-to-deploy"></a>Dağıtılacak ek dosyalar

Bir uzak makinede hata ayıklanırken burada belirtilen dosyalar ve dizinler (proje çıkışının yanı sıra) belirtilmişse dağıtım dizinine kopyalanır.

### <a name="deploy-visual-c-debug-runtime-libraries"></a>Visual C++ hata ayıklama çalışma zamanı kitaplıklarını dağıtma

Etkin platform (Win32, x64 veya ARM) için hata ayıklama çalışma zamanı kitaplıklarını dağıtıp dağıtmeyeceğinizi belirtir.

### <a name="amp-default-accelerator"></a>Amp varsayılan Hızlandırıcı

AMP C++ varsayılan Hızlandırıcı seçimini geçersiz kılar. Yönetilen kodda hata ayıklanırken Özellik uygulanmaz.

## <a name="web-browser-debugger-property-page"></a>Web tarayıcısı hata ayıklayıcısı Özellik sayfası

### <a name="http-url"></a>HTTP URL 'SI

Projenin URL 'sini belirtir.

### <a name="debugger-type"></a>Hata ayıklayıcı türü

Kullanılacak hata ayıklayıcı türünü belirtir. Auto olarak ayarlandığında, hata ayıklayıcı türü exe dosyasının içeriğine göre seçilir.

**Yapabileceği**

- Yalnızca **Yerel** -yerel
- Yalnızca **yönetilen** -yönetilen
- **Karma** karışık
- **Otomatik** otomatik
- **Betik** betiği

## <a name="web-service-debugger-property-page"></a>Web hizmeti hata ayıklayıcısı Özellik sayfası

### <a name="http-url"></a>HTTP URL 'SI

Projenin URL 'sini belirtir.

### <a name="debugger-type"></a>Hata ayıklayıcı türü

Kullanılacak hata ayıklayıcı türünü belirtir. Auto olarak ayarlandığında, hata ayıklayıcı türü exe dosyasının içeriğine göre seçilir.

**Yapabileceği**

- Yalnızca **Yerel** -yerel
- Yalnızca **yönetilen** -yönetilen
- **Karma** karışık
- **Otomatik** otomatik
- **Betik** betiği

### <a name="sql-debugging"></a>SQL hata ayıklaması

SQL hata ayıklayıcısını iliştirin.