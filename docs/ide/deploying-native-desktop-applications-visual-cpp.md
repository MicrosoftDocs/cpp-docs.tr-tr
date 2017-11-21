---
title: "Yerel Masaüstü uygulamaları (Visual C++) dağıtma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- deploying applications [C++]
- application deployment [C++]
- Visual C++, application deployment
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- distributing applications [C++]
ms.assetid: 37f1691e-d67c-41e4-926e-528a237a9bac
caps.latest.revision: "28"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7a8dcf4a49813ae108edb23b50676e751db5e2f1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="deploying-native-desktop-applications-visual-c"></a>Yerel Masaüstü Uygulamaları Dağıtma (Visual C++)
Dağıtım olarak diğer bilgisayarlara yüklenmesi tamamlanmış uygulamanın veya bileşenin dağıttığınız işlemidir. Bir geliştiricinin bilgisayarında bir uygulama oluşturduğunuzda dağıtım planlama başlatır. Uygulama yüklü ve bir kullanıcının bilgisayarında çalıştırılmaya hazır olduğunda dağıtım sona erer.  
  
 Visual Studio, Windows uygulamalarını dağıtmak için farklı teknolojiler sağlar. ClickOnce dağıtımı ve Windows Installer dağıtımı bunlar.  
  
-   Ortak dil çalışma zamanı (CLR) hedeflemek C++ uygulamalarını dağıtmak için ClickOnce kullanılabilir — karışık, saf ve doğrulanabilen derlemeler. Yönetilen bir uygulamayı dağıtmak için Windows Installer kullanabilmenize karşın, bildirim imzalama gibi .NET Framework güvenlik özellikleri yararlandığı için ClickOnce kullanmanızı öneririz. ClickOnce yerel C++ uygulamalarının dağıtımını desteklemez. Daha fazla bilgi için bkz: [Visual C++ uygulamaları için ClickOnce dağıtımı](../ide/clickonce-deployment-for-visual-cpp-applications.md).  
  
-   Windows Installer teknolojisi CLR'yi hedefleyen yerel C++ uygulamaları ya da C++ uygulamaları dağıtmak için kullanılabilir.  
  
 Bu bölümdeki makaleleri belgelerin yerel Visual C++ uygulamasını bir yükleme paketi ve önerilen yöntemleri için içermelidir hangi dosyaların bir desteklenen hedef platformu sağlayan herhangi bir bilgisayarda çalıştığından emin olmak nasıl ele almaktadır. uygulamanızın bağımlı bileşenleri yeniden dağıtabilir.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Visual C++ üzerinde dağıtım](../ide/deployment-in-visual-cpp.md)  
  
 [Dağıtım Kavramları](../ide/deployment-concepts.md)  
  
 [Visual C++ uygulaması bağımlılıklarını anlama](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)  
  
 [Hangi DLL'lerin yeniden dağıtılacağını belirleme](../ide/determining-which-dlls-to-redistribute.md)  
  
 [Dağıtım yöntemi seçme](../ide/choosing-a-deployment-method.md)  
  
 [Visual C++ dosyalarını yeniden dağıtma](../ide/redistributing-visual-cpp-files.md)  
  
 [Dağıtım örnekleri](../ide/deployment-examples.md)  
  
 [Web istemcisi uygulamalarını yeniden dağıtma](../ide/redistributing-web-client-applications.md)  
  
 [Visual C++ uygulamaları için ClickOnce dağıtımı](../ide/clickonce-deployment-for-visual-cpp-applications.md)  
  
 [Önceki bir çalışma zamanı sürümünde C++/CLR uygulaması çalıştırma](../ide/running-a-cpp-clr-application-on-a-previous-runtime-version.md)  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [C/C++ yalıtılmış uygulamaları ve yan yana derlemeler](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)  
  
 [Dağıtım](/dotnet/framework/deployment/index)  
  
 [Sorun giderme C/C++ yalıtılmış uygulamaları ve yan yana derlemeleri oluşturma](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)