---
title: "-NXCOMPAT (Veri Yürütme Engellemesi uyumlu) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /NXCOMPAT
dev_langs: C++
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
ms.assetid: 5858e7ff-24d3-4ac3-9046-af2c9e220d9b
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d97b1b84ef6894e4ec161dbcecef47f6b676af23
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT (Veri Yürütme Önlemesi ile Uyumlu)
Bir yürütülebilir dosya Windows Veri Yürütme Engellemesi özelliği ile uyumlu olacak şekilde test edilmiştir gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/NXCOMPAT[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, **/NXCOMPAT** açıktır.  
  
 **/NXCOMPAT:No** açıkça Veri Yürütme Engellemesi uyumlu olarak yürütülebilir bir dosya belirtmek için kullanılır.  
  
 Veri Yürütme Engellemesi hakkında daha fazla bilgi için bu makalelere bakın:  
  
-   [Veri Yürütme Engellemesi (DEP) özelliğinin ayrıntılı bir açıklaması](http://go.microsoft.com/fwlink/?LinkID=157771) Microsoft Help ve Destek Web sitesinde  
  
-   [Veri Yürütme Engellemesi](http://go.microsoft.com/fwlink/?LinkID=157770) MSDN Web sitesinde  
  
-   [Veri Yürütme Engellemesi (Windows Embedded)](http://go.microsoft.com/fwlink/?LinkID=157768) MSDN Web sitesinde  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio'da bu bağlayıcı seçeneği ayarlamak için  
  
1.  Projeyi açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Seçeneğinde yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)