---
title: "-Zp (yapı üyesi hizalama) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
dev_langs: C++
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d387e0ab020e96afb3e2975b5c8686b668cbc10
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="zp-struct-member-alignment"></a>/Zp (Yapı Üyesi Hizalama)
Bir yapı üyeleri belleğe nasıl paketlenmiş denetler ve tüm yapılar aynı sevk modülde belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Zp[1|2|4|8|16]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçeneği belirttiğinizde, her yapısı öğesinden sonra ilk üye türü ya da bir boyutu üzerinde depolanır veya `n`-bayt sınırları (burada `n` 1, 2, 4, 8 ya da 16), hangisi daha küçüktür.  
  
 Kullanılabilir değerler aşağıdaki tabloda açıklanmıştır.  
  
 1.  
 1-bayt sınırları yapıları paketleri. Aynı **/Zp**.  
  
 2  
 2-bayt sınırları yapıları paketleri.  
  
 4  
 4-bayt sınırları yapıları paketleri.  
  
 8  
 Paketleri yapıları 8 baytlık sınırlarda (varsayılan).  
  
 16  
 Yapıları 16 bayt sınırları paketleri.  
  
 Belirli bir uyum gereksinimlerin sürece bu seçeneği kullanmamanız gerekir.  
  
 Aynı zamanda [paketi](../../preprocessor/pack.md) denetim yapısı paket için. Hizalama hakkında daha fazla bilgi için bkz.  
  
-   [Hizalama](../../cpp/align-cpp.md)  
  
-   [__alignof İşleci](../../cpp/alignof-operator.md)  
  
-   [__unaligned](../../cpp/unaligned.md)  
  
-   [Yapı hizalama örnekleri](../../build/examples-of-structure-alignment.md) (x64 belirli)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **kod oluşturma** özellik sayfası.  
  
4.  Değiştirme **yapı üyesi hizalama** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)