---
title: -MANIFEST (yan yana derleme bildirimi oluşturma) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateManifest
dev_langs:
- C++
helpviewer_keywords:
- -MANIFEST linker option
- /MANIFEST linker option
- MANIFEST linker option
ms.assetid: 98c52e1e-712c-4f49-b149-4d0a3501b600
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7cdf0f5d1d736635af3d7bf1a853e9002e072ef5
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43199119"
---
# <a name="manifest-create-side-by-side-assembly-manifest"></a>/MANIFEST (Yan Yana Derleme Bildirimi Oluşturma)
```  
/MANIFEST[:{EMBED[,ID=#]|NO}]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 / MANIFEST, bağlayıcının yan yana bildirim dosyası oluşturması gerektiğini belirtir. Bildirim dosyaları hakkında daha fazla bilgi için bkz: [bildirim dosyaları başvuru](/windows/desktop/SbsCs/manifest-files-reference).  
  
 /MANIFEST varsayılandır.  
  
 /MANIFEST: ekleme seçeneği, bağlayıcı bildirim dosyası görüntüde bir rt_manıfest türü kaynağı olarak gömülü belirtir. İsteğe bağlı `ID` parametredir bildirim için kullanılacak kaynak kimliği. Yürütülebilir dosya için 1 değerini kullanın. Özel bağımlılıklarını belirtmek etkinleştirmek için bir DLL için 2 değeri kullanın. Varsa `ID` parametresi belirtilmezse, varsayılan değer olan 2/dll seçenek ayarlanırsa; Aksi takdirde, varsayılan değer 1'dir.  
  
 Yürütülebilir dosyalar için bildirim dosyalarını, Visual Studio 2008'den itibaren kullanıcı hesabı denetimi (UAC) bilgisinin belirten bir bölümü içermelidir. /MANIFEST belirtir, ancak bunların hiçbiri belirtin [/MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md) ya da [/dll](../../build/reference/dll-build-a-dll.md), UAC düzeyinde ayarlanmış bir varsayılan UAC parça *asInvoker* bildirimine eklenir. UAC düzeyleri hakkında daha fazla bilgi için bkz. [/MANIFESTUAC (bildirimdeki UAC bilgilerini katıştırır)](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md).  
  
 UAC için varsayılan davranışı değiştirmek için aşağıdakilerden birini yapın:  
  
-   /MANIFESTUAC seçeneğini belirtin ve UAC düzeyi istenen değere ayarlayın.  
  
-   Veya bildiriminde UAC parçası oluşturmak istemiyorsanız: No seçeneğini belirtin.  
  
 /MANIFEST belirtmeyin ancak belirtin [/MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md) yorumları, bir bildirim dosyası oluşturulur. /MANIFEST:NO belirtirseniz bir bildirim dosyası oluşturulmaz.  
  
 /MANIFEST belirtirseniz, bildirim dosyasının adı, çıkış dosyasının, ancak dosya adına .manifest adı ile aynıdır. Örneğin, çıktı dosyanızın adı MyFile.exe ise, bildirim dosyası adı MyFile.exe.manifest ' dir.  /MANIFESTFILE belirtirseniz:*adı*, içinde belirttiğiniz addır bildirimin *adı*.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).  
  
2.  Genişletin **yapılandırma özellikleri** düğümü.  
  
3.  Genişletin **bağlayıcı** düğümü.  
  
4.  Seçin **bildirim dosyası** özellik sayfası.  
  
5.  Değiştirme **oluşturma bildirimi** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)