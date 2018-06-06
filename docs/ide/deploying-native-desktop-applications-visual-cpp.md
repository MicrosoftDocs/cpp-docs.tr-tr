---
title: Yerel Masaüstü uygulamaları (Visual C++) dağıtma | Microsoft Docs
ms.custom: ''
ms.date: 05/11/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++]
- application deployment [C++]
- Visual C++, application deployment
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- distributing applications [C++]
ms.assetid: 37f1691e-d67c-41e4-926e-528a237a9bac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f4aa355c132b4c94f085cbdf7aa73785357d0f0
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34259250"
---
# <a name="deploying-native-desktop-applications-visual-c"></a>Yerel Masaüstü Uygulamaları Dağıtma (Visual C++)

Dağıtım olarak diğer bilgisayarlara yüklenmesi tamamlanmış uygulamanın veya bileşenin dağıttığınız işlemidir. Bir geliştiricinin bilgisayarında bir uygulama oluşturduğunuzda dağıtım planlama başlatır. Uygulama yüklü ve bir kullanıcının bilgisayarında çalıştırılmaya hazır olduğunda dağıtım sona erer.

Visual Studio, Windows uygulamalarını dağıtmak için farklı teknolojiler sağlar. ClickOnce dağıtımı ve Windows Installer dağıtımı bunlar.

- Ortak dil çalışma zamanı (CLR) hedeflemek C++ uygulamalarını dağıtmak için ClickOnce kullanılabilir — karışık, saf ve doğrulanabilen derlemeler. Yönetilen bir uygulamayı dağıtmak için Windows Installer kullanabilmenize karşın, bildirim imzalama gibi .NET Framework güvenlik özellikleri yararlandığı için ClickOnce kullanmanızı öneririz. ClickOnce yerel C++ uygulamalarının dağıtımını desteklemez. Daha fazla bilgi için bkz: [Visual C++ uygulamaları için ClickOnce dağıtımı](../ide/clickonce-deployment-for-visual-cpp-applications.md).

- Windows Installer teknolojisi CLR'yi hedefleyen yerel C++ uygulamaları ya da C++ uygulamaları dağıtmak için kullanılabilir.

Bu bölümdeki makaleleri belgelerin yerel Visual C++ uygulamasını bir yükleme paketi ve önerilen yöntemleri için içermelidir hangi dosyaların bir desteklenen hedef platformu sağlayan herhangi bir bilgisayarda çalıştığından emin olmak nasıl ele almaktadır. uygulamanızın bağımlı bileşenleri yeniden dağıtabilir.

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

- [Önceki bir çalışma zamanı sürümünde C++/CLR uygulaması çalıştırma](../ide/running-a-cpp-clr-application-on-a-previous-runtime-version.md)

## <a name="related-sections"></a>İlgili Bölümler

- [C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)

- [Dağıtım](/dotnet/framework/deployment/index)

- [C/C++ Yalıtılmış Uygulamalar ve Yan Yana Derlemeler ile İlgili Sorunları Giderme](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)