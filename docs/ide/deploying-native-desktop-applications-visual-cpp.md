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
ms.openlocfilehash: ca3949c0cc2a505148da2a1edb8f07eaf1b6a1f7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662689"
---
# <a name="deploying-native-desktop-applications-visual-c"></a>Yerel Masaüstü Uygulamaları Dağıtma (Visual C++)

Dağıtım olarak diğer bilgisayarlara yüklenmesi bir tamamlanmış uygulamanın veya bileşenin dağıttığınız işlemidir. Bir geliştiricinin bilgisayarında uygulama oluşturulduğunda dağıtımı planlama başlatır. Uygulama yüklü ve bir kullanıcının bilgisayarında çalıştırmaya hazır olduğunda dağıtım sona erer.

Visual Studio, Windows uygulamalarını dağıtmak için farklı teknolojiler sağlar. Bunlar, ClickOnce dağıtımı ve Windows Installer dağıtımı içerir.

- Ortak dil çalışma zamanı (CLR) hedefleyen C++ uygulamaları dağıtmak için ClickOnce kullanılabilir — karışık, saf ve doğrulanabilen derlemeler. Bir yönetilen uygulamayı dağıtmak için Windows Installer kullanmanız mümkün olmakla birlikte, ClickOnce bildirim imzalama gibi .NET Framework güvenlik özelliklerinden aldığından kullanmanızı öneririz. ClickOnce yerel C++ uygulamalarının dağıtımını desteklemez. Daha fazla bilgi için [Visual C++ uygulamaları için ClickOnce dağıtımı](../ide/clickonce-deployment-for-visual-cpp-applications.md).

- Windows Yükleyici teknolojisi CLR'yi hedefleyen yerel C++ uygulamalarında veya C++ uygulamaları dağıtmak için kullanılabilir.

Belgelerin bu bölümdeki makaleleri Visual C++ uygulamasını yerel bir yükleme paketi ve önerilen yöntemleri için içermelidir hangi dosyaların bir desteklenen hedef platformu sağlayan herhangi bir bilgisayarda çalıştığından emin olmak nasıl ele almaktadır uygulamanızın bağımlı bileşenleri yeniden dağıtabilirsiniz.

## <a name="in-this-section"></a>Bu Bölümde

- [Visual C++ üzerinde Dağıtım](../ide/deployment-in-visual-cpp.md)

- [Dağıtım Kavramları](../ide/deployment-concepts.md)

- [Visual C++ Uygulaması Bağımlılıklarını Anlama](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)

- [Hangi DLL'lerin Yeniden Dağıtılacağını Belirleme](../ide/determining-which-dlls-to-redistribute.md)

- [Dağıtım Yöntemi Seçme](../ide/choosing-a-deployment-method.md)

- [Evrensel CRT dağıtım](universal-crt-deployment.md).

- [Visual C++ Dosyalarını Yeniden Dağıtma](../ide/redistributing-visual-cpp-files.md)

- [Dağıtım Örnekleri](../ide/deployment-examples.md)

- [Web İstemcisi Uygulamalarını Yeniden Dağıtma](../ide/redistributing-web-client-applications.md)

- [Visual C++ Uygulamaları için ClickOnce Dağıtımı](../ide/clickonce-deployment-for-visual-cpp-applications.md)

- [Önceki çalışma zamanı sürümünde C++/CLR uygulaması çalıştırma](../ide/running-a-cpp-clr-application-on-a-previous-runtime-version.md)

## <a name="related-sections"></a>İlgili Bölümler

- [C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)

- [Dağıtım](/dotnet/framework/deployment/index)

- [C/C++ Yalıtılmış Uygulamalar ve Yan Yana Derlemeler ile İlgili Sorunları Giderme](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)