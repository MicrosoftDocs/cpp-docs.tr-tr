---
title: MFC kitaplığını yeniden dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, redistributing
- redistributing MFC library
ms.assetid: 72714ce1-385e-4c1c-afa5-96b03e873866
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19a49bf18721f605abe0c6e496d3532012c9c92c
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33340404"
---
# <a name="redistributing-the-mfc-library"></a>MFC Kitaplığını Yeniden Dağıtma
MFC kitaplığını uygulamanıza dinamik olarak bağlantı varsa, eşleşen MFC DLL yeniden dağıtmanız gerekir. MFC uygulamanızı Visual Studio 2015 ile birlikte gelen MFC sürümünü kullanarak oluşturulursa, örneğin, size mfc140.dll veya uygulamanızın dar karakter veya Unicode desteği için derlenmiş olan bağlı olarak mfc140u.dll yeniden dağıtmanız gerekir.  
  
> [!NOTE]
>  Mfc140.dll dosyaları, Visual Studio 2015 RTM yeniden dağıtılabilir dosyaları dizininden atlanmış. Bunun yerine Visual Studio 2015 tarafından Windows\system32 ve Windows\syswow64 dizinlerde yüklü sürümleri kullanabilirsiniz.  
  
 Tüm MFC DLL'leri C çalışma zamanı kitaplığı (CRT) paylaşılan sürümünü kullandığından, CRT yeniden dağıtmanız gerekebilir. Visual Studio 2015 ile birlikte gelen MFC sürümü Windows 10 bir parçası olarak dağıtılmış Evrensel CRT kitaplığını kullanır. Önceki Windows sürümlerinde Visual Studio 2015 kullanılarak oluşturulmuş bir MFC uygulamayı çalıştırmak için evrensel CRT yeniden dağıtmanız gerekir. İşletim sisteminin bir bileşeni olarak veya yerel dağıtım kullanarak evrensel CRT dağıtan hakkında daha fazla bilgi için bkz: [Evrensel CRT Tanıtımı](http://go.microsoft.com/fwlink/p/?linkid=617977). Windows'un desteklenen sürümlerindeki merkezi dağıtım için bkz: Evrensel CRT indirmek için bkz: [Windows 10 Universal C çalışma zamanı](http://go.microsoft.com/fwlink/p/?LinkId=619489). Ucrtbase.dll yerel dağıtım için yeniden dağıtılabilir mimarisi özgü sürümleri, Windows SDK'ın bulunur. Varsayılan olarak, Visual Studio mimari özgü alt dizinde bunları C:\Program Files (x86) \Windows Kits\10\Redist\ucrt\DLLs\ yükler.  
  
 MFC kitaplığını önceki bir sürümünü kullanarak uygulamanızı oluşturulursa, yeniden dağıtılabilir dosyaları dizininden eşleşen CRT DLL yeniden dağıtmanız gerekir. Örneğin, Visual Studio 2013 (vc120) araç setini kullanarak MFC uygulamanız oluşturulursa, msvcr120.dll yeniden dağıtmanız gerekir. Eşleşen mfc yeniden dağıtmak de`<version>`u.dll ya da mfc`<version>`.dll.  
  
 MFC uygulamanıza statik olarak bağlarsanız (diğer bir deyişle, belirtirseniz **bir statik kitaplık kullanımı MFC'de** üzerinde **genel** sekmesinde **özellik sayfaları** iletişim kutusu), yok MFC DLL yeniden dağıtmak için. Ancak, statik bağlama test etmek için işe yarayabilir olsa da ve iç dağıtım uygulamaların öneririz, onu MFC'yi yeniden kullanmanızı değil. Visual C++ kitaplıkları dağıtımı için önerilen strateji hakkında daha fazla bilgi için bkz: [dağıtım yöntemi seçme](../ide/choosing-a-deployment-method.md).  
  
 Uygulamanızın WebBrowser denetimi MFC sınıfları kullanıyorsa (örneğin, [CHtmlView sınıfı](../mfc/reference/chtmlview-class.md) veya [CHtmlEditView sınıfı](../mfc/reference/chtmleditview-class.md)), ayrıca en son sürümünü yüklemenizi öneririz Microsoft Internet Explorer böylece hedef bilgisayarın en güncel ortak denetim dosyalarına sahip olur. (En azından, Internet Explorer 4.0 gereklidir.) Internet Explorer bileşenlerini yükleme hakkında bilgi "Makale 185375: nasıl için oluşturma bir tek EXE yüklemek, Internet Explorer'da" Microsoft Support Web sitesinde mevcuttur.  
  
 Uygulamanız MFC veritabanı sınıfları kullanıyorsa (örneğin, [CRecordset sınıfı](../mfc/reference/crecordset-class.md) ve [CRecordView sınıfı](../mfc/reference/crecordview-class.md)), ODBC ve uygulamanızı kullanan herhangi bir ODBC sürücüsünü yeniden dağıtmanız gerekir. Daha fazla bilgi için bkz: [veritabanı destek dosyalarını yeniden dağıtma](../ide/redistributing-database-support-files.md).  
  
 MFC uygulamanız Windows Forms denetimleri kullanıyorsa, uygulamanızla mfcmifc80.dll'ye yeniden dağıtmanız gerekir. Bu DLL, kendi uygulama yerel klasöründe veya kullanarak genel derleme önbelleği (GAC) dağıtarak bir uygulama ile dağıtılabilir güçlü ad imzalı bir .NET derlemesi olduğunu [Gacutil.exe (Genel Derleme Önbelleği Aracı)](/dotnet/framework/tools/gacutil-exe-gac-tool).  
  
 MFC DLL dağıtırsanız perakende sürümü ve hata ayıklama sürümü yeniden dağıtmak emin olun. DLL'lerde hata ayıklama sürümleri dağıtılamaz. MFC DLL'leri hata ayıklama sürümleri adları "d", örneğin, Mfc140d.dll sonlandırın.  
  
 MFC ya da VCRedist_ kullanarak dağıtabilirsiniz*mimarisi*.exe, Visual Studio ile veya uygulamanızla aynı klasöre MFC DLL dağıtarak yüklü birleştirme modülleri. Yeniden MFC dağıtma hakkında daha fazla bilgi için bkz: [Visual C++ dosyalarını yeniden dağıtma](../ide/redistributing-visual-cpp-files.md).  
  
## <a name="installation-of-localized-mfc-components"></a>Yerelleştirilmiş MFC bileşenlerini yükleme  
 MFC yerelleştirme DLL'i yükleyerek uygulamanızı yerelleştirme karar verirseniz, yeniden dağıtılabilir birleştirme dosyaları (.msm) kullanmanız gerekir. Uygulamanızı bir x86 üzerinde yerelleştirme istiyorsanız, örneğin, bilgisayar, Microsoft_VC birleştirme gerekir`<version>`x x86 için yükleme paketi içine _MFCLOC_x86.msm bilgisayar.  
  
 Yeniden dağıtılabilir .msm dosyaları yerelleştirme için kullanılan DLL'ler içerir. Desteklenen her dil için bir DLL yoktur. Yükleme işlemi, hedef bilgisayarda %windir%\system32\ klasöründe bu DLL'ler yükler.  
  
 MFC uygulamaları yerelleştirme hakkında daha fazla bilgi için bkz: [TN057: MFC bileşenlerini yerelleştirme](../mfc/tn057-localization-of-mfc-components.md)hem de [makale 208983: MFC LOC DLL'leri kullanma nasıl](http://go.microsoft.com/fwlink/p/?linkid=198025) Microsoft Support Web sitesinde.  
  
 MFC DLL uygulama yerel klasörüne dağıtarak MFC yerelleştirme DLL'lerini yeniden dağıtabilirsiniz. Yeniden Visual C++ kitaplıkları dağıtma hakkında daha fazla bilgi için bkz: [Visual C++ dosyalarını yeniden dağıtma](../ide/redistributing-visual-cpp-files.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ Dosyalarını Yeniden Dağıtma](../ide/redistributing-visual-cpp-files.md)