---
title: -Gm (en az yeniden etkinleştirme) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.MinimalRebuild
- /Gm
- /FD
- VC.Project.VCCLWCECompilerTool.MinimalRebuild
dev_langs:
- C++
helpviewer_keywords:
- /Gm compiler option [C++]
- minimal rebuild
- enable minimal rebuild compiler option [C++]
- Gm compiler option [C++]
- -Gm compiler option [C++]
ms.assetid: d8869ce0-d2ea-40eb-8dae-6d2cdb61dd59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e0b83c34b0ff8cacbca9d21a40c6c9572f516d1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374576"
---
# <a name="gm-enable-minimal-rebuild"></a>/Gm (En Az Yeniden Derlemeyi Etkinleştir)
Değiştirilen C++ sınıf tanımları (Üstbilgi (.h) dosyalarında depolanır) dahil C++ kaynak dosyaları derlenmesi gerekip gerekmediğini belirler en az yeniden derleme sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Gm  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Derleyici sınıf tanımları ve kaynak dosyaları arasındaki bağımlılık bilgi ilk derleme sırasında projenin .idb dosyasında depolar. (Bağımlılık bilgileri hangi kaynak dosyasının hangi sınıf tanımı üzerinde bağımlı olduğunu bildirir ve hangi .h tanım dosyası bulunur.) Sonraki derlerken değiştirilmiş .h dosyası içerse bile kaynak dosyası derlenmesi gerekli olup olmadığını belirlemek için .idb dosyasında depolanan bilgileri kullanın.  
  
> [!NOTE]
>  En az yeniden derleme dayanır sınıfında arasında değiştirme değil tanımları dosyaları içerir. Sınıf tanımları (olmamalıdır belirli bir sınıfın yalnızca tek bir tanım) bir proje için genel olmalıdır bağımlılık bilgileri .idb dosyada için tüm proje oluşturulduğundan. Projenizde bir sınıf için birden fazla tanımına sahip en az yeniden derlemeyi devre dışı bırakın.  
  
 Incremental bağlayıcı kullanılarak .obj dosyaları dahil Windows meta verileri desteklemediğinden [/ZW (Windows çalışma zamanı derlemesi)](../../build/reference/zw-windows-runtime-compilation.md) seçeneği **/GM derlemeyi** seçeneği ile uyumlu  **/ZW**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **kod oluşturma** özellik sayfası.  
  
4.  Değiştirme **en az yeniden etkinleştirme** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.MinimalRebuild%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)