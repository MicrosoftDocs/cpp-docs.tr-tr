---
title: "-constexpr (Denetim constexpr değerlendirme) | Microsoft Docs"
ms.custom: 
ms.date: 08/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /constexpr
- -constexpr
dev_langs: C++
helpviewer_keywords:
- /constexpr control constexpr evaluation [C++]
- -constexpr control constexpr evaluation [C++]
- constexpr control constexpr evaluation [C++]
ms.assetid: 76d56784-f5ad-401d-841d-09d1059e8b8c
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 38bdf6bb5dbaaa802d669b81a2504a206642204e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="constexpr-control-constexpr-evaluation"></a>/constexpr (Denetim constexpr değerlendirme)  
  
Kullanım **/constexpr** denetim parametrelerini derleyici seçenekleri `constexpr` derleme zamanında değerlendirme.  
  
## <a name="syntax"></a>Sözdizimi  
  
> /constexpr:Depth*N*  
> /constexpr:backtrace*N*  
> /constexpr:Steps*N*  
  
## <a name="arguments"></a>Arguments  
  
**Derinlik***N*  
Özyinelemeli derinliğini sınırlamak `constexpr` işlev çağrısı için *N* düzeyleri. Varsayılan değer 512'dir.  
  
**backtrace***N*  
En fazla Göster *N* `constexpr` değerlendirmeleri tanılama. Varsayılan değer 10'dur.  
  
**adımları***N*  
Sonlandırma `constexpr` değerlendirmesinden sonra *N* adımları. Varsayılan değer 100. 000 ' dir.  
  
## <a name="remarks"></a>Açıklamalar  
  
**/Constexpr** derleyici seçeneklerini denetleme derleme zamanı değerlendirmesi `constexpr` ifadeler. Değerlendirme adımlar, özyineleme düzeyleri ve backtrace derinliği üzerinde çok fazla zaman harcama derleyici önlemek için denetlenir `constexpr` değerlendirme. Daha fazla bilgi için `constexpr` language öğesi bkz [constexpr (C++)](../../cpp/constexpr-cpp.md).  

**/Constexpr** seçeneklerdir Visual Studio 2015'te başlayarak bulunabilir.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1. Projenizin açmak **özellik sayfaları** iletişim kutusu.   
  
2. Altında **yapılandırma özellikleri**, genişletin **C/C++** klasör ve **komut satırı** özellik sayfası.  
  
3. Herhangi bir girin **/constexpr** derleyici seçenekleri **ek seçenekler** kutusu. Seçin **Tamam** veya **Uygula** yaptığınız değişiklikleri kaydetmek için.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
  
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
[Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)