---
title: "-ENTRY (giriş noktası simgesi) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /entry
- VC.Project.VCLinkerTool.EntryPointSymbol
dev_langs:
- C++
helpviewer_keywords:
- starting address
- -ENTRY linker option
- /ENTRY linker option
- ENTRY linker option
ms.assetid: 26c62ba2-4f52-4882-a7bd-7046a0abf445
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5ebaf9a8723f06b6fab8577abf283f6eec69aa25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="entry-entry-point-symbol"></a>/ENTRY (Giriş Noktası Simgesi)
```  
/ENTRY:function  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 *işlevi*  
 Kullanıcı tanımlı başlangıç belirten işlevi bir .exe dosyası veya DLL için adres.  
  
## <a name="remarks"></a>Açıklamalar  
 / Entry seçeneğini bir giriş noktası işlevi bir .exe dosyası ya da DLL için başlangıç adresi olarak belirtir.  
  
 İşlevi kullanmak için tanımlanmalıdır `__stdcall` çağırma. Parametreler ve dönüş değeri program bir konsol uygulaması, bir windows uygulaması veya bir DLL olup olmadığını bağlıdır. Giriş Noktası C çalışma zamanı kitaplığı doğru başlatılmadı ve C++ oluşturucuları statik nesneleri için yürütülen şekilde ayarlayın bağlayıcı izin vermeniz önerilir.  
  
 Varsayılan olarak, başlangıç adresi C Çalışma Zamanı Kitaplığı'ndan bir işlev adı değil. Bağlayıcı aşağıdaki tabloda gösterildiği gibi program özniteliklerine göre seçer.  
  
|İşlev adı|İçin varsayılan|  
|-------------------|-----------------|  
|**mainCRTStartup** (veya **wmainCRTStartup**)|/SUBSYSTEM:CONSOLE kullanan bir uygulamayı; çağrıları `main` (veya `wmain`)|  
|**WinMainCRTStartup** (veya **wWinMainCRTStartup**)|/SUBSYSTEM kullanan bir uygulamayı:**WINDOWS**; çağrıları `WinMain` (veya `wWinMain`), hangi tanımlanmalıdır kullanmak için`__stdcall`|  
|**_DllMainCRTStartup**|DLL; çağrıları `DllMain` varsa, hangi tanımlanmalıdır kullanmak için`__stdcall`|  
  
 Varsa [/dll](../../build/reference/dll-build-a-dll.md) veya [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) seçeneği belirtilmezse, bağlayıcı mı bağlı olarak bir alt sistemi ve giriş noktası seçer `main` veya `WinMain` tanımlanır.  
  
 İşlevler `main`, `WinMain`, ve `DllMain` kullanıcı tarafından tanımlanan giriş noktasının üç formlar.  
  
 Yönetilen resim oluşturulurken/Entry için belirtilen işlev imzası olması gerekir (LPVOID *var1*, DWORD *var2*, LPVOID *var3*).  
  
 Kendi tanımlama hakkında bilgi için `DllMain` giriş noktası bkz [DLL'ler ve Visual C++ çalışma zamanı kitaplığı davranışı](../../build/run-time-library-behavior.md) .  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **Gelişmiş** özellik sayfası.  
  
4.  Değiştirme **giriş noktası** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EntryPointSymbol%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)