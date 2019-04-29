---
title: MFC Kitaplığını Yeniden Dağıtma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, redistributing
- redistributing MFC library
ms.assetid: 72714ce1-385e-4c1c-afa5-96b03e873866
ms.openlocfilehash: faca2e7213ab0ad0c9b1a1a0fd6a7274094853f1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362232"
---
# <a name="redistributing-the-mfc-library"></a>MFC Kitaplığını Yeniden Dağıtma

Uygulamanızı MFC kitaplığına dinamik olarak bağlarsanız, eşleşen MFC DLL'yi yeniden dağıtmanız gerekir. MFC uygulamanızı Visual Studio 2015 ile birlikte gelen MFC sürümü kullanılarak oluşturulmuşsa, örneğin, mfc140.dll veya uygulamanızı dar karakter veya Unicode desteği için derlenmiş olan bağlı olarak mfc140u.dll, yeniden dağıtmanız gerekir.

> [!NOTE]
>  Visual Studio 2015 RTM yeniden dağıtılabilir dosyaları dizininden mfc140.dll dosyaları göz ardı. Visual Studio 2015 tarihine kadar Windows\system32 ve Windows\syswow64 dizinler bunun yerine yüklü sürümlerini kullanabilirsiniz.

MFC DLL'lerinin hepsi C çalışma zamanı kitaplığı (CRT) paylaşılan sürümünü kullandığından, CRT yeniden dağıtmanız gerekebilir. Visual Studio 2015 ile birlikte gelen MFC sürümü, Windows 10 'un bir parçası olarak dağıtılmış Evrensel CRT kitaplığını kullanır. Önceki Windows sürümlerinde Visual Studio 2015 kullanılarak oluşturulan bir MFC uygulaması çalıştırmak için evrensel CRT yeniden dağıtmanız gerekir. İşletim sisteminin bir bileşeni olarak veya yerel dağıtımını kullanarak evrensel CRT dağıtılacağı hakkında daha fazla bilgi için bkz. [Evrensel CRT giriş](https://devblogs.microsoft.com/cppblog/introducing-the-universal-crt/). Desteklenen Windows sürümleri üzerinde merkezi dağıtım için bkz: Evrensel CRT indirmek için bkz [Windows 10 Evrensel C çalışma zamanı](https://www.microsoft.com/en-us/download/details.aspx?id=48234). Ucrtbase.dll yerel dağıtımı için yeniden dağıtılabilir mimariye özgü sürümleri, Windows SDK'da bulunur. Varsayılan olarak, Visual Studio bu C:\Program Files (x86) \Windows Kits\10\Redist\ucrt\DLLs\ mimariye özgü alt dizinde yükler.

Uygulamanız MFC Kitaplığı'nın önceki bir sürümü kullanılarak oluşturulmuşsa, yeniden dağıtılabilir dosyaları dizininden eşleşen CRT DLL yeniden dağıtmanız gerekir. Örneğin, Visual Studio 2013 (vc120) araç takımı kullanarak MFC uygulamanızı oluşturdunuz, msvcr120.dll yeniden dağıtmanız gerekir. Eşleşen MFC'yi yeniden de`<version>`u.dll ya da mfc`<version>`.dll.

MFC uygulamanıza statik olarak bağlarsanız (diğer bir deyişle, belirtirseniz **MFC'yi statik kitaplıkta** üzerinde **genel** sekmesinde **özellik sayfaları** iletişim kutusu), erişiminiz yok bir MFC DLL'sini yeniden için. Ancak, statik bağlama test etmek için işe yarasa da ve iç dağıtım uygulamaların, bunu MFC'yi yeniden kullanmanız önerilir değil. Visual C++ kitaplarının dağıtımı için önerilen stratejiler hakkında daha fazla bilgi için bkz: [dağıtım yöntemi seçme](choosing-a-deployment-method.md).

Uygulamanız WebBrowser denetimi ekleyen MFC sınıfları kullanıyorsa (örneğin, [CHtmlView sınıfı](../mfc/reference/chtmlview-class.md) veya [CHtmlEditView sınıfı](../mfc/reference/chtmleditview-class.md)), ayrıca en son sürümünü yüklemenizi öneririz Microsoft Internet Explorer böylece hedef bilgisayarın en güncel ortak denetim dosyalarına sahip olur. (En azından, Internet Explorer 4.0 gereklidir.) Internet Explorer bileşenlerini yükleme hakkında bilgi sağlanmıştır "makale 185375: Nasıl oluşturmak için tek bir EXE yükle Internet Explorer'ın "Microsoft Support Web sitesinde.

Uygulamanız MFC veritabanı sınıflarını kullanıyorsa (örneğin, [CRecordset sınıfı](../mfc/reference/crecordset-class.md) ve [CRecordView sınıfı](../mfc/reference/crecordview-class.md)), ODBC ve uygulamanızın kullandığı ODBC sürücülerini yeniden dağıtmanız gerekir.

MFC uygulamanız Windows Forms denetimleri kullanıyorsa, mfcmifc80.dll'ye uygulamanızla birlikte yeniden dağıtmanız gerekir. Bu DLL, kendi uygulama yerel klasöründe veya kullanılarak Genel Derleme Önbelleği (GAC) dağıtarak bir uygulama ile dağıtılabilir kesin ad imzalı bir .NET derlemesi olduğundan [Gacutil.exe (Genel Derleme Önbelleği Aracı)](/dotnet/framework/tools/gacutil-exe-gac-tool).

Bir MFC DLL'sini yeniden dağıtıyorsanız perakende sürümü ve hata ayıklama sürümü olmayan yeniden dağıttığınızdan emin olun. DLL'lerin hata ayıklama sürümleri yeniden dağıtılamaz. MFC DLL'lerin hata ayıklama sürümlerinin adları "d", örneğin, Mfc140d.dll sonlandırın.

MFC ya da VCRedist_ kullanarak dağıtabilirsiniz*mimarisi*.exe, uygulamanızla aynı klasöre MFC DLL'yi dağıtarak veya Visual Studio ile yüklenen birleştirme modüllerini. MFC'yi yeniden dağıtma hakkında daha fazla bilgi için bkz. [Visual C++ dosyalarını yeniden dağıtma](redistributing-visual-cpp-files.md).

## <a name="installation-of-localized-mfc-components"></a>Yerelleştirilmiş MFC bileşenlerini yükleme

Uygulamanız bir MFC yerelleştirme DLL'i yükleyerek yerelleştirmeye karar verirseniz, yeniden dağıtılabilir birleştirme dosyaları (.msm) kullanmanız gerekir. Örneğin, uygulamanızın bir x86 yerelleştirmek istiyorsanız bilgisayar Microsoft_VC birleştirme gerekir`<version>`_MFCLOC_x86.msm x x86 yükleme paketi içinde bilgisayar.

Yeniden dağıtılabilir .msm dosyaları yerelleştirme için kullanılan dll öğelerini içerir. Desteklenen her dil için bir DLL yoktur. Yükleme işlemi, bu DLL'leri hedef bilgisayarda %windir%\system32\ klasörüne yükler.

MFC uygulamalarının yerelleştirilmesi hakkında daha fazla bilgi için bkz. [TN057: MFC bileşenlerini yerelleştirme](../mfc/tn057-localization-of-mfc-components.md).

Uygulama yerel klasörünüzdeki MFC DLL'yi dağıtarak MFC yerelleştirme DLL'lerini yeniden dağıtabilirsiniz. Visual C++ kütüphanelerini yeniden dağıtma hakkında daha fazla bilgi için bkz. [Visual C++ dosyalarını yeniden dağıtma](redistributing-visual-cpp-files.md).

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Dosyalarını Yeniden Dağıtma](redistributing-visual-cpp-files.md)
