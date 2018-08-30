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
ms.openlocfilehash: 9caf6c9a47a667b57220b6bf577080d3548e94e9
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43198556"
---
# <a name="tsaware-create-terminal-server-aware-application"></a>/TSAWARE (Terminal Sunucusu Algılayan Uygulama Oluştur)
```  
/TSAWARE[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 / TSAWARE seçeneği program görüntüsünün isteğe bağlı üst bilgisindeki ımage_optıonal_header DllCharacteristics alanında bir bayrak ayarlar. Bu bayrak ayarlandığında Terminal sunucusu uygulamada bazı değişiklikler yapmaz.  
  
 Terminal sunucusu kullanan (eski bir uygulama olarak da bilinir) bir uygulama olmadığı durumlarda, Terminal sunucusu çok kullanıcılı bir ortamda düzgün çalışması için eski uygulamayı bazı değişiklikler yapar. Örneğin, her kullanıcı bir Windows klasörü sisteminin Windows dizini alınırken yerine alır, Terminal sunucusu sanal bir Windows klasörü oluşturun. Bu kullanıcıların kendi INİ dosyaları için erişim sağlar. Ayrıca, Terminal sunucusu kayıt defteri eski bir uygulama için bazı ayarlamalar yapar. Bu değişiklikler, Terminal sunucusu üzerinde eski uygulamayı yüklenmesini yavaş.  
  
 Terminal sunucusu kullanan bir uygulama ise, gerekir INI dosyalarına dayanan ne yazma **HKEY_CURRENT_USER** Kurulum sırasında kayıt defteri.  
  
 / TSAWARE kullandığınız ve uygulamanızı INİ dosyaları yine de kullanıyorsa, dosya sisteminin tüm kullanıcılar tarafından paylaşılır. Kabul edilebilir ise, / TSAWARE uygulamanızla hala bağlantı oluşturabilirsiniz; Aksi takdirde: No kullanmanız gerekir.  
  
 / TSAWARE seçeneği, Windows ve konsol uygulamaları için varsayılan olarak etkindir. Bkz: [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) ve [/VERSION](../../build/reference/version-version-information.md) bilgi.  
  
 / TSAWARE, sürücüleri, VxD veya dll için geçerli değil.  
  
 / TSAWARE ile DUMPBIN uygulamanın bağlı olduğu [OPTIONAL](../../build/reference/headers.md) belirlememişse bu bağlamda bilgileri görüntüler.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklayın **bağlayıcı** klasör.  
  
3.  Tıklayın **sistem** özellik sayfası.  
  
4.  Değiştirme **Terminal sunucusu** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)   
 [Kullanıcıya özgü bilgileri depolayan](/windows/desktop/TermServ/storing-user-specific-information)   
 [Terminal Hizmetleri ortamında eski uygulamaları](https://msdn.microsoft.com/library/aa382957.aspx)