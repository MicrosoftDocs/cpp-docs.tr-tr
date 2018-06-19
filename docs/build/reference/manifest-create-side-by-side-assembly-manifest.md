---
title: -Bildirim (yan yana derleme bildirimi oluşturma) | Microsoft Docs
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
ms.openlocfilehash: 5486eca41c93adb074cde6dc9602149d7dfa4f13
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378320"
---
# <a name="manifest-create-side-by-side-assembly-manifest"></a>/MANIFEST (Yan Yana Derleme Bildirimi Oluşturma)
```  
/MANIFEST[:{EMBED[,ID=#]|NO}]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 / BİLDİRİMİ bağlayıcı bir yan yana bildirim dosyası oluşturmak belirtir. Bildirim dosyaları hakkında daha fazla bilgi için bkz: [bildirim dosyaları başvuru](http://msdn.microsoft.com/library/aa375632).  
  
 /MANIFEST varsayılandır.  
  
 /MANIFEST: ekleme seçeneği, bağlayıcı bildirim dosyası görüntüde RT_MANIFEST türde bir kaynak gömülü belirtir. İsteğe bağlı `ID` parametredir bildirim için kullanılacak kaynak kimliği. 1 değeri, yürütülebilir bir dosya için kullanın. Özel bağımlılıklarını belirt etkinleştirmek için bir DLL için 2 değerini kullanın. Varsa `ID` parametresi belirtilmezse, varsayılan değer olan 2/dll seçeneği ayarlarsanız; Aksi takdirde, varsayılan değer 1'dir.  
  
 Visual Studio 2008'den itibaren bildirim dosyası yürütülebilir dosyaları için kullanıcı hesabı denetimi (UAC) bilgi belirten bir bölüm içerir. /MANIFEST belirtin, ancak ne belirtin [/MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md) ya da [/dll](../../build/reference/dll-build-a-dll.md), UAC düzeyi ayarlanmış varsayılan UAC parçası *asInvoker* bildirimine eklenir. UAC düzeyleri hakkında daha fazla bilgi için bkz: [/MANIFESTUAC (bildirimdeki UAC bilgilerini katıştırır)](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md).  
  
 UAC için varsayılan davranışı değiştirmek için şunlardan birini yapın:  
  
-   /MANIFESTUAC seçeneğini belirtin ve UAC düzeyi istenen değere ayarlayın.  
  
-   Veya UAC parçası bildirim oluşturmak üzere istemiyorsanız /MANIFESTUAC:NO seçeneğini belirtin.  
  
 /MANIFEST belirtmeyin ancak belirtin [/MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md) yorumları, bir bildirim dosyası oluşturulur. /MANIFEST:NO belirtirseniz, bir bildirim dosyası oluşturulmaz.  
  
 /MANIFEST belirtirseniz, bildirim dosyasının adı adı, çıktı dosyanızın ancak dosya adına eklenmiş .manifest ile aynıdır. Örneğin, çıktı dosyası adı MyFile.exe ise, yayılma dosyası adı MyFile.exe.manifest ' dir.  /MANIFESTFILE belirtirseniz:*adı*, bildirim içinde belirttiğiniz adıdır *adı*.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri** düğümü.  
  
3.  Genişletme **bağlayıcı** düğümü.  
  
4.  Seçin **bildirim dosyası** özellik sayfası.  
  
5.  Değiştirme **oluşturmak bildirim** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateManifest%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)