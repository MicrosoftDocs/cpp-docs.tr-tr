---
title: C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma
ms.date: 11/04/2016
helpviewer_keywords:
- isolated applications [C++]
- WinSxS [C++]
- native assembly cache [C++]
- builds [C++], isolated applications
- side-by-side applications [C++]
- builds [C++], side-by-side assemblies
ms.assetid: 9465904e-76f7-48bd-bb3f-c55d8f1699b6
ms.openlocfilehash: b962796c3bf32bc312d3047535ae90a40a37094d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196696"
---
# <a name="building-cc-isolated-applications-and-side-by-side-assemblies"></a>C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma

Visual C++ fikrini tabanlı Windows istemci uygulamaları için bir dağıtım modelini destekler [yalıtılmış uygulamalar](/windows/desktop/SbsCs/isolated-applications) ve [yan yana derlemeler](/windows/desktop/SbsCs/about-side-by-side-assemblies-). Varsayılan olarak, Visual C++ tüm yerel C/C++ uygulamaları kullanan yalıtılmış uygulamalar derleme [bildirimlerini](/windows/desktop/sbscs/manifests) Visual C++ kitaplıklarındaki bağımlılıklarını tanımlamak için.

C/C++ programları olarak yalıtılmış uygulamalar derleme çeşitli avantajlar sunar. Örneğin, diğer C/C++ uygulamaları yüklediğinizde veya Visual C++ kitaplıklarının kaldırma yalıtılmış bir uygulama etkilenmez. Yalıtılmış uygulamalar tarafından kullanılan visual C++ kitaplıkları, yine de uygulamanın yerel klasörü veya (WinSxS); yerel derleme önbelleğine yükleme dağıtılabilir zaten dağıtılmış uygulamaları kullanılarak basitleştirilebilir için Visual C++ kitaplıklarının ancak bakım bir [yayımcı yapılandırma dosyası](/windows/desktop/SbsCs/publisher-configuration). Yalıtılmış uygulama dağıtım modeli hala olasılığını sistem yöneticileri için açık bırakarak belirli bir bilgisayarda çalışan bir C/C++ uygulamalarında Visual C++ kitaplıklarının en son sürümünü kullandığınızdan emin olmak kolaylaştırır ve uygulama yazarları, sürüm bağlama bunların bağımlı dll uygulamaları denetlemek için.

Bu bölümde ele alınmaktadır nasıl yalıtılmış bir uygulama olarak C/C++ uygulamanızı derleme ve bildirim kullanarak Visual C++ kitaplıklarına bağlar emin olun. Bu bölümdeki bilgiler, öncelikle yerel veya yönetilmeyen, Visual C++ uygulamaları için geçerlidir. Visual C++ ile oluşturulan yerel uygulamalarını dağıtma hakkında daha fazla bilgi için bkz: [Visual C++ dosyalarını yeniden dağıtma](../windows/redistributing-visual-cpp-files.md).

## <a name="in-this-section"></a>Bu Bölümde

[Yalıtılmış Uygulama ve Yan Yana Derleme Kavramları](concepts-of-isolated-applications-and-side-by-side-assemblies.md)

[C/C++ Yalıtılmış Uygulamaları Derleme](building-c-cpp-isolated-applications.md)

[C/C++ Yan Yana Derlemeleri Oluşturma](building-c-cpp-side-by-side-assemblies.md)

[Nasıl yapılır: Kayıt Gerektirmeyen COM Bileşenlerini Derleme](how-to-build-registration-free-com-components.md)

[Nasıl yapılır: COM Bileşenlerini Kullanacak Yalıtılmış Uygulamalar Derleme](how-to-build-isolated-applications-to-consume-com-components.md)

[C/C++ Programları Bildirim Üretimini Anlama](understanding-manifest-generation-for-c-cpp-programs.md)

[C/C++ Yalıtılmış Uygulamalar ve Yan Yana Derlemeler ile İlgili Sorunları Giderme](troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)

## <a name="related-sections"></a>İlgili Bölümler

[Yalıtılmış uygulamalar ve yan yana derlemeler](/windows/desktop/SbsCs/isolated-applications-and-side-by-side-assemblies-portal)

[Masaüstü uygulamalarını dağıtma](../windows/deploying-native-desktop-applications-visual-cpp.md)