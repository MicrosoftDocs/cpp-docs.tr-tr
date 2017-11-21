---
title: "Visual C++ dosyalarını yeniden dağıtma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- application deployment [C++], file redistributing
- redistributing applications [C++]
- deploying applications [C++], file redistributing
- file redistribution [C++]
- redistributing applications [C++], about redistributing applications
ms.assetid: d201b2ce-36f1-44e5-a96c-0db81a1ba652
caps.latest.revision: "50"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9b2e0af195270b55f80f7eaba37f273765b3cf4b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="redistributing-visual-c-files"></a>Visual C++ Dosyalarını Yeniden Dağıtma
Bir uygulamayı dağıtırken, onu desteklemek için gerekli tüm dosyaları da dağıtmalısınız. Bu dosyalardan herhangi biri Microsoft tarafından sağlanıyorsa, bunları yeniden dağıtma izniniz olup olmadığını kontrol edin. Visual Studio Lisans Koşulları'nı gözden geçirmek için IDE Microsoft Visual Studio hakkında iletişim kutusunda lisans koşulları bağlantısına bakın veya karşıdan [Microsoft Yazılımı Lisans koşulları](http://go.microsoft.com/fwlink/p/?LinkId=831114) dosya. "Visual Studio belirli sürümleri için Microsoft Yazılım Lisans Koşulları'nın"Dağıtılabilir kod"bölümünde başvurulan listesidir" görüntülemek için bkz: [Microsoft Visual Studio 2017 ve Microsoft Visual Studio 2017 için dağıtılabilir kod SDK (içerir yardımcı programları ve BuildServer Dosyaları)](http://go.microsoft.com/fwlink/p/?LinkId=823098), veya Visual Studio 2015 için bkz. [Microsoft Visual Studio 2015 ve Microsoft Visual Studio 2015 SDK için dağıtılabilir kod](http://go.microsoft.com/fwlink/p/?LinkId=523763). Yeniden dağıtılabilir dosyalar hakkında daha fazla bilgi için bkz: [belirleme hangi DLL'lerin yeniden dağıtılacağını](../ide/determining-which-dlls-to-redistribute.md) ve [Dağıtım örnekleri](../ide/deployment-examples.md).  
  
 Visual C++ yeniden dağıtılabilir dosyaları dağıtmak için Visual C++ yeniden dağıtılabilir paketleri kullanabilirsiniz (VCRedist\_x86.exe, VCRedist\_x64.exe veya VCRedist\_arm.exe) Visual Studio'da dahil edilir. Visual Studio 2017 ' Bu dosyalar Program dosyaları [(x86)] bulunabilir\\Microsoft Visual Studio\\2017\\_edition_\\VC\\Redist\\ MSVC\\_lib sürüm_ klasörü, burada _edition_ olan yüklüyse, Visual Studio sürümü ve _lib sürüm_ sürümü yeniden dağıtmak için kitaplıkları. Program dosyaları [(x 86)] \Microsoft Visual Studio Visual Studio 2015'te bu dosyalar, Visual Studio yükleme dizini altında bulunabilir *sürüm*\VC\redist\\*yerel ayar* \\. Başka bir seçenek, Visual Studio 2017 [(x 86)] Program Files yer yeniden dağıtılabilir birleştirme modülleri (.msm dosyaları) kullanmaktır\\Microsoft Visual Studio\\2017\\_edition_ \\ VC\\Redist\\MSVC\\_lib sürüm_\\MergeModules\\ klasör. Visual Studio 2015'te bu Program dosyaları [(x 86)] \Common Files\Merge modülleri bulunabilir\\. Yeniden dağıtılabilir Visual C++ DLL'lerde doğrudan yüklemeye mümkündür *uygulama yerel klasörüne*, yürütülebilir uygulama dosyanızı içeren klasörü olduğu. Nedeni bakım için bu yükleme konumu kullanmanızı önermiyoruz.  
  
 Visual C++ Yeniden Dağıtılabilir Paketleri tüm Visual C++ kitaplıklarını yükler ve kaydeder. Bu paketlerden birini kullanırsanız, uygulamanın yüklenmesi için bir önkoşul olarak hedef sistem üzerinde çalışacak şekilde ayarlamanız gerekir. Visual C++ kitaplıklarının otomatik güncelleştirilmesini sağladıklarından, dağıtımlarınız için bu paketleri kullanmanızı öneririz. Bu paketleri kullanma hakkında bir örnek için bkz: [izlenecek yol: Visual C++ uygulaması tarafından kullanarak bir Visual C++ yeniden dağıtılabilir paketi dağıtma](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).  
  
 Her Visual C++ yeniden dağıtılabilir paketi makinede daha yeni bir sürüm varlığını denetler. Daha yeni bir sürümü bulunursa, paketi yüklü değil. Yeniden dağıtılabilir paketleri görüntü Visual Studio 2015'ten başlayarak, bu kurulum bildiren bir hata iletisi başarısız oldu. Kullanarak bir paket çalıştırırsanız **/quiet** bayrağı, hata iletisi görüntülenir. Her iki durumda da Microsoft Installer tarafından bir hata günlüğe kaydedilir ve bir hata sonucu çağırana döndürülür. Visual Studio 2015 paketlerinde başlayarak, daha yeni bir sürümünün yüklü olup olmadığını öğrenmek için kayıt defterini denetleyerek bu hatayı önleyebilirsiniz. Şu anda yüklü olan sürümü HKEY_LOCAL_MACHINE\Software [\Wow6432Node] \Microsoft\VisualStudio depolanan\\_vs sürüm_\VC\Runtimes\\{x86 | x64 | ARM} anahtarı burada _vs sürüm_ için Visual Studio sürüm numarasıdır (14.0 Visual Studio 2015 ve Visual Studio 2017 için yeniden dağıtılabilir güncelleştirilmiş 2017 2015 sürümü ile ikili uyumlu olduğundan), ve anahtarın olduğu X 86 veya platformu için yüklü vcredist sürümleri bağlı olarak x64 ARM. (Yüklü x86 sürümünü görüntülemek için RegEdit kullanmadığınız sürece Wow6432Node alt anahtarı altında denetlemeniz gerekmez x x64 paketi platform.) Sürüm numarasını REG_SZ dize değerinde depolanan **sürüm** ve ayrıca kümesini **ana**, **küçük**, **Bld**ve **Rbld** REG_DWORD değerleri. Yükleme zamanında bir hatayı önlemek için şu anda yüklü olan sürümü daha yeni ise yeniden dağıtılabilir paketinin yüklemesi atlamanız gerekir.  
  
 Visual C++ DLL içeren bir birleştirme modülünü kullanıyorsanız, Windows Installer paketi (veya benzer yükleme paketi) uygulamayı dağıtmak için kullanmakta olduğunuz içermelidir. Daha fazla bilgi için bkz: [yeniden dağıtma tarafından kullanarak birleştirme modülleri](../ide/redistributing-components-by-using-merge-modules.md). Bir örnek için bkz: [izlenecek yol: bir Visual C++ uygulamasını kullanarak bir kurulum projesi dağıtma](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md), hangi ayrıca InstallShield Limited Edition bir yükleme paketi oluşturmak için nasıl kullanılacağını gösterir.  
  
## <a name="potential-run-time-errors"></a>Olası Çalışma Zamanı Hataları  
 Visual C++ Kitaplık DLL erişilebilir değil ve Windows, uygulamanız için onu yükleyemiyor, bu iletiyi görüntülenebilir: **bu uygulama başarısız oldu MSVCR\<sürüm numarası > .dll bulunamadı. Uygulamanın yeniden yüklenmesi, bu sorunu çözebilir.**  
  
 Bu tür bir hatayı gidermek için uygulamanızın doğru bir şekilde derlendiğinden ve Visual C++ kitaplıklarının hedef sistemde doğru bir şekilde dağıtıldığından emin olun. Daha fazla bilgi için bkz: [bir Visual C++ uygulaması bağımlılıklarını anlama](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md).  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Birleştirme modüllerini kullanarak yeniden dağıtma](../ide/redistributing-components-by-using-merge-modules.md)|Visual C++ yeniden dağıtılabilir birleştirme modülleri Visual C++ çalışma zamanı kitaplıkları paylaşılan DLL'ler %windir%\system32\ klasör olarak yüklemek için nasıl kullanılacağını açıklar.|  
|[Visual C++ ActiveX denetimlerini yeniden dağıtma](../ide/redistributing-visual-cpp-activex-controls.md)|ActiveX Denetimlerini kullanan bir uygulamanın nasıl yeniden dağıtılması gerektiği açıklanmaktadır.|  
|[Veritabanı destek dosyalarını yeniden dağıtma](../ide/redistributing-database-support-files.md)|Microsoft Veri Erişim SDK'sındaki veritabanı teknolojileri ve Veri Erişim Nesneleri (DAO) için destek dosyalarının nasıl yeniden dağıtılacağı ele alınmaktadır.|  
|[MFC kitaplığını yeniden dağıtma](../ide/redistributing-the-mfc-library.md)|MFC kullanan bir uygulamanın nasıl yeniden dağıtılacağı açıklanmaktadır.|  
|[ATL uygulamasını yeniden dağıtma](../ide/redistributing-an-atl-application.md)|ATL kullanan bir uygulamayı yeniden dağıtmak açıklar Visual Studio 2012'den itibaren yeniden dağıtılabilir kitaplık ATL için gereklidir.|  
|[Dağıtım örnekleri](../ide/deployment-examples.md)|Visual C++ uygulamalarının nasıl dağıtıldığını gösteren örneklere bağlantılar verir.|  
|[Masaüstü uygulamaları dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)|Visual C++ dağıtım kavramlarını ve teknolojilerini tanıtır.|