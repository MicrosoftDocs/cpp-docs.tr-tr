---
title: Yalıtılmış Uygulama ve Yan Yana Derleme Kavramları
ms.date: 05/06/2019
helpviewer_keywords:
- side-by-side assemblies [C++]
- isolated assemblies [C++]
ms.assetid: 945a885f-cb3e-4c8a-a0b9-2c2e3e02cc50
ms.openlocfilehash: f569381b9efe9a8ca7704dc87bcb8e8102e0cde2
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220915"
---
# <a name="concepts-of-isolated-applications-and-side-by-side-assemblies"></a>Yalıtılmış Uygulama ve Yan Yana Derleme Kavramları

Bir uygulama olarak kabul edilir bir [yalıtılmış uygulama](/windows/desktop/SbsCs/isolated-applications) tüm bileşenleri varsa [yan yana derlemeler](/windows/desktop/SbsCs/about-side-by-side-assemblies-). Yan yana derleme, birlikte dağıtılan ve bir uygulama tarafından çalışma zamanında kullanılabilir hale getirilen kaynaklar topluluğudur (bir grup DLL dosyası, windows sınıfları, COM sunucuları, tür kitaplıkları veya arabirimler). Genellikle, yan yana derleme, bir ila birden fazla DLL dosyasından oluşur.

## <a name="shared-or-private"></a>Paylaşılan veya özel

Yan yana derleme, paylaşılan veya özel olabilir. [Paylaşılan yan yana derlemeler](https://msdn.microsoft.com/library/aa375996.aspx) , bildirimlerinde derlemeye kendi Bildirimlerde belirtin. birden çok uygulama tarafından kullanılabilir. Yan yana derlemenin birden fazla sürümü, aynı anda çalışan farklı uygulamalarla paylaşılabilir. A [özel derleme](/windows/desktop/SbsCs/about-private-assemblies-) uygulamasının özel kullanım için uygulama ile birlikte dağıtılan bir derlemedir. Özel derlemeler, uygulamanın yürütülebilir dosyasını veya alt klasörlerinden birini içeren klasörüne yüklenir.

## <a name="manifests-and-search-order"></a>Bildirimler ve arama sırası

Yalıtılmış uygulamalar ve yan yana derlemeler tarafından açıklanmıştır [bildirimlerini](/windows/desktop/sbscs/manifests). Bildirim, harici bir dosyada olabilir veya bir uygulama ya da derleme kaynağı olarak gömülü bir XML belgesidir. Yalıtılmış bir uygulamanın bildirim dosyası, uygulamanın çalışma zamanında bağlanması gereken paylaşılan yan yana derlemelerin adlarını ve sürümlerini yönetmek üzere kullanılır. Yan yana derlemenin bildirimi; yan yana derlemelerin adlarını, sürümlerini, kaynaklarını ve bağımlı derlemelerini belirtir. Paylaşılan bir yan yana derlemenin bildirimi, %WINDIR%\WinSxS\Manifests\ klasörüne yüklenir. Özel bir derleme söz konusu olduğunda, bildirimi, DLL içine bir kimliği 1'e eşit olan bir kaynak olarak eklemenizi öneririz. Özel derlemeye DLL'ninki ile aynı adı verebilirsiniz. Daha fazla bilgi için [hakkında özel derlemeler](/windows/desktop/SbsCs/about-private-assemblies-).

Yürütme sırasında Windows, karşılık gelen yan yana derlemeyi aramak ve yüklemek amacıyla uygulama bildirimindeki derleme bilgilerini kullanır. Yalıtılmış bir uygulama bir derleme bağımlılığı belirtiyorsa, işletim sistemi öncelikle %WINDIR%\WinSxS\ klasöründeki yerel derleme önbelleğindeki paylaşılan derlemeler arasında derleme için arama yapar. Gerekli derleme bulunamadığında, işletim sistemi uygulamanın dizin yapısının klasöründe özel bir derleme için arama yapar. Daha fazla bilgi için [derleme arama sırası](/windows/desktop/SbsCs/assembly-searching-sequence).

## <a name="changing-dependencies"></a>Bağımlılıkları değiştirme

Yan yana derleme bağımlılıklarını değiştirerek bir uygulama dağıtıldıktan sonra değiştirebilirsiniz [yayımcı yapılandırma dosyaları](/windows/desktop/SbsCs/publisher-configuration-files) ve [uygulama yapılandırma dosyaları](/windows/desktop/SbsCs/application-configuration-files). Yayımcı ilkesi dosyası olarak da bilinen yayımcı yapılandırma dosyası; uygulamaları ve derlemeleri, genel olarak, yan yana derlemenin bir sürümünü kullanırken aynı derlemenin başka bir sürümünü kullanmaya yönlendiren bir XML dosyasıdır. Örneğin, bir hata düzeltmesi veya güvenlik düzeltmesi yan yana derleme için dağıtıldığında ve tüm uygulamaları düzeltilmiş sürümü kullanmak üzere yeniden yönlendirmek istediğinizde bağımlılığı değiştirebilirsiniz. Uygulama yapılandırma dosyası, belirli bir uygulamayı yan yana bir derlemenin bir sürümünden aynı derlemenin başka bir sürümünü kullanmaya yönlendiren bir XML dosyasıdır. Uygulama yapılandırma dosyasını, belirli bir uygulamayı yan yana derlemenin yayımcı yapılandırma dosyasında tanımlanandan farklı bir sürümünü kullanmaya yeniden yönlendirebilirsiniz. Daha fazla bilgi için [yapılandırma](/windows/desktop/SbsCs/configuration).

## <a name="visual-c-libraries"></a>Visual C++ kitaplıkları

Visual Studio 2005 ve Visual Studio 2008'de; ATL, MFC, CRT, Standart C++, OpenMP ve MSDIA gibi yeniden dağıtılabilir kitaplıklar, yerel derleme önbelleğine paylaşılan yan yana derlemeler olarak dağıtılmıştır. Geçerli sürümde, yeniden dağıtılabilir kitaplıklar merkezi dağıtım kullanmaktadır. Varsayılan olarak, Visual Studio kullanılarak oluşturulan tüm uygulamalar son ikili dosyada gömülü bildirimle oluşturulur ve bildirim görselde ikili dosya bağımlılıklarını açıklar C++ kitaplıkları. Bildirim üretimini anlama için C++ uygulamaları, [Understanding Manifest Generation for C /C++ programlar](understanding-manifest-generation-for-c-cpp-programs.md). Bildirim; kullandıkları ya da yerel dağıtım kullanan kitaplıklara statik olarak bağlı uygulamalar için gerekli değildir. Dağıtım hakkında daha fazla bilgi için bkz: [Visual C++ üzerinde dağıtım](../windows/deployment-in-visual-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
