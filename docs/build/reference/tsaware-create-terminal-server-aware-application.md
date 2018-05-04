---
title: -TSAWARE (Terminal sunucusu algılayan uygulama oluştur) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /tsaware
- VC.Project.VCLinkerTool.TerminalServerAware
dev_langs:
- C++
helpviewer_keywords:
- Terminal Server
- /TSAWARE linker option
- Terminal Server, Terminal Server-aware applications
- -TSAWARE linker option
- TSAWARE linker option
ms.assetid: fe1c1846-de5b-4839-b562-93fbfe36cd29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e386c9024ea7736adb2766488c1c51c80ff7177b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="tsaware-create-terminal-server-aware-application"></a>/TSAWARE (Terminal Sunucusu Algılayan Uygulama Oluştur)
```  
/TSAWARE[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 / TSAWARE seçeneği program görüntünün isteğe bağlı üstbilgi IMAGE_OPTIONAL_HEADER DllCharacteristics alanında bir bayrak ayarlar. Terminal sunucusu bu bayrağı ayarlandığında, bazı değişiklikler uygulamaya yapmaz.  
  
 Bir uygulama Terminal sunucusu kullanan (aynı zamanda eski uygulamayı olarak da bilinir) değilse, Terminal sunucusu çok kullanıcılı bir ortamda düzgün çalışması için eski uygulamayı için bazı değişiklikleri yapar. Örneğin, her kullanıcı sisteminin Windows dizini alınırken yerine bir Windows klasörü alır, Terminal sunucusu sanal bir Windows klasörü oluşturun. Bu kullanıcıların kendi INI dosyalara erişim sağlar. Ayrıca, Terminal sunucusu bazı ayarlamalar için eski bir uygulama kayıt yapar. Bu değişiklikler eski uygulamayı Terminal sunucusu üzerinde yüklenmesini yavaşlatabilir.  
  
 Terminal sunucusu kullanan bir uygulama ise, onu gerekir INI dosyalarına dayanan ne yazma **HKEY_CURRENT_USER** Kurulum sırasında kayıt defteri.  
  
 / TSAWARE kullanın ve uygulamanızı hala INİ dosyaları kullanıyorsa, dosya sistemi tüm kullanıcılar tarafından paylaşılır. / TSAWARE uygulamanızla hala kabul edilebilir değilse bağlayabilirsiniz; Aksi takdirde /TSAWARE:NO kullanmanız gerekir.  
  
 / TSAWARE seçeneği, Windows ve konsol uygulamaları için varsayılan olarak etkindir. Bkz: [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) ve [/VERSION](../../build/reference/version-version-information.md) bilgi.  
  
 / TSAWARE sürücüleri, vxd ya da DLL'ler için geçerli değil.  
  
 / TSAWARE ile DUMPBIN uygulamanın bağlı olduğu [/HEADERS](../../build/reference/headers.md) belirten bilgi görüntüler.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **sistem** özellik sayfası.  
  
4.  Değiştirme **Terminal sunucusu** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)   
 [Kullanıcıya özgü bilgileri depolayan](http://msdn.microsoft.com/library/aa383452)   
 [Terminal Hizmetleri ortamında eski uygulamaları](https://msdn.microsoft.com/en-us/library/aa382957.aspx)