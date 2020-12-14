---
description: 'Daha fazla bilgi edinin: MFC kitaplığını yeniden dağıtma'
title: MFC Kitaplığını Yeniden Dağıtma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, redistributing
- redistributing MFC library
ms.assetid: 72714ce1-385e-4c1c-afa5-96b03e873866
ms.openlocfilehash: 7089b7000d3a9d397291379e47da6b49c4c9da71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247364"
---
# <a name="redistributing-the-mfc-library"></a>MFC Kitaplığını Yeniden Dağıtma

Uygulamanızı MFC kitaplığına dinamik olarak bağlarsanız, eşleşen MFC DLL 'sini yeniden dağıtmanız gerekir. Örneğin, MFC uygulamanız Visual Studio 2015 ile birlikte gelen MFC sürümü kullanılarak derlenmişse, uygulamanızın dar karakterler veya Unicode desteği için derlendiğine bağlı olarak mfc140.dll veya mfc140u.dll yeniden dağıtmanız gerekir.

> [!NOTE]
> mfc140.dll dosyalar, Visual Studio 2015 RTM içindeki yeniden dağıtılabilir dosyalar dizininden atlanmıştı. Bunun yerine, Visual Studio 2015 tarafından yüklenen sürümleri Windows\System32 ve Windows\syswow64 dizinlerinde kullanabilirsiniz.

Tüm MFC DLL 'Leri C çalışma zamanı kitaplığı 'nın (CRT) paylaşılan sürümünü kullandığından, CRT 'yi yeniden dağıtmanız de gerekebilir. Visual Studio 2015 ile birlikte gelen MFC sürümü, Windows 10 ' un bir parçası olarak dağıtılan Universal CRT kitaplığını kullanır. Windows 'un önceki sürümlerinde Visual Studio 2015 kullanılarak oluşturulan bir MFC uygulamasını çalıştırmak için Evrensel CRT 'yi yeniden dağıtmanız gerekir. Evrensel CRT 'yi bir işletim sistemi bileşeni olarak veya yerel dağıtım kullanarak yeniden dağıtma hakkında daha fazla bilgi için bkz. [UNIVERSAL CRT 'ye giriş](https://devblogs.microsoft.com/cppblog/introducing-the-universal-crt/). Windows 'un desteklenen sürümlerinde merkezi dağıtım için Universal CRT 'yi indirmek için bkz. [Windows 10 Universal C çalışma zamanı](https://www.microsoft.com/download/details.aspx?id=48234). Yerel dağıtım için ucrtbase.dll yeniden dağıtılabilir mimariye özgü sürümleri Windows SDK bulunur. Varsayılan olarak, Visual Studio bunları mimariye özgü bir alt dizinde C:\Program Files (x86) \Windows Kits\10\Redist\ucrt\DLLs\ dizinine yüklenir.

Uygulamanız MFC kitaplığının önceki bir sürümü kullanılarak derlendikten sonra, eşleşen CRT DLL 'yi yeniden dağıtılabilir dosyalar dizininden yeniden dağıtmanız gerekir. Örneğin, MFC uygulamanız Visual Studio 2013 (vc120) araç kümesi kullanılarak derlenip, msvcr120.dll yeniden dağıtmanız gerekir. Ayrıca, eşleşen MFC `<version>`u.dll veya MFC. dll ' ye yeniden dağıtmanız gerekir `<version>` .

Uygulamanızı MFC 'ye statik olarak bağlarsanız (yani, **Özellik sayfaları** Iletişim kutusundaki **genel** sekmesinde **MFC 'yi statik kitaplıkta kullan** SEÇENEĞINI belirtirseniz), bir MFC DLL 'yi yeniden dağıtmanız gerekmez. Ancak, statik bağlama uygulamaların test ve iç dağıtımı için çalışabilse de, MFC 'yi yeniden dağıtmak için bunu kullanmanızı öneririz. Visual C++ kitaplıklarını dağıtmaya yönelik önerilen stratejiler hakkında daha fazla bilgi için bkz. [dağıtım yöntemi seçme](choosing-a-deployment-method.md).

Uygulamanız WebBrowser denetimini uygulayan MFC sınıflarını kullanıyorsa (örneğin, [CHtmlView sınıfı](../mfc/reference/chtmlview-class.md) veya [CHtmlEditView sınıfı](../mfc/reference/chtmleditview-class.md)), hedef bilgisayar en güncel ortak denetim dosyalarına sahip olacak şekilde Microsoft Internet Explorer 'ın en güncel sürümünü de yüklemenizi öneririz. (En azından, Internet Explorer 4,0 gereklidir.) Internet Explorer bileşenlerinin nasıl yükleneceğine ilişkin bilgiler, Microsoft Desteği Web sitesinde "Makale 185375: Internet Explorer 'ın tek EXE yüklemesi oluşturma" makalesinde bulunabilir.

Uygulamanız MFC veritabanı sınıflarını (örneğin, [CRecordset sınıfı](../mfc/reference/crecordset-class.md) ve [CRecordView sınıfı](../mfc/reference/crecordview-class.md)) kullanıyorsa, ODBC 'YI ve uygulamanızın kullandığı ODBC sürücülerini yeniden dağıtmanız gerekir.

MFC uygulamanız Windows Forms denetimleri kullanıyorsa, mfcmifc80.dll uygulamanızla yeniden dağıtmanız gerekir. Bu DLL, uygulamanın yerel klasöründeki bir uygulamayla veya [Gacutil.exe (genel bütünleştirilmiş kod önbelleği aracı)](/dotnet/framework/tools/gacutil-exe-gac-tool)kullanarak genel derleme önbelleği 'NE (GAC) dağıtarak yeniden dağıtılabilir bir güçlü ad imzalı .net derlemesidir.

Bir MFC DLL 'yi yeniden dağıtırsanız, hata ayıklama sürümünü değil, perakende sürümünü yeniden dağıttığınızdan emin olun. Dll 'lerin hata ayıklama sürümleri yeniden dağıtılabilir değildir. MFC DLL 'lerinin hata ayıklama sürümlerinin adları bir "d" ile biter, örneğin Mfc140d.dll.

MFC 'yi VCRedist_ *mimari*. exe ' yi kullanarak, Visual Studio ile yüklenen birleştirme MODÜLLERINI veya MFC DLL 'yi uygulamanızla aynı klasöre dağıtarak yeniden dağıtabilirsiniz. MFC 'yi yeniden dağıtma hakkında daha fazla bilgi için bkz. [Visual C++ dosyalarını yeniden dağıtma](redistributing-visual-cpp-files.md).

## <a name="installation-of-localized-mfc-components"></a>Yerelleştirilmiş MFC Bileşenlerinin Yüklenmesi

Uygulamanızı bir MFC yerelleştirme DLL 'SI yükleyerek yerelleştirmeye karar verirseniz, yeniden dağıtılabilir birleştirme dosyalarını (. msm) kullanmanız gerekir. Örneğin, uygulamanızı bir x86 bilgisayarda yerelleştirmek isterseniz, `<version>` bir x86 bilgisayar için Microsoft_VC _MFCLOC_x86. msm ' i yükleme paketine birleştirmeniz gerekir.

Yeniden dağıtılabilir. msm dosyaları, yerelleştirme için kullanılan dll 'Leri içerir. Desteklenen her dil için bir DLL vardır. Yükleme işlemi, bu DLL 'Leri hedef bilgisayardaki%windir%\system32\ klasörüne yüklenir.

MFC uygulamalarının yerelleştirilmesi hakkında daha fazla bilgi için bkz. [TN057: MFC bileşenlerini yerelleştirme](../mfc/tn057-localization-of-mfc-components.md).

MFC DLL 'sini uygulama yerel klasörünüzde dağıtarak MFC yerelleştirme dll 'Lerini yeniden dağıtabilirsiniz. Visual C++ kitaplıklarını yeniden dağıtma hakkında daha fazla bilgi için bkz. [Visual C++ dosyalarını yeniden dağıtma](redistributing-visual-cpp-files.md).

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Dosyalarını Yeniden Dağıtma](redistributing-visual-cpp-files.md)
