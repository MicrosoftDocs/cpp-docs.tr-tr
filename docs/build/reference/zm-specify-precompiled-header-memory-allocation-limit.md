---
title: "-Zm (önceden derlenmiş üst bilgi bellek ayırma sınırını belirt) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /zm
dev_langs: C++
helpviewer_keywords:
- PCH files, memory allocation limit
- Zm compiler option [C++]
- /Zm compiler option [C++]
- precompiled header files, memory allocation limit
- Specify Precompiled Header Memory Allocation Limit compiler option
- cl.exe compiler, memory allocation limit
- .pch files, memory allocation limit
- memory allocation, Memory Allocation Limit compiler option
- -Zm compiler option [C++]
ms.assetid: 94c77d5e-6672-46a7-92e0-3f69e277727d
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 476e64d052912e9937d054e52c66e1397b8da66f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="zm-specify-precompiled-header-memory-allocation-limit"></a>/Zm (Önceden Derlenmiş Üst Bilgi Bellek Ayırma Sınırını Belirt)
Önceden derlenmiş üstbilgileri oluşturmak için derleyicinin ayırdığı bellek miktarını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Zmfactor  
```  
  
## <a name="arguments"></a>Arguments  
 `factor`  
 Önceden derlenmiş üstbilgileri oluşturmak için derleyicinin kullandığı bellek miktarını belirleyen bir ölçekleme faktörü.  
  
 `factor` Değişkendir derleyici tarafından tanımlanan iş arabelleğin varsayılan boyutun yüzdesi. Varsayılan değer olan `factor` 100 (yüzde), ancak daha büyük ya da daha küçük miktarda belirtebilirsiniz.  
  
## <a name="remarks"></a>Açıklamalar  
 Visual C++'ın önceki sürümlerinde, derleyici çeşitli ayrı yığınlar kullanıyordu ve her birinin sınırı sonsuzdu. Şu anda ise, derleyici yığınları toplam yığın boyutu sınırına doğru gerekli oldukça dinamik olarak yükseltir ve yalnızca önceden işlenmiş üstbilgileri oluşturmak için sabit boyutlu bir arabellek gerektirir. Sonuç olarak, **/Zm** derleyici seçeneği nadiren gereklidir.  
  
 Derleyici yığın alan tükendiğinde ve yayar [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) kullandığınızda hata iletisi **/Zm** derleyici seçeneği, çok fazla bellek ayrılmış. Kaldırmayı düşünün **/Zm** seçeneği. Derleyici yayar, [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) hata iletisi, bir eşlik eden [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) iletiyi belirtir `factor` kullanarak yeniden derleyin, kullanılacak değişkeni **/Zm** derleyici seçeneği.  
  
 Aşağıdaki tabloda nasıl `factor` bağımsız değişkeni etkiliyorsa bellek ayırma sınırını varsayılan önceden derlenmiş üst bilgi arabellek boyutu 75 MB olduğunu varsayalım.  
  
|Değeri`factor`|Bellek ayırma sınırı|  
|-----------------------|-----------------------------|  
|10|7.5 MB|  
|100|75 MB|  
|200|150 MB|  
|1000|750 MB|  
|2000|1500 MB|  
  
## <a name="other-ways-to-set-the-memory-allocation-limit"></a>Bellek Ayırma Sınırını Ayırmanın Diğer Yolları  
  
#### <a name="to-set-the-zm-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında /Zm derleyici seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Gezinti bölmesinde seçin **yapılandırma özellikleri**, **C/C++**, **komut satırı**.  
  
3.  Girin **/Zm** derleyici seçeneği **ek seçenekler** kutusu.  
  
#### <a name="to-set-the-zm-compiler-option-programmatically"></a>/Zm derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)