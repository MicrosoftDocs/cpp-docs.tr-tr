---
title: C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma
ms.date: 05/06/2019
helpviewer_keywords:
- isolated applications [C++]
- WinSxS [C++]
- native assembly cache [C++]
- builds [C++], isolated applications
- side-by-side applications [C++]
- builds [C++], side-by-side assemblies
ms.assetid: 9465904e-76f7-48bd-bb3f-c55d8f1699b6
ms.openlocfilehash: 8164ede1379e573b08f699cd55c199f6fa228823
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220979"
---
# <a name="building-cc-isolated-applications-and-side-by-side-assemblies"></a>C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma

Visual Studio fikrini tabanlı Windows istemci uygulamaları için bir dağıtım modeli destekler [yalıtılmış uygulamalar](/windows/desktop/SbsCs/isolated-applications) ve [yan yana derlemeler](/windows/desktop/SbsCs/about-side-by-side-assemblies-). Varsayılan olarak, Visual Studio tüm yerel C oluşturur /C++ uygulamaları kullanan yalıtılmış uygulamalar olarak [bildirimlerini](/windows/desktop/sbscs/manifests) görselde bağımlılıklarını tanımlamak için C++ kitaplıkları.

C/C++ programları olarak yalıtılmış uygulamalar derleme çeşitli avantajlar sunar. Örneğin, diğer C/C++ uygulamaları yüklediğinizde veya Visual C++ kitaplıklarının kaldırma yalıtılmış bir uygulama etkilenmez. Yalıtılmış uygulamalar tarafından kullanılan visual C++ kitaplıkları, yine de uygulamanın yerel klasörü veya (WinSxS); yerel derleme önbelleğine yükleme dağıtılabilir zaten dağıtılmış uygulamaları kullanılarak basitleştirilebilir için Visual C++ kitaplıklarının ancak bakım bir [yayımcı yapılandırma dosyası](/windows/desktop/SbsCs/publisher-configuration). Yalıtılmış uygulama dağıtım modeli hala olasılığını sistem yöneticileri için açık bırakarak belirli bir bilgisayarda çalışan bir C/C++ uygulamalarında Visual C++ kitaplıklarının en son sürümünü kullandığınızdan emin olmak kolaylaştırır ve uygulama yazarları, sürüm bağlama bunların bağımlı dll uygulamaları denetlemek için.

Bu bölümde ele alınmaktadır nasıl yalıtılmış bir uygulama olarak C/C++ uygulamanızı derleme ve bildirim kullanarak Visual C++ kitaplıklarına bağlar emin olun. Bu bölümdeki bilgiler, öncelikle yerel ya da yönetilmeyen, geçerli C++ uygulamalar. Dağıtma hakkında bilgi yerel C++ bkz. Visual Studio ile oluşturulmuş uygulamalar [yeniden dağıtma Visual C++ dosyaları](../windows/redistributing-visual-cpp-files.md).

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