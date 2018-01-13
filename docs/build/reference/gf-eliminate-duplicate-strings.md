---
title: -GF (yinelenen dizeleri ele) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.StringPooling
- VC.Project.VCCLWCECompilerTool.StringPooling
- /gf
dev_langs: C++
helpviewer_keywords:
- duplicate strings
- Eliminate Duplicate Strings compiler option [C++]
- pooling strings compiler option [C++]
- -GF compiler option [C++]
- /GF compiler option [C++]
- GF compiler option [C++]
- strings [C++], pooling
ms.assetid: bb7b5d1c-8e1f-453b-9298-8fcebf37d16c
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d69e892fb9487b66da4dfa2a801bab302e962af7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="gf-eliminate-duplicate-strings"></a>/GF (Yinelenen Dizeleri Ele)
Yürütme sırasında program görüntü ve bellek aynı dize tek bir kopyasını oluşturmak derleyici sağlar. Adlı bir iyileştirme budur *dize havuzu* küçük programlar oluşturabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/GF  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanırsanız **/GF**, işletim sisteminin bellek dize bölümünü değiştirme değil ve görüntü dosyasından geri dizelerin okuyabilirsiniz.  
  
 **/GF** dizeleri salt okunur olarak havuza ekler. Altında dizeleri değiştirmeye çalışırsanız, **/GF**, bir uygulama hatası oluşur.  
  
 Dize havuzu ne birden çok arabellekleri için birden çok işaretçiler olarak tek bir arabelleğe birden çok işaretçileri olması düşünülmemiştir sağlar. Aşağıdaki kodda, `s` ve `t` aynı dizesiyle başlatılır. Dize havuzu bunları aynı belleği işaret edecek şekilde neden olur:  
  
```  
char *s = "This is a character buffer";  
char *t = "This is a character buffer";  
```  
  
> [!NOTE]
>  [/Zı](../../build/reference/z7-zi-zi-debug-information-format.md) Düzenle ve devam et, için kullanılan seçeneği, otomatik olarak ayarlar **/GF** seçeneği.  
  
> [!NOTE]
>  **/GF** derleyici seçeneği her benzersiz bir dize için adreslenebilir bir bölüm oluşturur. Ve varsayılan olarak, bir nesne dosyası en çok 65.536 adreslenebilir bölümleri içerebilir. Programınızı birden fazla 65.536 dizelerini içeriyorsa, [/bigobj](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md) daha fazla bölüm oluşturmak için derleyici seçeneği.  
  
 **/GF** içinde ne zaman efekt olan [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) veya **O2** kullanılır.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **kod oluşturma** özellik sayfası.  
  
4.  Değiştirme **etkinleştirmek dize havuzu** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)