---
title: MFC Kitaplığını Yeniden Dağıtma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, redistributing
- redistributing MFC library
ms.assetid: 72714ce1-385e-4c1c-afa5-96b03e873866
ms.openlocfilehash: e1434bee6d134d4c02b2c06125d340a68a6c305d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359898"
---
# <a name="redistributing-the-mfc-library"></a>MFC Kitaplığını Yeniden Dağıtma

Uygulamanızı Dinamik olarak MFC kitaplığına bağlarsanız, eşleşen MFC DLL'yi yeniden dağıtmanız gerekir. Örneğin, MFC uygulamanız Visual Studio 2015 ile birlikte gönderen MFC sürümünü kullanarak oluşturulmuşsa, uygulamanızın dar karakterler veya Unicode desteği için derlenip derlenmediğine bağlı olarak mfc140.dll veya mfc140u.dll'yi yeniden dağıtmanız gerekir.

> [!NOTE]
> mfc140.dll dosyaları Visual Studio 2015 RTM'deki yeniden dağıtılabilir dosya dizininden çıkarıldı. Visual Studio 2015 tarafından yüklenen sürümleri Windows\system32 ve Windows\syswow64 dizinlerinde kullanabilirsiniz.

Tüm MFC DL'ler C çalışma zamanı kitaplığı (CRT) paylaşılan sürümünü kullandığından, CRT'yi yeniden dağıtmanız da gerekebilir. Visual Studio 2015 ile birlikte gelen MFC sürümü, Windows 10'un bir parçası olarak dağıtılan evrensel CRT kitaplığını kullanır. Windows'un önceki sürümlerinde Visual Studio 2015 kullanılarak oluşturulmuş bir MFC uygulamasını çalıştırmak için Evrensel CRT'yi yeniden dağıtmanız gerekir. Evrensel CRT'nin işletim sistemi bileşeni olarak veya yerel dağıtım kullanılarak nasıl yeniden dağıtılanacınız hakkında bilgi [için](https://devblogs.microsoft.com/cppblog/introducing-the-universal-crt/)bkz. Windows'un desteklenen sürümlerinde merkezi dağıtım için evrensel CRT'yi indirmek için [Windows 10 Universal C Runtime'a](https://www.microsoft.com/download/details.aspx?id=48234)bakın. Yerel dağıtım için ucrtbase.dll'nin yeniden dağıtılabilir mimariye özgü sürümleri Windows SDK'da bulunur. Varsayılan olarak Visual Studio bunları C:\Program Files (x86)\Windows Kitleri\10\Redist\ucrt\DLLs\ olarak mimariye özgü bir alt dizine yükler.

Uygulamanız MFC kitaplığı önceki bir sürümünü kullanarak inşa edilirse, eşleşen CRT DLL'yi yeniden dağıtılabilir dosyalar dizininden yeniden dağıtmanız gerekir. Örneğin, MFC uygulamanız Visual Studio 2013 (vc120) araç kümesini kullanarak oluşturulmuşsa, msvcr120.dll'yi yeniden dağıtmanız gerekir. Ayrıca eşleşen mfc`<version>`u.dll veya mfc`<version>`.dll yeniden dağıtmak zorunda.

Uygulamanızı statik olarak MFC'ye bağlarsanız (diğer bir deyişle, **Özellik Sayfaları** iletişim kutusundaki **Genel** **sekmesinde Statik Kitaplıkta MFC kullanın'ı** belirtirseniz), bir MFC DLL'yi yeniden dağıtmanız gerekmez. Ancak, statik bağlantı uygulamaların sınama ve iç dağıtım için çalışabilir, ancak MFC yeniden dağıtmak için kullanmamanızı öneririz. Visual C++ kitaplıklarını dağıtmak için önerilen stratejiler hakkında daha fazla bilgi için dağıtım [yöntemi seçme'ye](choosing-a-deployment-method.md)bakın.

Uygulamanız WebBrowser denetimini uygulayan MFC sınıflarını kullanıyorsa (örneğin, [CHtmlView Sınıfı](../mfc/reference/chtmlview-class.md) veya [CHtmlEditView Sınıfı),](../mfc/reference/chtmleditview-class.md)hedef bilgisayarın en güncel ortak denetim dosyalarına sahip olması için Microsoft Internet Explorer'ın en güncel sürümünü de yüklemenizi öneririz. (En azından Internet Explorer 4.0 gereklidir.) Internet Explorer bileşenlerinin nasıl yüklenirhakkında bilgi, Microsoft Destek web sitesinde "Madde 185375: Internet Explorer'Da Tek EXE Yükleme Nasıl Oluşturulur" adlı bilgide mevcuttur.

Uygulamanız MFC veritabanı sınıflarını kullanıyorsa (örneğin, [CRecordset Class](../mfc/reference/crecordset-class.md) ve [CRecordView Class),](../mfc/reference/crecordview-class.md)ODBC'yi ve uygulamanızın kullandığı Tüm ODBC sürücülerini yeniden dağıtmanız gerekir.

MFC uygulamanız Windows Forms denetimlerini kullanıyorsa, uygulamanızla birlikte mfcmifc80.dll'yi yeniden dağıtmanız gerekir. Bu DLL, uygulama yerel klasöründe bir uygulama ile veya [Gacutil.exe (Küresel Derleme Önbellek Aracı)](/dotnet/framework/tools/gacutil-exe-gac-tool)kullanarak Küresel Derleme Önbelleğine (GAC) dağıtılarak yeniden dağıtılabilen güçlü bir ad imzalı .NET derlemesidir.

Bir MFC DLL'yi yeniden dağıtırsanız, hata ayıklama sürümünü değil, perakende sürümünü yeniden dağıttığınızdan emin olun. DL'lerin hata ayıklama sürümleri yeniden dağıtılamaz. MFC DLs'in hata ayıklama sürümlerinin adları "d" ile sona erer, örneğin, Mfc140d.dll.

MFC'yi VCRedist_*architecture*.exe kullanarak, Visual Studio ile yüklü modülleri birleştirerek veya MFC DLL'yi uygulamanızla aynı klasöre dağıtarak yeniden dağıtabilirsiniz. MFC'nin yeniden nasıl dağıtılanılabilenhakkında daha fazla bilgi [için](redistributing-visual-cpp-files.md)bkz.

## <a name="installation-of-localized-mfc-components"></a>Yerelleştirilmiş MFC Bileşenlerinin Yüklenmesi

Bir MFC yerelleştirme DLL yükleyerek uygulamanızı yerelleştirmeye karar verirseniz, yeniden dağıtılabilir birleştirme dosyalarını (.msm) kullanmanız gerekir. Örneğin, uygulamanızı bir x86 bilgisayarında yerelleştirmek istiyorsanız, Microsoft_VC`<version>`_MFCLOC_x86.msm'yi x86 bilgisayarın yükleme paketinde birleştirmeniz gerekir.

Yeniden dağıtılabilir .msm dosyaları yerelleştirme için kullanılan DL'leri içerir. Desteklenen her dil için bir DLL vardır. Yükleme işlemi bu DL'leri hedef bilgisayardaki %windir%\system32\ klasörüne yükler.

MFC uygulamalarının nasıl yerelleştirilen hakkında daha fazla bilgi için Bkz. [TN057: MFC Bileşenlerinin Yerelleştirilmesi.](../mfc/tn057-localization-of-mfc-components.md)

MFC DLL'yi uygulama yerel klasörünüzde dağıtarak MFC yerelleştirme DL'lerini yeniden dağıtabilirsiniz. Visual C++ kitaplıklarını yeniden dağıtma hakkında daha fazla bilgi [için](redistributing-visual-cpp-files.md)bkz.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Dosyalarını Yeniden Dağıtma](redistributing-visual-cpp-files.md)
