---
title: Yerel Masaüstü Uygulamaları Dağıtma (Visual C++)
ms.date: 05/11/2018
helpviewer_keywords:
- deploying applications [C++]
- application deployment [C++]
- Visual C++, application deployment
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- distributing applications [C++]
ms.assetid: 37f1691e-d67c-41e4-926e-528a237a9bac
ms.openlocfilehash: 46ced4ac5f7952a9b7f66418ea037e053b16e9be
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58787069"
---
# <a name="deploying-native-desktop-applications-visual-c"></a>Yerel Masaüstü Uygulamaları Dağıtma (Visual C++)

Dağıtım olarak diğer bilgisayarlara yüklenmesi bir tamamlanmış uygulamanın veya bileşenin dağıttığınız işlemidir. Bir geliştiricinin bilgisayarında uygulama oluşturulduğunda dağıtımı planlama başlatır. Uygulama yüklü ve bir kullanıcının bilgisayarında çalıştırmaya hazır olduğunda dağıtım sona erer.

Visual Studio, Windows uygulamalarını dağıtmak için farklı teknolojiler sağlar. Bunlar, ClickOnce dağıtımı ve Windows Installer dağıtımı içerir.

- Ortak dil çalışma zamanı (CLR) hedefleyen C++ uygulamaları dağıtmak için ClickOnce kullanılabilir — karışık, saf ve doğrulanabilen derlemeler. Bir yönetilen uygulamayı dağıtmak için Windows Installer kullanmanız mümkün olmakla birlikte, ClickOnce bildirim imzalama gibi .NET Framework güvenlik özelliklerinden aldığından kullanmanızı öneririz. ClickOnce yerel C++ uygulamalarının dağıtımını desteklemez. Daha fazla bilgi için [Visual C++ uygulamaları için ClickOnce dağıtımı](clickonce-deployment-for-visual-cpp-applications.md).

- Windows Yükleyici teknolojisi CLR'yi hedefleyen yerel C++ uygulamalarında veya C++ uygulamaları dağıtmak için kullanılabilir.

Belgelerin bu bölümdeki makaleleri Visual C++ uygulamasını yerel bir yükleme paketi ve önerilen yöntemleri için içermelidir hangi dosyaların bir desteklenen hedef platformu sağlayan herhangi bir bilgisayarda çalıştığından emin olmak nasıl ele almaktadır uygulamanızın bağımlı bileşenleri yeniden dağıtabilirsiniz.

## <a name="in-this-section"></a>Bu Bölümde

- [Visual C++ üzerinde Dağıtım](deployment-in-visual-cpp.md)

- [Dağıtım Kavramları](deployment-concepts.md)

- [Visual C++ Uygulaması Bağımlılıklarını Anlama](understanding-the-dependencies-of-a-visual-cpp-application.md)

- [Hangi DLL'lerin Yeniden Dağıtılacağını Belirleme](determining-which-dlls-to-redistribute.md)

- [Dağıtım Yöntemi Seçme](choosing-a-deployment-method.md)

- [Evrensel CRT dağıtım](universal-crt-deployment.md).

- [Visual C++ Dosyalarını Yeniden Dağıtma](redistributing-visual-cpp-files.md)

- [Dağıtım Örnekleri](deployment-examples.md)

- [Web İstemcisi Uygulamalarını Yeniden Dağıtma](redistributing-web-client-applications.md)

- [Visual C++ Uygulamaları için ClickOnce Dağıtımı](clickonce-deployment-for-visual-cpp-applications.md)

- [Önceki çalışma zamanı sürümünde C++/CLR uygulaması çalıştırma](running-a-cpp-clr-application-on-a-previous-runtime-version.md)

## <a name="related-sections"></a>İlgili Bölümler

- [C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)

- [Dağıtım](/dotnet/framework/deployment/index)

- [C/C++ Yalıtılmış Uygulamalar ve Yan Yana Derlemeler ile İlgili Sorunları Giderme](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)