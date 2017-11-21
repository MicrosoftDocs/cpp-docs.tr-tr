---
title: "Yalıtılmış uygulamalar ve yan yana derlemeler kavramlarını | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- side-by-side assemblies [C++]
- isolated assemblies [C++]
ms.assetid: 945a885f-cb3e-4c8a-a0b9-2c2e3e02cc50
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 08c3b48ebfc96a93961c6c810312daa6072e8f40
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="concepts-of-isolated-applications-and-side-by-side-assemblies"></a>Yalıtılmış Uygulama ve Yan Yana Derleme Kavramları
Bir uygulama olarak kabul edilir bir [yalıtılmış uygulama](http://msdn.microsoft.com/library/aa375190) tüm bileşenleri varsa [yan yana derlemeler](http://msdn.microsoft.com/library/ff951640). Yan yana derleme, birlikte dağıtılan ve bir uygulama tarafından çalışma zamanında kullanılabilir hale getirilen kaynaklar topluluğudur (bir grup DLL dosyası, windows sınıfları, COM sunucuları, tür kitaplıkları veya arabirimler). Genellikle, yan yana derleme, bir ila birden fazla DLL dosyasından oluşur.  
  
## <a name="shared-or-private"></a>Paylaşılan veya özel  
 Yan yana derleme, paylaşılan veya özel olabilir. [Yan yana derlemeler paylaşılan](https://msdn.microsoft.com/en-us/library/aa375996.aspx) belirtin, kendi bildirimleri, bir bağımlılığı derleme birden çok uygulama tarafından kullanılıyor olabilir. Yan yana derlemenin birden fazla sürümü, aynı anda çalışan farklı uygulamalarla paylaşılabilir. A [özel derleme](http://msdn.microsoft.com/library/ff951638) uygulamasının özel kullanım için uygulama ile birlikte dağıtılan bir derlemedir. Özel derlemeler, uygulamanın yürütülebilir dosyasını veya alt klasörlerinden birini içeren klasörüne yüklenir.  
  
## <a name="manifests-and-search-order"></a>Bildirimler ve arama sırası  
 Yalıtılmış uygulamalar ve yan yana derlemeleri tarafından açıklanmıştır [bildirimleri](http://msdn.microsoft.com/library/aa375365). Bildirim, harici bir dosyada olabilir veya bir uygulama ya da derleme kaynağı olarak gömülü bir XML belgesidir. Yalıtılmış bir uygulamanın bildirim dosyası, uygulamanın çalışma zamanında bağlanması gereken paylaşılan yan yana derlemelerin adlarını ve sürümlerini yönetmek üzere kullanılır. Yan yana derlemenin bildirimi; yan yana derlemelerin adlarını, sürümlerini, kaynaklarını ve bağımlı derlemelerini belirtir. Paylaşılan bir yan yana derlemenin bildirimi, %WINDIR%\WinSxS\Manifests\ klasörüne yüklenir. Özel bir derleme söz konusu olduğunda, bildirimi, DLL içine bir kimliği 1'e eşit olan bir kaynak olarak eklemenizi öneririz. Özel derlemeye DLL'ninki ile aynı adı verebilirsiniz. Daha fazla bilgi için bkz: [hakkında özel derlemeler](http://msdn.microsoft.com/library/ff951638).  
  
 Yürütme sırasında Windows, karşılık gelen yan yana derlemeyi aramak ve yüklemek amacıyla uygulama bildirimindeki derleme bilgilerini kullanır. Yalıtılmış bir uygulama bir derleme bağımlılığı belirtiyorsa, işletim sistemi öncelikle %WINDIR%\WinSxS\ klasöründeki yerel derleme önbelleğindeki paylaşılan derlemeler arasında derleme için arama yapar. Gerekli derleme bulunamadığında, işletim sistemi uygulamanın dizin yapısının klasöründe özel bir derleme için arama yapar. Daha fazla bilgi için bkz: [derleme arama sırası](http://msdn.microsoft.com/library/aa374224).  
  
## <a name="changing-dependencies"></a>Bağımlılıkları değiştirme  
 Değiştirerek bir uygulama dağıtıldıktan sonra yan yana derleme bağımlılıkları değiştirebilirsiniz [yayımcı yapılandırma dosyalarını](http://msdn.microsoft.com/library/aa375682) ve [uygulama yapılandırma dosyaları](http://msdn.microsoft.com/library/aa374182). Yayımcı ilkesi dosyası olarak da bilinen yayımcı yapılandırma dosyası; uygulamaları ve derlemeleri, genel olarak, yan yana derlemenin bir sürümünü kullanırken aynı derlemenin başka bir sürümünü kullanmaya yönlendiren bir XML dosyasıdır. Örneğin, bir hata düzeltmesi veya güvenlik düzeltmesi yan yana derleme için dağıtıldığında ve tüm uygulamaları düzeltilmiş sürümü kullanmak üzere yeniden yönlendirmek istediğinizde bağımlılığı değiştirebilirsiniz. Uygulama yapılandırma dosyası, belirli bir uygulamayı yan yana bir derlemenin bir sürümünden aynı derlemenin başka bir sürümünü kullanmaya yönlendiren bir XML dosyasıdır. Uygulama yapılandırma dosyasını, belirli bir uygulamayı yan yana derlemenin yayımcı yapılandırma dosyasında tanımlanandan farklı bir sürümünü kullanmaya yeniden yönlendirebilirsiniz. Daha fazla bilgi için bkz: [yapılandırma](http://msdn.microsoft.com/library/aa375123).  
  
## <a name="visual-c-libraries"></a>Visual C++ kitaplıkları  
 Visual Studio 2005 ve Visual Studio 2008'de; ATL, MFC, CRT, Standart C++, OpenMP ve MSDIA gibi yeniden dağıtılabilir kitaplıklar, yerel derleme önbelleğine paylaşılan yan yana derlemeler olarak dağıtılmıştır. Geçerli sürümde, yeniden dağıtılabilir kitaplıklar merkezi dağıtım kullanmaktadır. Varsayılan olarak, Visual C++ kullanılarak oluşturulan tüm uygulamalar, son ikili dosyada gömülü bildirimle oluşturulur ve bildirim Visual C++ kitaplıklarındaki iki dosyanın bağımlılıklarını açıklar. Visual C++ uygulamaları için bildirim üretme anlamak için bkz: [anlama bildirim oluşturma için C/C++ programları](../build/understanding-manifest-generation-for-c-cpp-programs.md). Bildirim; kullandıkları ya da yerel dağıtım kullanan kitaplıklara statik olarak bağlı uygulamalar için gerekli değildir. Dağıtımı hakkında daha fazla bilgi için bkz: [Visual C++ üzerinde dağıtım](../ide/deployment-in-visual-cpp.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C/C++ yalıtılmış uygulamaları ve yan yana derlemeler](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)