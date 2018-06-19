---
title: -Gw (genel verileri En İyileştir) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Gw
dev_langs:
- C++
helpviewer_keywords:
- /Gw compiler option [C++]
- -Gw compiler option [C++]
ms.assetid: 6f90f4e9-5eb8-4c47-886e-631278a5a4a9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 173b9499477ee02cbb1f052d3d85445a9ffb7732
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376445"
---
# <a name="gw-optimize-global-data"></a>/Gw (Genel Verileri En İyileştir)
En iyi duruma getirme için comdat'ı bölümleri genel veri paketi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Gw[-]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/Gw** seçeneği comdat'ı bölümleri tek tek Paket genel veri derleyicinin neden olur. Varsayılan olarak, **/Gw** kapalıdır ve açıkça etkinleştirilmesi gerekir. Açıkça devre dışı bırakmak için **/Gw-**. Her ikisi de **/Gw** ve [/GL](../../build/reference/gl-whole-program-optimization.md) olan etkinse, bağlayıcı bütün program iyileştirmesi başvurulmayan genel veri dışlamak için ya da birleştirmek için birden çok nesne dosyalardaki comdat'ı bölümleri Karşılaştırılacak kullanır aynı salt okunur genel veriler. Bu, sonuçta elde edilen ikili yürütülebilir boyutunu önemli ölçüde azaltabilir.  
  
 Derleme ve ayrı bağlantı kullanabileceğiniz [/OPT:REF](../../build/reference/opt-optimizations.md) bağlayıcı seçeneği ile nesne dosyaları başvurulmayan genel verilerde derlenmiş yürütülebilir dışında bırakın **/Gw** seçeneği.  
  
 Aynı zamanda [/OPT:ICF](../../build/reference/opt-optimizations.md) ve [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) bağlayıcı seçenekleri ile birden çok nesne dosyaları arasında özdeş herhangi salt okunur genel verileri derlenmiş yürütülebilir birleştirin **/Gw** seçeneği.  
  
 Daha fazla bilgi için bkz: [/Gw derleyici anahtar Tanıtımı](http://blogs.msdn.com/b/vcblog/archive/2013/09/11/introducing-gw-compiler-switch.aspx) Visual C++ ekip blogunda.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **C/C++** klasör.  
  
3.  Seçin **komut satırı** özellik sayfası.  
  
4.  Değiştirme **ek seçenekler** eklenecek özellik **/Gw** ve ardından **Tamam**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)