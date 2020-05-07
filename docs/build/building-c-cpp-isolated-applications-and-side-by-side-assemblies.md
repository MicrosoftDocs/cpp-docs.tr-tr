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
ms.openlocfilehash: db2978c054362b6c329fb786d0f7da322d4c9201
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169883"
---
# <a name="building-cc-isolated-applications-and-side-by-side-assemblies"></a>C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma

Visual Studio, [yalıtılmış uygulamaların](/windows/win32/SbsCs/isolated-applications) ve [yan yana derlemelerin](/windows/win32/SbsCs/about-side-by-side-assemblies-)fikrini temel alarak Windows istemci uygulamalarına yönelik bir dağıtım modelini destekler. Varsayılan olarak, Visual Studio tüm yerel C/C++ uygulamalarını, Visual C++ kitaplıklarında bağımlılıklarını betimleyen [bildirimleri](/windows/win32/sbscs/manifests) kullanan yalıtılmış uygulamalar olarak oluşturur.

Yalıtılmış uygulamalar olarak C/C++ programlarının oluşturulması bir dizi avantaj sunar. Örneğin, başka C/C++ uygulamaları Visual C++ kitaplıklarını yüklerken veya kaldırırken yalıtılmış bir uygulama etkilenmez. Yalıtılmış uygulamalar tarafından kullanılan Visual C++ kitaplıkları, uygulamanın yerel klasöründe ya da yerel derleme önbelleğine (WinSxS) yüklenmeye devam edebilir. Ancak, zaten dağıtılan uygulamalar için Visual C++ kitaplıklarının bakımı, bir [Yayımcı yapılandırma dosyası](/windows/win32/SbsCs/publisher-configuration)kullanılarak basitleştirilerek basitleştirilebilir. Yalıtılmış uygulama dağıtım modeli, belirli bir bilgisayarda çalışan C/C++ uygulamalarının Visual C++ kitaplıklarının en son sürümünü kullandığından emin olmayı kolaylaştırır, ancak hala sistem yöneticileri ve uygulama yazarlarının, uygulamaların bağımlı dll 'lerine yönelik açık sürüm bağlamasını denetlemesine olanak sağlar.

Bu bölümde, C/C++ uygulamanızı yalıtılmış bir uygulama olarak nasıl oluşturabileceğiniz ve bir bildirim kullanarak Visual C++ kitaplıklarına bağlandığından emin olabilirsiniz. Bu bölümdeki bilgiler birincil olarak yerel veya yönetilmeyen C++ uygulamaları için geçerlidir. Visual Studio ile oluşturulan yerel C++ uygulamalarının dağıtımı hakkında bilgi için bkz. [Visual C++ dosyalarını yeniden dağıtma](../windows/redistributing-visual-cpp-files.md).

## <a name="in-this-section"></a>Bu Bölümde

[Yalıtılmış uygulamalar ve yan yana derlemeler için kavramlar](concepts-of-isolated-applications-and-side-by-side-assemblies.md)

[C/C++ yalıtılmış uygulamaları oluşturma](building-c-cpp-isolated-applications.md)

[C/C++ Yan Yana Derlemeleri Oluşturma](building-c-cpp-side-by-side-assemblies.md)

[Nasıl Yapılır: Kayıt Gerektirmeyen COM Bileşenlerini Derleme](how-to-build-registration-free-com-components.md)

[Nasıl Yapılır: COM Bileşenlerini Kullanacak Yalıtılmış Uygulamalar Derleme](how-to-build-isolated-applications-to-consume-com-components.md)

[C/C++ Programları Bildirim Üretimini Anlama](understanding-manifest-generation-for-c-cpp-programs.md)

[C/C++ Yalıtılmış Uygulamalar ve Yan Yana Derlemeler ile İlgili Sorunları Giderme](troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)

## <a name="related-sections"></a>İlgili Bölümler

[Yalıtılmış uygulamalar ve yan yana derlemeler](/windows/win32/SbsCs/isolated-applications-and-side-by-side-assemblies-portal)

[Masaüstü uygulamaları dağıtma](../windows/deploying-native-desktop-applications-visual-cpp.md)
