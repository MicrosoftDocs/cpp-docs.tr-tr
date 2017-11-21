---
title: "C/C++ yan yana derlemeleri oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: side-by-side applications [C++]
ms.assetid: 7fa20b16-3737-4f76-a0b5-1dacea19a1e8
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 40b8099a1159514d3ffce8cfeb9b38274c3e68b0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="building-cc-side-by-side-assemblies"></a>C/C++ Yan Yana Derlemeleri Oluşturma
A [yan yana derleme](http://msdn.microsoft.com/library/windows/desktop/ff951640) kaynakları koleksiyonudur — DLL'leri, windows sınıfı, COM sunucuları, tür kitaplıklarının veya arabirimleri grubu — çalışma zamanında kullanılacak bir uygulama için kullanılabilir. DLL'leri derlemelerde yeniden paketleme birincil avantajı, aynı anda birden fazla sürümünü derlemeleri uygulamalar tarafından kullanılabilir ve yüklü hizmet derlemeleri güncelleştirme sürüm durumunda mümkündür olmasıdır.  
  
 Visual C++ uygulamasını uygulama farklı bölümlerinin bir veya birkaç DLL'lerde kullanabilir. Çalışma zamanında DLL'leri ana işlem içine yüklenmiş ve gerekli kodu yürütülür. Uygulama istenen DLL'leri bulmak, diğer bağımlı DLL'lerin yüklenmesi ve ardından bunları istenen birlikte DLL'yi sahip anlamak için işletim sistemini kullanır. Windows işletim sistemi sürümlerinde uygulamanın yerel klasör veya sistem yolunda belirtilen başka bir klasöre bağımlı DLL'lerde Windows XP, Windows Server 2003 ve Windows Vista'den önceki işletim sistemi yükleyicisi arar. Windows XP, Windows Server 2003 ve Windows Vista üzerinde işletim sistemi yükleyicisi kullanılarak bağımlı DLL'ler için de arayabilirsiniz bir [bildirim](http://msdn.microsoft.com/library/windows/desktop/aa375365) dosyasını ve arama bu DLL'ler içeren yan yana derlemeler için.  
  
 Varsayılan olarak, DLL Visual Studio ile yapılandırıldığında, sahip bir [uygulama bildirimi](http://msdn.microsoft.com/library/windows/desktop/aa374191) kimliği 2'ye eşit olan bir RT_MANIFEST kaynak olarak katıştırılmış. Yalnızca bir yürütülebilir dosya için olduğu gibi bu bildirim diğer derlemelerini bu DLL bağımlılıklarını açıklar. Bu DLL yan yana derleme parçası değildir ve bu DLL bağımlı uygulamaları yüklemek, ancak bunun yerine sistem yolunda bu DLL bulmak için işletim sistemi yükleyicisi kullanan bir uygulama bildirimi kullanmanız yapmayacağınız varsayar.  
  
> [!NOTE]
>  Bir uygulama bildirimi kimliği 2'ye eşit olan bir kaynak olarak katıştırılmış bildirim sağlamak için kullandığı bir DLL için önemlidir. DLL çalışma zamanında dinamik olarak yüklü değilse (örneğin, kullanarak [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175) işlevi), işletim sistemi yükleyicisi DLL'nin bildiriminde belirtilen bağımlı derlemeleri yükler. DLL'ler için bir dış uygulama bildirimi sırasında işaretli bir `LoadLibrary` çağırın. Bildirim gömülü olmayan, yükleyici derlemeleri yanlış sürümlerini yüklemek veya bulma için Bul bağımlı derlemeleri başarısız deneyebilir.  
  
 Bir veya birkaç ilişkili DLL'ler paketlenmiş bir karşılık gelen bir yan yana derleme içine [derleme bildirimi](http://msdn.microsoft.com/library/windows/desktop/aa374219), hangi dosyaların bağımlılığı derlemesinin yanı sıra derleme diğer yan yana üzerinde form açıklar derlemeler.  
  
> [!NOTE]
>  Bir derlemeyi bir DLL içeriyorsa, derleme bildirimi bu DLL içine kimliği 1'e eşit olan bir kaynak olarak ekleme ve özel derleme DLL aynı adı vermek için önerilir. DLL adı mylibrary.dll ise, örneğin, adı özniteliğinin değeri kullanılan \<assemblyIdentity > öğesi bildiriminin kitaplığım da olabilir. Bir kitaplık .dll dışında bir uzantıya sahipse, bazı durumlarda (örneğin, MFC ActiveX denetimleri projesinde .ocx kitaplığı oluşturur) bir dış derleme bildirimi oluşturulabilir. Bu durumda, derleme ve kendi bildirim adını (örneğin, MyAssembly, MyAssembly.manifest ve mylibrary.ocx) DLL adından farklı olmalıdır. Ancak extension.dll varsa ve bu derleme gelecek bakım maliyetini azaltmak için bir kaynak olarak bildirimi katıştırmak için tür kitaplığı yeniden adlandırmak için hala önerilir. İşletim sistemi için özel derlemeler nasıl arayacağını hakkında daha fazla bilgi için bkz: [derleme arama sırası](http://msdn.microsoft.com/library/windows/desktop/aa374224).  
  
 Bu değişiklik karşılık gelen dll dağıtımını izin verebilir bir [özel derleme](http://msdn.microsoft.com/library/windows/desktop/aa370850) uygulama yerel klasöründe veya farklı bir [derleme paylaşılan](http://msdn.microsoft.com/library/windows/desktop/aa371839) WinSxS derleme önbelleğinde. Bu yeni bir derleme doğru çalışma zamanı davranışını elde etmek için izlenmesi birkaç adım vardır; içinde açıklanan [oluşturma yan yana derlemeler için yönergeleri](http://msdn.microsoft.com/library/windows/desktop/aa375155). Bir derlemeyi doğru yazılmasını sonra dağıtılmış herhangi bir paylaşılan ya da özel bir derleme bağımlı bir uygulama ile birlikte olarak. Yan yana derlemeler paylaşılan bir derlemede yüklerken yönergeleri ana hatlarıyla ya da izleme olabilir [yan yana paylaşım Windows XP için Win32 derlemeleri yükleme](http://msdn.microsoft.com/library/windows/desktop/aa369532) veya [birleştirme modülleri](http://msdn.microsoft.com/library/windows/desktop/aa369820). Yan yana derlemeler özel derleme olarak yüklerken, yalnızca ilgili DLL, kaynakları ve derleme bildirimi yükleme işleminin parçası olarak hedef bilgisayarda uygulama yerel klasörüne bu derleme olabilir sağlama kopyaladığınız Çalışma zamanında yükleyicisi tarafından bulundu (bkz [derleme arama sırası](http://msdn.microsoft.com/library/windows/desktop/aa374224)). Başka bir yolu kullanmaktır [Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688) ve'nda gösterilen yönergeleri izleyin [uygulamanın Windows XP üzerinde özel kullanım için Win32 derlemeleri yükleme](http://msdn.microsoft.com/library/windows/desktop/aa369534).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dağıtım örnekleri](../ide/deployment-examples.md)   
 [C/C++ yalıtılmış uygulamaları derleme](../build/building-c-cpp-isolated-applications.md)   
 [C/C++ yalıtılmış uygulamaları ve yan yana derlemeler](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)