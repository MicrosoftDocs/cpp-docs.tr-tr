---
title: "-Yl (hata ayıklama kitaplığı için PCH Başvurusu Ekle) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /yi
dev_langs: C++
helpviewer_keywords:
- -Yl compiler option [C++]
- Yl compiler option [C++]
- /Yl compiler option [C++]
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 271681849d78eb8a6a4032bcbafbcc81b96c9f9b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="yl-inject-pch-reference-for-debug-library"></a>/Yl (Hata Ayıklama Kitaplığı için PCH Başvurusu Ekle)
Önceden derlenmiş üst bilgileri kullanan bir hata ayıklama kitaplığı oluşturma ve derleme başarısız olursa kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Ylsymbol  
```  
  
```  
/Yl-  
```  
  
## <a name="arguments"></a>Arguments  
 `symbol`  
 Nesne modülde depolanması için rasgele bir simge.  
  
 \-  
 Bir açıkça devre dışı bırakan eksi (-) **/Yl** derleyici seçeneği.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, derleyici kullanır **/Yl** seçeneği (belirtmeden bir *simgesi*). **/Yl** türleri hakkında tam bilgi almak hata ayıklayıcı seçeneğini etkinleştirir. **/Yl-** varsayılan davranışı devre dışı bırakır.  
  
 Derleme zaman sahip bir modül **/Yc** ve **/Yl**`symbol`, derleyici __ benzeyen bir simge oluşturur@_PchSym\_@00@...@`symbol`, burada üç nokta (...) bir bağlayıcı oluşturulan karakter dizesini temsil eder ve nesne modülünde depolar. Bu önceden derlenmiş üst bilgi ile derleme herhangi bir kaynak dosyayı nesne modülü ve kitaplık hata ayıklama bilgilerini içerecek şekilde bağlayıcı neden olan belirtilen simgeyi gösterir.  
  
 Bu seçeneği kullanarak LNK1211 oluşturabilir. Belirttiğinizde [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md) ve [/Z7, / zi, /zı (hata ayıklama bilgileri biçimi)](../../build/reference/z7-zi-zi-debug-information-format.md) seçenekleri, derleyici, hata ayıklama bilgilerini içeren bir önceden derlenmiş üst bilgi dosyası oluşturur. Bir kitaplığı, bir nesne modülü ve kaynak kodu derleme için kitaplık herhangi önceden derlenmiş üst bilgi dosyası tanımlar işlevleri başvurmuyor kullanım önceden derlenmiş üst bilgi depolamak bir hata oluşabilir.  
  
 Sorunu çözmek için belirtmek **/Yl**`symbol`, burada `symbol` hiçbir işlev tanımları içermeyen bir önceden derlenmiş üst bilgi dosyası oluşturduğunuzda Kitaplığı'nda, rasgele bir simge adıdır. Bu seçenek önceden derlenmiş üst bilgi dosyasında hata ayıklama bilgilerini depolamak için derleyici yönlendirir.  
  
 Önceden derlenmiş üst bilgileri hakkında daha fazla bilgi için bkz:  
  
-   [/Y (önceden derlenmiş başlıklar)](../../build/reference/y-precompiled-headers.md)  
  
-   [Önceden derlenmiş üst bilgi dosyaları oluşturma](../../build/reference/creating-precompiled-header-files.md)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)