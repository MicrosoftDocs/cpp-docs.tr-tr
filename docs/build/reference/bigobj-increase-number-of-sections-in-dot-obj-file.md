---
title: -bigobj (bölümlerde artış sayısı. Obj dosyası) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /bigobj
dev_langs:
- C++
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df8bc379462bf5937f463b464ea2972472c49808
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369961"
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj (.Obj Dosyasında Bölüm Sayısını Arttırma)
**/ bigobj** bir nesne dosyası içerebilir bölümleri sayısını artırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/bigobj  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bir nesne dosyası en çok 65.536 barındırabilir (2 ^ 16) adreslenebilir bölümler. Bu, hedef platformu olsun belirtilen durumdur. **/ bigobj** 4,294,967,296 için bu adresi kapasitesini artırır (2 ^ 32).  
  
 Çoğu modülleri hiçbir zaman birden fazla 65.536 bölümleri içeren bir .obj dosyası oluşturur. Ancak, oluşturulan kodda makine veya Şablon Kütüphanesi kullanımına ağırlık yapan kod daha fazla bölüm tutabilir .obj dosyaları gerektirebilir. **/ bigobj** üstbilgileri çok sayıda makine oluşturulan XAML kod içerdiği için evrensel Windows Platformu (UWP) projelerde varsayılan olarak etkindir. Bir UWP uygulaması projesi bu seçeneği devre dışı bırakırsanız derleyici hatası C1128 karşılaşma olasılığı yüksektir.  
  
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