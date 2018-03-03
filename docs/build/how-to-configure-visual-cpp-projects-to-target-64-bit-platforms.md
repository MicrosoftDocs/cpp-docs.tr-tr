---
title: "Nasıl yapılır: 64 Bit hedeflemek için Visual C++ projeleri x64 yapılandırma platformları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- platforms [C++], 64-bit
- 64-bit programming [C++], configuring projects
- project configurations [C++]
ms.assetid: 2b9ae001-df36-4750-83b2-982145d632ad
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7e651d28af3bd8635691d6a54d6c4cca8eb8c160
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-configure-visual-c-projects-to-target-64-bit-x64-platforms"></a>Nasıl yapılır: 64 Bit hedeflemek için Visual C++ projeleri x64 yapılandırma platformları

64 bit hedeflemek için C++ uygulamalar ayarlamak x64 platformlar için Visual Studio IDE içinde proje yapılandırmaları kullanın. Ayrıca, bir 64-bit proje yapılandırması Win32 Proje ayarlarını geçirebilirsiniz.  
  
### <a name="to-set-up-c-applications-to-target-64-bit-platforms"></a>64 bit platformları hedeflemesi için C++ uygulamalar ayarlamak için  
  
1.  Yapılandırmak istediğiniz C++ projesini açın.  
  
2.  Proje özellik sayfalarını açın. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../ide/working-with-project-properties.md).  
  
    > [!NOTE]
    >  .NET projelerde olduğundan emin olun **yapılandırma özellikleri** düğümü ya da kendi alt düğümlerinden biri seçildiğinde,  **\<Projectname > özellik sayfaları** iletişim kutusu; Aksi halde,  **Configuration Manager** düğmesi kullanılamıyor kalır.  
  
3.  Seçin **Configuration Manager** açmak için düğmeye **Configuration Manager** iletişim kutusu.  
  
4.  İçinde **etkin çözüm platformu** aşağı açılan listesinden,  **\<yeni... >** açmak için seçeneği **yeni çözüm platformu** iletişim kutusu.  
  
5.  İçinde **yazın veya seçin yeni platformu** açılan listesinden, select 64 bit hedef platformu.  
  
    > [!NOTE]
    >  İçinde **yeni çözüm platformu** kullanabileceğiniz iletişim kutusu, **kopyalama ayarlarından** mevcut proje ayarları yeni 64-bit proje yapılandırması kopyalamak için seçeneği.  
  
6.  Seçin **Tamam** düğmesi. Önceki adımda seçtiğiniz platform altında görünür **etkin çözüm platformu** içinde **Configuration Manager** iletişim kutusu.  
  
7.  Seçin **Kapat** düğmesini **Configuration Manager** iletişim kutusuna ve ardından **Tamam** düğmesini  **\<Projectname > Özellik sayfaları** iletişim kutusu.  
  
### <a name="to-copy-win32-project-settings-into-a-64-bit-project-configuration"></a>Win32 Proje ayarları bir 64-bit proje yapılandırmasını kopyalamak için  
  
-   Zaman **yeni çözüm platformu** iletişim kutusu, hedef bir 64-bit platformu için bir proje olarak ayarlamanız sırada açıksa **ayarları kopyalamak** aşağı açılan listesinden, **Win32**. Bu proje ayarları üzerinde proje düzeyi otomatik olarak güncelleştirilir:  
  
    -   [/Makine](../build/reference/machine-specify-target-platform.md) bağlayıcı seçeneği ayarlanmış **/MACHINE:X 64**.  
  
    -   **Çıkış kaydedin** olan kapalı. Daha fazla bilgi için bkz: [bağlayıcı özellik sayfaları](../ide/linker-property-pages.md).  
  
    -   **Hedef ortamı** ayarlanır **/env x64**. Daha fazla bilgi için bkz: [MIDL özellik sayfaları: Genel](../ide/midl-property-pages-general.md).  
  
    -   **Parametreleri doğrulayın** temizlendi ve varsayılan değeri sıfırlayın. Daha fazla bilgi için bkz: [MIDL özellik sayfaları: Gelişmiş](../ide/midl-property-pages-advanced.md).  
  
    -   Varsa **hata ayıklama bilgileri biçimi** ayarlandı **/zı** Win32 Proje yapılandırması sonra ayarlanır **/zi** 64-bit proje yapılandırması. Daha fazla bilgi için bkz: [/Z7, / zi, /zı (hata ayıklama bilgileri biçimi)](../build/reference/z7-zi-zi-debug-information-format.md).  
  
    > [!NOTE]
    >  Dosya düzeyinde kılınırsa bu proje özellikleri hiçbiri olarak değiştirilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[.NET framework 64-bit uygulamalar](/dotnet/framework/64-bit-apps)   
[Visual C++ 64-bit, x64 için yapılandırma hedefleri](../build/configuring-programs-for-64-bit-visual-cpp.md)   
[64 Bit uygulamalarda hata ayıklama](/visualstudio/debugger/debug-64-bit-applications)