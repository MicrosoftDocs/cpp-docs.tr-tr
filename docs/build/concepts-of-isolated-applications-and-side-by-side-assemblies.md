---
title: Yalıtılmış Uygulama ve Yan Yana Derleme Kavramları
ms.date: 05/06/2019
helpviewer_keywords:
- side-by-side assemblies [C++]
- isolated assemblies [C++]
ms.assetid: 945a885f-cb3e-4c8a-a0b9-2c2e3e02cc50
ms.openlocfilehash: f75a95ccca214f437152d13e099fbd9d03eaaee2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493303"
---
# <a name="concepts-of-isolated-applications-and-side-by-side-assemblies"></a>Yalıtılmış Uygulama ve Yan Yana Derleme Kavramları

Bir uygulama, tüm bileşenleri [yan yana derlemeler](/windows/win32/SbsCs/about-side-by-side-assemblies-)ise [yalıtılmış bir uygulama](/windows/win32/SbsCs/isolated-applications) olarak kabul edilir. Yan yana derleme, birlikte dağıtılan ve bir uygulama tarafından çalışma zamanında kullanılabilir hale getirilen kaynaklar topluluğudur (bir grup DLL dosyası, windows sınıfları, COM sunucuları, tür kitaplıkları veya arabirimler). Genellikle, yan yana derleme, bir ila birden fazla DLL dosyasından oluşur.

## <a name="shared-or-private"></a>Paylaşılan veya özel

Yan yana derleme, paylaşılan veya özel olabilir. [Paylaşılan yan yana derlemeler](/windows/win32/sbscs/about-shared-assemblies-) , bildirimlerinde, derlemesinde bir bağımlılığı belirten birden çok uygulama tarafından kullanılabilir. Yan yana derlemenin birden fazla sürümü, aynı anda çalışan farklı uygulamalarla paylaşılabilir. [Özel derleme](/windows/win32/SbsCs/about-private-assemblies-) , uygulamanın dışlamalı kullanımı için bir uygulamayla birlikte dağıtılan bir derlemedir. Özel derlemeler, uygulamanın yürütülebilir dosyasını veya alt klasörlerinden birini içeren klasörüne yüklenir.

## <a name="manifests-and-search-order"></a>Bildirimler ve arama sırası

Yalıtılmış uygulamalar ve yan yana derlemeler, [Bildirimler](/windows/win32/sbscs/manifests)tarafından açıklanır. Bildirim, harici bir dosyada olabilir veya bir uygulama ya da derleme kaynağı olarak gömülü bir XML belgesidir. Yalıtılmış bir uygulamanın bildirim dosyası, uygulamanın çalışma zamanında bağlanması gereken paylaşılan yan yana derlemelerin adlarını ve sürümlerini yönetmek üzere kullanılır. Yan yana derlemenin bildirimi; yan yana derlemelerin adlarını, sürümlerini, kaynaklarını ve bağımlı derlemelerini belirtir. Paylaşılan bir yan yana derlemenin bildirimi, %WINDIR%\WinSxS\Manifests\ klasörüne yüklenir. Özel bir derleme söz konusu olduğunda, bildirimi, DLL içine bir kimliği 1'e eşit olan bir kaynak olarak eklemenizi öneririz. Özel derlemeye DLL'ninki ile aynı adı verebilirsiniz. Daha fazla bilgi için bkz. [özel derlemeler hakkında](/windows/win32/SbsCs/about-private-assemblies-).

Yürütme sırasında Windows, karşılık gelen yan yana derlemeyi aramak ve yüklemek amacıyla uygulama bildirimindeki derleme bilgilerini kullanır. Yalıtılmış bir uygulama bir derleme bağımlılığı belirtiyorsa, işletim sistemi öncelikle %WINDIR%\WinSxS\ klasöründeki yerel derleme önbelleğindeki paylaşılan derlemeler arasında derleme için arama yapar. Gerekli derleme bulunamadığında, işletim sistemi uygulamanın dizin yapısının klasöründe özel bir derleme için arama yapar. Daha fazla bilgi için bkz. [Derleme arama sırası](/windows/win32/SbsCs/assembly-searching-sequence).

## <a name="changing-dependencies"></a>Bağımlılıkları değiştirme

[Yayımcı yapılandırma dosyalarını](/windows/win32/SbsCs/publisher-configuration-files) ve [uygulama yapılandırma dosyalarını](/windows/win32/SbsCs/application-configuration-files)değiştirerek bir uygulama dağıtıldıktan sonra yan yana derleme bağımlılıklarını değiştirebilirsiniz. Yayımcı ilkesi dosyası olarak da bilinen yayımcı yapılandırma dosyası; uygulamaları ve derlemeleri, genel olarak, yan yana derlemenin bir sürümünü kullanırken aynı derlemenin başka bir sürümünü kullanmaya yönlendiren bir XML dosyasıdır. Örneğin, bir hata düzeltmesi veya güvenlik düzeltmesi yan yana derleme için dağıtıldığında ve tüm uygulamaları düzeltilmiş sürümü kullanmak üzere yeniden yönlendirmek istediğinizde bağımlılığı değiştirebilirsiniz. Uygulama yapılandırma dosyası, belirli bir uygulamayı yan yana bir derlemenin bir sürümünden aynı derlemenin başka bir sürümünü kullanmaya yönlendiren bir XML dosyasıdır. Uygulama yapılandırma dosyasını, belirli bir uygulamayı yan yana derlemenin yayımcı yapılandırma dosyasında tanımlanandan farklı bir sürümünü kullanmaya yeniden yönlendirebilirsiniz. Daha fazla bilgi için bkz. [yapılandırma](/windows/win32/SbsCs/configuration).

## <a name="visual-c-libraries"></a>Visual C++ kitaplıkları

Visual Studio 2005 ve Visual Studio 2008'de; ATL, MFC, CRT, Standart C++, OpenMP ve MSDIA gibi yeniden dağıtılabilir kitaplıklar, yerel derleme önbelleğine paylaşılan yan yana derlemeler olarak dağıtılmıştır. Geçerli sürümde, yeniden dağıtılabilir kitaplıklar merkezi dağıtım kullanmaktadır. Varsayılan olarak, Visual Studio kullanılarak oluşturulan tüm uygulamalar, son ikiliye gömülü bildirimle oluşturulur ve bildirim Visual C++ kitaplıklarında ikilinin bağımlılıklarını açıklar. C++ uygulamaları için bildirim oluşturmayı anlamak için bkz. [C/C++ programları Için bildirim oluşturmayı anlama](understanding-manifest-generation-for-c-cpp-programs.md). Bildirim; kullandıkları ya da yerel dağıtım kullanan kitaplıklara statik olarak bağlı uygulamalar için gerekli değildir. Dağıtım hakkında daha fazla bilgi için bkz. [Visual C++ dağıtım](../windows/deployment-in-visual-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
