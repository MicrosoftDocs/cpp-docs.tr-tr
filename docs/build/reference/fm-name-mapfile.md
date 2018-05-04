---
title: -Fm (adı eşlem) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /fm
dev_langs:
- C++
helpviewer_keywords:
- -Fm compiler option [C++]
- mapfiles [C++], creating linker
- files [C++], creating map
- Fm compiler option [C++]
- /Fm compiler option [C++]
ms.assetid: 8154448a-93a7-4546-8e4c-5c44d0aff45d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94a499b943fcd3213aa76876c65c3aac2dd79060
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="fm-name-mapfile"></a>/Fm (Eşlem Dosyasını Adlandır)
Karşılık gelen .exe dosyası ya da DLL göründükleri sırada kesimlerin listesini içeren bir eşlem dosyası üretmek için bağlayıcı söyler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Fmpathname  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, mapfile karşılık gelen C veya C++ kaynak dosyayla temel adı verilen bir. Uzantı EŞLEYİN.  
  
 Belirtme **/Fm** olarak belirttiyseniz aynı etkiye sahip [/Map (eşlem dosyası oluştur)](../../build/reference/map-generate-mapfile.md) bağlayıcı seçeneği.  
  
 Belirtirseniz [/c (derleme olmadan bağlama)](../../build/reference/c-compile-without-linking.md) bağlama, gizlemek için **/Fm** hiçbir etkisi olmaz.  
  
 Derleyici değişken adları önde gelen bir alt çizgi eklediğinden bir eşlem genel simgeler genellikle bir veya daha fazla başında alt çizgi sahiptir. Mapfile görünen birçok genel semboller derleyicisi ve standart kitaplığı tarafından dahili olarak kullanılır.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıktı dosyası (/ F) seçenekleri](../../build/reference/output-file-f-options.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [Yol Adını Belirtme](../../build/reference/specifying-the-pathname.md)