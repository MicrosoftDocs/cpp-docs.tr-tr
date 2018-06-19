---
title: -LIBPATH (ek Libpath) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /libpath
- VC.Project.VCLinkerTool.AdditionalLibraryDirectories
dev_langs:
- C++
helpviewer_keywords:
- LIBPATH linker option
- /LIBPATH linker option
- Additional Libpath linker option
- environment library path override
- -LIBPATH linker option
- library path linker option
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ccb94ad20735e81fc3d83f757cc0265cdc32169
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372886"
---
# <a name="libpath-additional-libpath"></a>/LIBPATH (Ek Libpath)
```  
/LIBPATH:dir  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 `dir`  
 Bir yol belirtir LIB ortam seçeneğinde belirtilen yol arar önce bağlayıcı arar.  
  
## <a name="remarks"></a>Açıklamalar  
 Ortam Kitaplığı yol geçersiz kılmak için / Libpath seçeneğini kullanın. Bağlayıcı önce bu seçeneği tarafından belirtilen yol içinde arama ve LIB ortam değişkeninde belirtilen yolda arayın. Girdiğiniz her/Libpath seçeneği yalnızca bir dizine belirtebilirsiniz. Birden fazla dizine belirtmek istiyorsanız, birden çok/Libpath seçeneği belirtmeniz gerekir. Bağlayıcı, belirtilen dizinlerin sonra sırayla arar.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **genel** özellik sayfası.  
  
4.  Değiştirme **ek kitaplık dizinleri** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)