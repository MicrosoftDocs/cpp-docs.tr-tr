---
title: C/C++ Yan Yana Derlemeleri Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- side-by-side applications [C++]
ms.assetid: 7fa20b16-3737-4f76-a0b5-1dacea19a1e8
ms.openlocfilehash: 6e49ba72a397efb97437a2f7e6d721c782875c48
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493333"
---
# <a name="building-cc-side-by-side-assemblies"></a>C/C++ Yan Yana Derlemeleri Oluşturma

[Yan yana derleme](/windows/win32/SbsCs/about-side-by-side-assemblies-) , bir uygulamanın çalışma zamanında kullanması için kullanılabilen bir dizi dll, Windows sınıfı, com sunucusu, tür kitaplığı veya arabirim grubu olan bir kaynak koleksiyonudur. Derlemelerdeki dll 'Lerin yeniden paketlenmesi, derlemelerin birden çok sürümünün uygulamalar tarafından aynı anda kullanılabileceği ve güncelleştirme sürümü durumunda yüklü olan derlemelere hizmet vermek mümkün hale gelir.

C++ Uygulama, uygulamanın farklı bölümlerinde bir veya birkaç dll kullanabilir. Çalışma zamanında, dll 'Ler ana işleme yüklenir ve gerekli kod yürütülür. Uygulama, istenen dll 'Leri bulmak için işletim sistemini kullanır, diğer bağımlı dll 'Lerin ne şekilde yükleneceğini anlayın ve ardından bunları istenen DLL ile birlikte yükler. Windows XP, Windows Server 2003 ve Windows Vista 'dan önceki Windows işletim sistemleri sürümlerinde, işletim sistemi yükleyicisi uygulamanın yerel klasöründeki bağımlı dll 'Leri veya sistem yolunda belirtilen başka bir klasörü arar. Windows XP, Windows Server 2003 ve Windows Vista 'da, işletim sistemi yükleyicisi Ayrıca bir [bildirim](/windows/win32/sbscs/manifests) dosyası kullanarak bağımlı dll 'leri arayabilir ve bu DLL 'leri içeren yan yana derlemeler arayabilir.

Varsayılan olarak, bir DLL Visual Studio ile oluşturulduğunda, KIMLIĞI 2 ' ye eşit olan bir RT_MANIFEST kaynağı olarak gömülü bir [uygulama bildirimi](/windows/win32/SbsCs/application-manifests) vardır. Bir yürütülebilir için olduğu gibi, bu bildirim diğer derlemelerde bu DLL 'nin bağımlılıklarını açıklar. Bu, DLL 'nin yan yana derlemenin bir parçası olmadığı ve bu DLL 'ye bağımlı uygulamaların, yüklemek için bir uygulama bildirimi kullanmadığına ve bunun yerine, bu DLL 'yi sistem yolunda bulmak için işletim sistemi yükleyicisine güvendiğini varsayar.

> [!NOTE]
> Bildirim, KIMLIĞI 2 ' ye eşit olan bir kaynak olarak katıştırılması için bir uygulama bildirimi kullanan bir DLL için önemlidir. DLL, çalışma zamanında dinamik olarak yüklenirse (örneğin, [LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw) işlevi kullanılarak), işletim SISTEMI yükleyicisi dll 'nin bildiriminde belirtilen bağımlı derlemeleri yükler. Bir `LoadLibrary` çağrı sırasında dll 'ler için bir dış uygulama bildirimi denetlenmez. Bildirim ekli değilse, yükleyici derlemelerin yanlış sürümlerini yüklemeye veya bağımlı derlemeleri bulmak için bulamamasına çalışabilir.

Bir veya birkaç ilgili DLL, ilgili [derleme bildirimiyle](/windows/win32/SbsCs/assembly-manifests)birlikte yan yana derlemeye yeniden paketlenebilir ve bu, derlemeyi oluşturan dosyaları ve diğer yan yana derlemelerde derlemenin bağımlılığını açıklar.

> [!NOTE]
> Bir derleme bir DLL içeriyorsa, derleme bildirimini bu DLL 'ye KIMLIĞI 1 ' e eşit olan bir kaynak olarak eklemek ve özel derlemeye DLL ile aynı adı vermek önerilir. Örneğin, DLL adı MyLibrary. dll ise, bildirimin \<assemblyIdentity > öğesinde kullanılan Name özniteliğinin değeri MyLibrary de olabilir. Bazı durumlarda, bir kitaplık. dll dışında bir uzantıya sahip olduğunda (örneğin, bir MFC ActiveX denetimleri projesi bir. ocx kitaplığı oluşturduğunda), bir dış derleme bildirimi oluşturulabilir. Bu durumda, derlemenin adı ve bildirimi DLL 'nin adından farklı olmalıdır (örneğin, MyAssembly, MyAssembly. manifest ve MyLibrary. ocx). Ancak, bu tür kitaplıkların uzantısı. dll olacak şekilde yeniden adlandırılması önerilir ve bu derlemenin gelecekteki bakım maliyetini azaltmak için bildirimi bir kaynak olarak katıştırın. İşletim sisteminin özel derlemeleri nasıl aradığı hakkında daha fazla bilgi için bkz. [Derleme arama sırası](/windows/win32/SbsCs/assembly-searching-sequence).

Bu değişiklik, bir uygulama yerel klasöründe veya WinSxS [](/windows/win32/Msi/private-assemblies) derleme önbelleğinde [paylaşılan bir derleme](/windows/win32/Msi/shared-assemblies) olarak karşılık gelen DLL 'lerin dağıtımına izin verebilir. Bu yeni derlemenin doğru çalışma zamanı davranışına ulaşmak için birkaç adım izlenmelidir; [yan yana derlemeler oluşturmak Için yönergeler](/windows/win32/SbsCs/guidelines-for-creating-side-by-side-assemblies)bölümünde açıklanmıştır. Bir derleme doğru bir şekilde alındıktan sonra, ona bağlı bir uygulamayla birlikte paylaşılan veya özel bir derleme olarak dağıtılabilir. Yan yana derlemeleri paylaşılan bir derleme olarak yüklerken, [WINDOWS XP 'de yan yana paylaşım Için Win32 derlemelerini yükleme](/windows/win32/Msi/installing-win32-assemblies-for-side-by-side-sharing-on-windows-xp) veya [birleştirme modüllerini](/windows/win32/msi/merge-modules)kullanma konusunda özetlenen yönergeleri izleyebilirsiniz. Yan yana derlemeler özel bir derleme olarak yüklenirken, ilgili DLL 'yi, kaynakları ve derleme bildirimini, yükleme işleminin bir parçası olarak hedef bilgisayardaki uygulama yerel klasörüne kopyalayabilir ve bu derlemenin çalışma zamanında yükleyici tarafından bulunur (bkz. [Derleme arama dizisi](/windows/win32/SbsCs/assembly-searching-sequence)). Başka bir yöntem de [Windows Installer](/windows/win32/Msi/windows-installer-portal) kullanmak ve [Windows XP 'de bir uygulamanın özel kullanımı Için Win32 derlemelerini yükleme](/windows/win32/Msi/installing-win32-assemblies-for-the-private-use-of-an-application-on-windows-xp)konusunda özetlenen yönergeleri izlemelidir.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Yalıtılmış Uygulamaları Derleme](building-c-cpp-isolated-applications.md)<br/>
[C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
