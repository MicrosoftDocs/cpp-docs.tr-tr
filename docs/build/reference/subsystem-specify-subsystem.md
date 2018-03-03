---
title: -SUBSYSTEM (alt sistemi belirt) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /subsystem
- VC.Project.VCLinkerTool.SubSystem
- VC.Project.VCLinkerTool.SubSystemVersion
dev_langs:
- C++
helpviewer_keywords:
- /SUBSYSTEM linker option
- SUBSYSTEM linker option
- -SUBSYSTEM linker option
- subsystem specifications
ms.assetid: d7b133cf-cf22-4da8-ab46-6552702c0b9b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3fd96a89ef4228835307f8f8f0d9fff5d61441f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="subsystem-specify-subsystem"></a>/SUBSYSTEM (Alt Sistemi Belirt)
```  
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|  
            EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|NATIVE|  
            POSIX|WINDOWS)  
            [,major[.minor]]  
```  
  
 BOOT_APPLICATION  
 Windows Önyükleme Ortamı'çalışan bir uygulama. Önyükleme uygulamalar hakkında daha fazla bilgi için bkz: [hakkında BCD](http://msdn.microsoft.com/library/windows/desktop/aa362639).  
  
 KONSOL  
 Win32 karakter modu uygulama. İşletim sistemi konsol uygulamaları için bir konsol sağlar. Varsa `main` veya `wmain` yerel kod için tanımlanan `int main(array<String ^> ^)` yönetilen kod için tanımlanan veya uygulamanın tamamen yapı `/clr:safe`, KONSOL varsayılan değerdir.  
  
 Genişletilebilir Bellenim Arabirimi  
 EFI_ * alt sistemleri. EFI belirtimi daha fazla bilgi için bkz. Örneğin, Intel Web sitesine bakın. En düşük sürümü ve varsayılan sürüm 1.0 ' dir.  
  
 YEREL  
 Windows NT Çekirdek modu sürücüleri. Bu seçenek, genellikle Windows sistemi bileşenleri için ayrılmıştır. Varsa [/DRIVER:WDM](../../build/reference/driver-windows-nt-kernel-mode-driver.md) belirtilmemişse, yerel varsayılan değerdir.  
  
 POSIX  
 POSIX alt sisteminde Windows NT ile çalıştırır uygulama.  
  
 WINDOWS  
 Uygulama kullanıcı etkileşimi için kendi windows oluşturduğundan bir konsol büyük olasılıkla gerektirmez. Varsa `WinMain` veya `wWinMain` yerel kod için tanımlanan veya `WinMain(HISTANCE *, HINSTANCE *, char *, int)` veya `wWinMain(HINSTANCE *, HINSTANCE *, wchar_t *, int)` tanımlanmış yönetilen kod için WINDOWS varsayılandır.  
  
 `Major`ve `minor` (isteğe bağlı)  
 Alt sistemi gerekli en düşük sürümü belirtin. 0 ile 65.535 aralıktaki ondalık sayılar bağımsız değişkenler. Açıklamalar daha fazla bilgi için bkz. Sürüm numaraları için hiçbir üst sınırları vardır.  
  
## <a name="remarks"></a>Açıklamalar  
 /SUBSYSTEM seçeneği yürütülebilir ortamını belirtir.  
  
 Giriş Noktası simgesi (veya giriş noktası işlevi) alt sistemi seçimi etkiler, bağlayıcı seçer.  
  
 İsteğe bağlı minimum ve varsayılan `major` ve `minor` alt sistemleri için sürüm numaraları aşağıdaki gibidir.  
  
|Alt sistemi|Minimum|Varsayılan|  
|---------------|-------------|-------------|  
|BOOT_APPLICATION|1.0|1.0|  
|KONSOL|(x 86) 5.01 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|6,00 (x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|  
|WINDOWS|(x 86) 5.01 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|6,00 (x86, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|  
|Yerel (ile sürücü: WDM)|(x 86) 1.00 1.10 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], ARM)|(x 86) 1.00 1.10 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], ARM)|  
|Yerel (olmadan /DRIVER:WDM)|(x 86) 4.00 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|(x 86) 4.00 5.02 ([!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]) 6.02 (ARM)|  
|POSIX|1.0|19.90|  
|EFI_APPLICATION, EFI_BOOT_SERVICE_DRIVER, EFI_ROM, EFI_RUNTIME_DRIVER|1.0|1.0|  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Bağlayıcı klasörü seçin.  
  
3.  Seçin **sistem** özellik sayfası.  
  
4.  Değiştirme `SubSystem` özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SubSystem%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)