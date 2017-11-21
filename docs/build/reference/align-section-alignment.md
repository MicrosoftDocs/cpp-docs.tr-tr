---
title: "-ALIGN (bölüm hizalama) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.Alignment
- /align
dev_langs: C++
helpviewer_keywords:
- sections, specifying alignment
- ALIGN linker option
- /ALIGN linker option
- -ALIGN linker option
- section alignment
- sections
ms.assetid: f2f8ac24-e90e-4bea-8205-f2960a3b1740
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e620719d5a69c333a45664fba5967a740224d4d5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="align-section-alignment"></a>/ALIGN (Bölüm Hizalama)
```  
/ALIGN[:number]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 `number`  
 Hizalama değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 /ALIGN seçeneği programının doğrusal adres alanı içinde her bölüm hizalamasını belirtir. `number` Bağımsız değişkeni bayt ve iki gücünü olması gerekir. 4 K (4096) varsayılandır. Hizalama geçersiz bir görüntü üretiyor, bağlayıcı bir uyarı verir.  
  
 Bir aygıt sürücüsü gibi bir uygulama yazıyorsanız sürece hizalamasını değiştirme gerekmez.  
  
 Belirli bir bölümü için Hizala parametresiyle hizalamasını değiştirmek mümkündür [/SECTION](../../build/reference/section-specify-section-attributes.md) seçeneği.  
  
 Belirttiğiniz hizalama değeri en büyük bölüm hizalama küçük olamaz.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Seçenek içine türünü **ek seçenekler** kutusu.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)