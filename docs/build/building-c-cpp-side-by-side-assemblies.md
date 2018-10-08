---
title: C/C++ yan yana derlemeleri oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- side-by-side applications [C++]
ms.assetid: 7fa20b16-3737-4f76-a0b5-1dacea19a1e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2e3c80b383c592d3eebf892981c088e26529c515
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860946"
---
# <a name="building-cc-side-by-side-assemblies"></a>C/C++ Yan Yana Derlemeleri Oluşturma

A [yan yana derleme](/windows/desktop/SbsCs/about-side-by-side-assemblies-) bir kaynaklar koleksiyonudur — bir grup dll, windows sınıfları, COM sunucuları, tür kitaplıkları veya arabirimler — çalışma zamanında kullanmak bir uygulama için kullanılabilir. Derlemelerde DLL'leri yeniden paketleme birincil avantajı, derlemeleri birden çok sürümünü aynı anda uygulamalar tarafından kullanılabilir ve şu anda yüklü hizmet derlemelere güncelleştirme yayın olması durumunda mümkündür olmasıdır.

Visual C++ uygulaması, bir veya birden çok uygulamanın farklı kısımlarını DLL'lerde kullanabilir. Çalışma zamanında, DLL'leri ana işlem içine yüklenmiş ve gerekli kod yürütülür. Uygulamanın işletim sistemi, istenen DLL'leri bulun, bağımlı diğer DLL'leri yüklenmesi ve sonra bunları istenen DLL ile birlikte yüklemek sahip anlamak için kullanır. Windows işletim sistemi sürümlerinde bağımlı DLL'lerin uygulamanın yerel klasörü veya sistem yolunda belirtilen başka bir klasöre Windows XP, Windows Server 2003 ve Windows Vista'den önceki işletim sistemi yükleyicisi arar. Windows XP, Windows Server 2003 ve Windows Vista üzerinde işletim sistemi yükleyicisi kullanarak bağımlı dll dosyaları için de arayabilirsiniz bir [bildirim](https://msdn.microsoft.com/library/windows/desktop/aa375365) dosya ve bu DLL'leri içeren yan yana derlemeler arayın.

Varsayılan olarak, Visual Studio ile bir DLL derlenirken, sahip bir [uygulama bildirimini](/windows/desktop/SbsCs/application-manifests) kimliği 2'ye eşit olan bir rt_manıfest kaynak olarak gömülü. Yalnızca bir yürütülebilir dosya olduğu gibi bu bildirim diğer derlemeleri bu DLL bağımlılıkları açıklar. Bu DLL, yan yana derlemenin parçası değildir ve bu DLL bağımlı uygulamaları yükler, ancak bunun yerine sistem yolunda bu DLL bulmak için işletim sistemi yükleyicisi kullanan bir uygulama bildirimi kullanmanız yapmayacağınız varsayar.

> [!NOTE]
> Kimliği 2'ye eşit olan bir kaynak olarak gömülü bildirimle sağlamak için bir uygulama bildirimi kullanan bir DLL için önemlidir. DLL çalışma zamanında dinamik olarak yüklenirse (örneğin, kullanarak [LoadLibrary](https://msdn.microsoft.com/library/windows/desktop/ms684175) işlevi), işletim sistemi yükleyicisi DLL'nin bildiriminde belirtilen bağımlı derlemeleri yükler. DLL için bir dış uygulama bildirimi sırasında işaretli bir `LoadLibrary` çağırın. Bildirim gömülü değilse yükleyici yanlış derlemelerin sürümleri yüklenemiyor veya bağımlı derlemeleri bulmak için bulma başarısız deneyebilir.

Bir veya birkaç ilgili dll paketlenmiş ilgili bir yan yana derleme içine [derleme bildirimi](/windows/desktop/SbsCs/assembly-manifests), diğer yan yana üzerinde hangi dosyaların derleme bağımlılığı yanı sıra derleme form açıklar bütünleştirilmiş kodları.

> [!NOTE]
> Bir derleme bir DLL içeriyorsa, derleme bildirimi bu DLL içine kimliği 1'e eşit olan bir kaynak olarak ekleyin ve özel derleme DLL aynı adı vermek için önerilir. DLL mylibrary.dll adıdır, örneğin, adı özniteliğinin değeri kullanılan \<assemblyIdentity > bildirimin öğesi kitaplığım da olabilir. Bir kitaplığı .dll bir uzantıya sahip olduğunda bazı durumlarda (örneğin, bir MFC ActiveX denetimleri projesi .ocx kitaplığı oluşturur) bir dış derleme bildirimi oluşturulabilir. Bu durumda, derleme ve bildirimi adını (örneğin, MyAssembly, MyAssembly.manifest ve mylibrary.ocx) DLL adından farklı olmalıdır. Bununla birlikte, yine de extension.dll varsa ve bu derlemeye gelecek bakım maliyeti azaltmak için bir kaynak olarak bildirimi katıştırmak için tür kitaplıkları yeniden adlandırmak için önerilir. İşletim sistemi özel derlemeler için nasıl arama hakkında daha fazla bilgi için bkz. [derleme arama sırası](/windows/desktop/SbsCs/assembly-searching-sequence).

Bu değişiklik dağıtım karşılık gelen dll izin verebileceği bir [özel derleme](/windows/desktop/Msi/private-assemblies) uygulama yerel klasöründe veya olarak bir [derleme paylaşılan](/windows/desktop/Msi/shared-assemblies) WinSxS derleme önbelleğinde. Bu yeni bir derleme doğru çalışma zamanı davranışını elde etmek için izlenmesi gereken birkaç adım vardır; içinde açıklanan [yan yana derlemeleri oluşturma için yönergeler](/windows/desktop/SbsCs/guidelines-for-creating-side-by-side-assemblies). Bir derleme doğru yazılmasını sonra dağıtılmış olarak herhangi bir paylaşılan veya özel bir derleme bağımlı bir uygulama ile birlikte. Yan yana derlemeler paylaşılan bir derleme yüklerken yönergeleri ana hatlarıyla belirtilen ya da izleme olabilir [yan yana paylaşım Windows XP için Win32 derlemeleri yükleme](/windows/desktop/Msi/installing-win32-assemblies-for-side-by-side-sharing-on-windows-xp) veya [birleştirme modülleri](https://msdn.microsoft.com/library/windows/desktop/aa369820). Yan yana derlemeler özel bir derleme yüklerken, yalnızca yükleme işleminin bir parçası olarak karşılık gelen DLL, kaynaklar ve derleme bildirimi hedef bilgisayarda yerel uygulama klasörü bu derleme olabilir sağlama kopyaladığınız Çalışma zamanında yükleyicisi tarafından bulundu (bkz [derleme arama sırası](/windows/desktop/SbsCs/assembly-searching-sequence)). Başka bir yolu [Windows Installer](/windows/desktop/Msi/windows-installer-portal) ve içinde açıklanan yönergeleri izlemeniz [bir uygulamanın Windows XP özel kullanım için Win32 derlemeleri yükleme](/windows/desktop/Msi/installing-win32-assemblies-for-the-private-use-of-an-application-on-windows-xp).

## <a name="see-also"></a>Ayrıca Bkz.

[Dağıtım Örnekleri](../ide/deployment-examples.md)<br/>
[C/C++ Yalıtılmış Uygulamaları Derleme](../build/building-c-cpp-isolated-applications.md)<br/>
[C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)