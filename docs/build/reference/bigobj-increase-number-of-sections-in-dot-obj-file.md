---
title: "-bigobj (bölümlerde artış sayısı. Obj dosyası) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /bigobj
dev_langs: C++
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 384ec0de9e5cb1b3172b980bf7f412abe759ff91
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj (.Obj Dosyasında Bölüm Sayısını Arttırma)
**/ bigobj** bir nesne dosyası içerebilir bölümleri sayısını artırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/bigobj  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bir nesne dosyası en çok 65.536 barındırabilir (2 ^ 16) adreslenebilir bölümler. Bu, hedef platformu olsun belirtilen durumdur. **/ bigobj** 4,294,967,296 için bu adresi kapasitesini artırır (2 ^ 32).  
  
 Çoğu modülleri hiçbir zaman birden fazla 65.536 bölümleri içeren bir .obj dosyası oluşturur. Ancak, oluşturulan kodda makine veya Şablon Kütüphanesi kullanımına ağırlık yapan kod daha fazla bölüm tutabilir .obj dosyaları gerektirebilir. **/ bigobj** makine oluşturulan XAML kod çok sayıda üst bilgiler içerdiğinden Windows mağazası projeleri üzerinde varsayılan olarak etkindir. Bir Windows mağazası uygulama projesi bu seçeneği devre dışı bırakırsanız derleyici hatası C1128 karşılaşma olasılığı yüksektir.  
  
 Visual C++ 2005 önce sevk linkers ile üretilen .obj dosyaları okuyamıyor **/bigobj**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)