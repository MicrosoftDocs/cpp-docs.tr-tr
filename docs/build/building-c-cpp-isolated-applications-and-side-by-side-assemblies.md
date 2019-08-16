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
ms.openlocfilehash: b7deb68a441d392464dad8763f80bd4d9cdfcb17
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493352"
---
# <a name="building-cc-isolated-applications-and-side-by-side-assemblies"></a>C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma

Visual Studio, [yalıtılmış uygulamaların](/windows/win32/SbsCs/isolated-applications) ve [yan yana derlemelerin](/windows/win32/SbsCs/about-side-by-side-assemblies-)fikrini temel alarak Windows istemci uygulamalarına yönelik bir dağıtım modelini destekler. Varsayılan olarak, Visual Studio tüm yerel C/C++ uygulamalarını görsel C++ kitaplıklara bağımlılıklarını anlatmak için [bildirimleri](/windows/win32/sbscs/manifests) kullanan yalıtılmış uygulamalar olarak oluşturur.

Yalıtılmış uygulamalar olarakC++ C/programları oluşturmak bir dizi avantaj sunar. Örneğin, yalıtılmış bir uygulama, diğer C/C++ uygulamalar görsel C++ kitaplıkları yüklerken veya kaldırırken etkilenmemiştir. Yalıtılmış C++ uygulamalar tarafından kullanılan görsel kitaplıklar, uygulamanın yerel klasöründe veya yerel bütünleştirilmiş kod önbelleğine (WinSxS) yüklenmeye devam edebilir. Ancak, zaten dağıtılan uygulamalar C++ için görsel kitaplıkların bakımı bir [Yayımcı yapılandırma dosyası](/windows/win32/SbsCs/publisher-configuration)kullanılarak basitleştirilir. Yalıtılmış uygulama dağıtım modeli, belirli bir bilgisayarda çalışan C/C++ uygulamaların Visual C++ kitaplıklarının en son sürümünü kullandığından emin olmayı kolaylaştırır, ancak hala sistem olanağını açmaya devam ediyor. uygulamaların bağımlı dll 'lerine açık sürüm bağlamasını denetleyen Yöneticiler ve uygulama yazarları.

Bu bölümde, C/C++ uygulamanızı yalıtılmış bir uygulama olarak nasıl oluşturabileceğiniz ve bir bildirim kullanarak görsel C++ kitaplıklara bağlandığı nasıl emin olduğunuz açıklanmaktadır. Bu bölümdeki bilgiler birincil olarak yerel veya yönetilmeyen C++ uygulamalar için geçerlidir. Visual Studio ile oluşturulan yerel C++ uygulamaları dağıtma hakkında bilgi için bkz. [ C++ görsel dosyaları yeniden dağıtma](../windows/redistributing-visual-cpp-files.md).

## <a name="in-this-section"></a>Bu Bölümde

[Yalıtılmış Uygulama ve Yan Yana Derleme Kavramları](concepts-of-isolated-applications-and-side-by-side-assemblies.md)

[C/C++ Yalıtılmış Uygulamaları Derleme](building-c-cpp-isolated-applications.md)

[C/C++ Yan Yana Derlemeleri Oluşturma](building-c-cpp-side-by-side-assemblies.md)

[Nasıl yapılır: Kayıt Gerektirmeyen COM Bileşenlerini Derleme](how-to-build-registration-free-com-components.md)

[Nasıl yapılır: COM Bileşenlerini Kullanacak Yalıtılmış Uygulamalar Derleme](how-to-build-isolated-applications-to-consume-com-components.md)

[C/C++ Programları Bildirim Üretimini Anlama](understanding-manifest-generation-for-c-cpp-programs.md)

[C/C++ Yalıtılmış Uygulamalar ve Yan Yana Derlemeler ile İlgili Sorunları Giderme](troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)

## <a name="related-sections"></a>İlgili Bölümler

[Yalıtılmış uygulamalar ve yan yana derlemeler](/windows/win32/SbsCs/isolated-applications-and-side-by-side-assemblies-portal)

[Masaüstü uygulamaları dağıtma](../windows/deploying-native-desktop-applications-visual-cpp.md)