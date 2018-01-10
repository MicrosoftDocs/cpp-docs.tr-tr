---
title: "Dağıtım Kavramları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Windows Installer [C++]
- dependencies [C++], application deployment and
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- libraries [C++], application deployment issues
ms.assetid: ebd7f246-ab54-40e8-87fa-dac02c0047b3
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b40865266548067e2dda3782e66802c0dbe2844e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="deployment-concepts"></a>Dağıtım Kavramları
Bu bölümde, C++ uygulamaları dağıtmak için ana hususlar anlatılmaktadır.  
  
## <a name="windows-installer-deployment-in-c"></a>C++'ta Windows Installer dağıtımı  
 Visual C++ projeleri, genellikle geleneksel Windows Installer Kurulum dağıtım için kullanın. Windows Installer dağıtımı hazırlamak için setup.exe dosyasını uygulamanızda paketini ve Installer (.msi) paketi ile birlikte bu dosyayı dağıtın. Kullanıcılar daha sonra uygulamanızı yüklemek için Setup.exe'yi çalıştırın.  
  
 Çözümünüze bir kurulum projesi ekleyerek uygulamanızı paketini; yapılandırıldığında, Kurulum ve yükleyici, kullanıcılara dağıttığınız paket dosyaları oluşturur. Daha fazla bilgi için bkz: [dağıtım yöntemi seçme](../ide/choosing-a-deployment-method.md).  
  
## <a name="library-dependencies"></a>Kitaplık bağımlılıkları  
 C/C++ uygulamasına Visual C++ kitaplıkları tarafından sağlanan işlevsellik kullanılarak yapılandırıldığında, çalışma zamanında o kitaplıkların varlıklarına bağımlı olur. Uygulamayı çalıştırmak için sırayla, statik veya dinamik olarak gerekli Visual C++ kitaplıkları Bağla gerekir. Bunu yüklenebilmesi için bir uygulama dinamik olarak bağlantılar için bir Visual C++ Kitaplık, ardından bu kitaplığın çalıştığında mevcut olması gerekir. Uygulama için bir Visual C++ Kitaplık statik olarak bağlanıyorsa, diğer taraftan, ardından bunu ilgili DLL'lerin kullanıcının bilgisayarda mevcut olması gerekmez. Statik bağlama, ancak uygulama dosyalarının boyutunu artırma ve Bakım potansiyel olarak çok daha zorlaşır gibi bazı olumsuz etkileri vardır. Daha fazla bilgi için bkz: [DLL'leri kullanmanın yararları](../build/dlls-in-visual-cpp.md#advantages-of-using-dlls).  
  
## <a name="packaging-and-redistributing"></a>Paketleme ve dağıtma  
 Visual C++ kitaplıkları DLL'ler olarak paketlenir ve C/C++ uygulamaları için gerekli tüm kitaplıklar geliştiricinin bilgisayarında Visual Studio tarafından yüklenir. Ancak, kullanıcılarınızın uygulamanıza dağıtırken, bunları uygulamanızı çalıştırmak için Visual Studio'yu yüklemek için gerektirecek şekilde, çoğu durumda uygun değil. Yalnızca doğru çalışması için uygulamanız tarafından gerekli olan Visual C++ bölümlerini yeniden dağıtmak önemlidir.  
  
 Paketleme ve dağıtma hakkında daha fazla bilgi için aşağıdaki konulara bakın:  
  
-   [Hangi DLL'lerin yeniden dağıtılacağını belirleme](../ide/determining-which-dlls-to-redistribute.md).  
  
-   [Dağıtım yöntemi seçme](../ide/choosing-a-deployment-method.md).  
  
 Dağıtım örnekleri ve sorun giderme hakkında öneriler için bkz:  
  
-   [Dağıtım örnekleri](../ide/deployment-examples.md).  
  
-   [Sorun giderme C/C++ yalıtılmış uygulamalar ve yan yana derlemeler](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Masaüstü uygulamaları dağıtma](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Visual C++ uygulaması bağımlılıklarını anlama](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)   
 [Windows Installer dağıtımı](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)