---
title: "-WX (Bağlayıcı uyarılarını hata olarak) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /WX
dev_langs: C++
helpviewer_keywords:
- /WX linker option
- -WX linker option
- WX linker option
ms.assetid: e4ba97c7-93f7-43ae-a4bb-d866790926c9
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a4624436ac3109286749d654fb90d4318a837bc0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="wx-treat-linker-warnings-as-errors"></a>/WX (Bağlayıcı Uyarılarını Hata Olarak İşle)
```  
/WX[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 /WX bağlayıcı bir uyarı oluşturursa oluşturulacak hiçbir çıktı dosyası neden olur.  
  
 Bu benzer **/WX** derleyici için (bkz [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, wln, /wd, / biz, /wo, /Wv, /WX (uyarı düzeyi)](../../build/reference/compiler-option-warning-level.md) daha fazla bilgi için). Ancak, belirtme **/WX** derleme, göstermez için **/WX** açıkça belirtmeniz gerekir; ayrıca bağlantı aşaması için uygulanmaz **/WX** her aracı için.  
  
 Varsayılan olarak, **/WX** etkili değildir. Bağlayıcı uyarılarını hata olarak değerlendirmek için belirtmek **/WX**. **/WX:No** değil belirtme aynı **/WX**.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Seçenek içine türünü **ek seçenekler** kutusu.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)