---
title: "-GL (bütün Program iyileştirmesi) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /gl
- VC.Project.VCCLWCECompilerTool.WholeProgramOptimization
dev_langs: C++
helpviewer_keywords:
- /GL compiler option [C++]
- whole program optimizations and C++ compiler
- -GL compiler option [C++]
- GL compiler option [C++]
ms.assetid: 09d51e2d-9728-4bd0-b5dc-3b8284aca1d1
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 20436df9fd2f54193183505eb56da7c7b3371164
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="gl-whole-program-optimization"></a>/GL (Bütün Program İyileştirmesi)
Bütün program iyileştirmesi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/GL[-]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bütün program iyileştirmesi program tüm modüllerdeki bilgilerle iyileştirmeler gerçekleştirileceği derleyici sağlar. Bütün program iyileştirmesi iyileştirmeler üzerinde gerçekleştirilen bir modül (derlenecek) temelinde.  
  
 Bütün program iyileştirmesi varsayılan olarak kapalıdır ve açıkça etkinleştirilmesi gerekir. Ancak, aynı zamanda açıkça ile devre dışı bırakmak mümkündür **/GL-**.  
  
 Tüm modülleri hakkında daha fazla bilgi ile derleyici yapabilirsiniz:  
  
-   Yazmaçları kullanımını işlevi sınırlarında iyileştirin.  
  
-   Daha iyi iş yükleri ve depoları sayısında azaltma izin genel veri değişiklikleri izleme yapın.  
  
-   Daha iyi iş tarafından bir işaretçi değiştirilmiş öğelerini olası kümesini dereference, yükler ve depoları sayısı azaltma izleme yapın.  
  
-   Satır içi bile işlevi başka bir modülde tanımlandığında modülünde bir işlev.  
  
 .obj dosyaları üretilen ile **/GL** böyle bağlayıcı yardımcı programları için kullanılabilir olmayacak [EDITBIN](../../build/reference/editbin-reference.md) ve [DUMPBIN](../../build/reference/dumpbin-reference.md).  
  
 Programınızla birlikte derleme yaparsanız **/GL** ve [/c](../../build/reference/c-compile-without-linking.md), çıktı dosyasını oluşturmak için /LTCG bağlayıcı seçeneği kullanmanız gerekir.  
  
 [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) kullanılamaz **/GL**  
  
 Dosya biçimi ile üretilen **/GL** geçerli sürümde Visual C++'ın sonraki sürümleri tarafından okunabilir olmayabilir. İle üretilen .obj dosyaları oluşan bir .lib dosyası sevk etmesi değil **/GL** Visual C++'in tüm sürümleri .lib dosya kopyalarını dağıtmayı hazır olduğunuz sürece, şimdi ve gelecekte kullanmak için kullanıcılarınızın bekler.  
  
 .obj dosyaları üretilen ile **/GL** ve .lib dosyası üretilen aynı makinede bağlanır sürece .lib dosyasını oluşturmak için önceden derlenmiş üstbilgi dosyaları kullanılmamalıdır **/GL** .obj dosya. .Obj dosyanın önceden derlenmiş üst bilgi dosya bilgileri bağlantı zaman gerekecektir.  
  
 En iyi duruma getirme ile kullanılabilir ve bütün program iyileştirmesi sınırlamaları hakkında daha fazla bilgi için bkz: [/LTCG](../../build/reference/ltcg-link-time-code-generation.md).  **/GL** da yapar profil destekli iyileştirme kullanılabilir; /LTCG bakın.  Profil temelli iyileştirmeler ve, profil temelli iyileştirmeler sıralama işlevi isteyip istemediğinizi için derlerken ile derlemeniz gerekir [/Gy](../../build/reference/gy-enable-function-level-linking.md) veya /Gy gelir derleyici seçeneği.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Bkz: [/LTCG (bağlama zamanı kodu oluşturma)](../../build/reference/ltcg-link-time-code-generation.md) nasıl belirtileceği hakkında bilgi için **/GL** geliştirme ortamında.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)