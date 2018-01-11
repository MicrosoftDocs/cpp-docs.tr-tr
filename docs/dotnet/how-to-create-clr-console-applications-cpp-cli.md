---
title: "Nasıl yapılır: CLR konsol uygulamaları oluşturma (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- console applications, templates
- CLR console applications, project template
ms.assetid: e89bce3c-706f-4ae0-8a90-cb1a0f674e70
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ccb46ca7cd9cb7e1999a0be684eccf712006618e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-clr-console-applications-ccli"></a>Nasıl yapılır: CLR Konsol Uygulamaları Oluşturma (C++/CLI)
Konsol uygulaması şablonu temel proje başvuruları ve dosyaları zaten bir konsol uygulama projesi oluşturmak için kullanabilirsiniz.  
  
 Genellikle, bir konsol uygulaması bir tek başına yürütülebilir dosyaya derlendiği ancak bir grafik kullanıcı arabirimi yok. Bir kullanıcı, bir komut isteminde konsol uygulaması çalışır ve sorunu yönergeleri çalışan uygulama için komut istemine kullanır. Uygulamayı komut istemine çıktı bilgiler de sağlar. Bir konsol uygulaması immediacy programlama tekniklerinin bir kullanıcı arabirimi uygulamak için sorun olmadan öğrenmek için kullanışlı bir yoludur kolaylaştırır.  
  
 Bir proje oluşturmak için konsol uygulaması şablonunu kullandığınızda, bu başvurular ve dosyaları otomatik olarak ekler:  
  
-   Bu .NET Framework ad alanlarına başvurular:  
  
    -   [Sistem](https://msdn.microsoft.com/en-us/library/system.appdomainmanager.appdomainmanager.aspx)— temel sınıfları içerir ve genellikle tanımlayan temel sınıflar kullanılan değerleri ve başvuru veri türleri, olayları ve olay işleyicileri, arabirimler, öznitelikleri ve işlem özel durumları.  
  
    -   mscorlib — .NET Framework geliştirme destekleyen DLL derleme.  
  
-   Kaynak dosyalar:  
  
    -   Konsol (.cpp dosyası) — oluşturduğunuz uygulamada ana kaynak dosya ve giriş noktası. Proje .dll dosyasını ve proje ad alanını tanımlar. Bu dosyadaki kendi kodunuzu girin.  
  
    -   AssemblyInfo.cpp—Contains öznitelikleri, dosyalar, kaynaklar, türleri, sürüm bilgisini, imzalama bilgilerini ve projenin derleme meta verilerini değiştirmek için kullanabileceğiniz benzeri. Daha fazla bilgi için bkz: [derleme içeriklerini](/dotnet/framework/app-domains/assembly-contents).  
  
    -   Win32.pch adlı bir önceden derlenmiş üst bilgi dosyası ve StdAfx.obj adlı bir önceden derlenmiş türleri dosyası oluşturmak için Stdafx.cpp—Used.  
  
-   Üstbilgi dosyaları:  
  
    -   Win32.pch adlı bir önceden derlenmiş üst bilgi dosyası ve StdAfx.obj adlı bir önceden derlenmiş türleri dosyası oluşturmak için Stdafx.h—Used.  
  
    -   oluşturulan resource.h—A app.rc dosyası içerir.  
  
-   Kaynak dosyaları:  
  
    -   bir programın App.rc—the kaynak komut dosyası.  
  
    -   bir programın App.ico—the simge dosyası.  
  
-   ReadMe.txt—Describes projedeki dosyaları.  
  
## <a name="to-create-a-common-language-runtime-clr-console-app-project"></a>Ortak dil çalışma zamanı (CLR) konsol uygulama projesi oluşturmak için  
  
1.  Menü çubuğunda seçin **dosya**, **yeni**, **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda **yüklü şablonlar**seçin **Visual C++** düğümü, select **CLR** düğümünü ve ardından seçin Konsol uygulaması şablonu.  
  
3.  İçinde **adı** kutusuna, uygulamanız için benzersiz bir ad girin.  
  
     Diğer proje ve çözüm ayarlarını belirtebilirsiniz, ancak bunlar gerekli değildir.  
  
4.  Seçin **Tamam** düğmesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CLR projeleri](../ide/files-created-for-clr-projects.md)   


