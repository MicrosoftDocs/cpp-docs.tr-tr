---
title: "-IMPLIB (içeri aktarma kitaplığını Adlandır) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /implib
- VC.Project.VCLinkerTool.ImportLIbrary
dev_langs: C++
helpviewer_keywords:
- IMPLIB linker option
- /IMPLIB linker option
- -IMPLIB linker option
- import libraries, overriding default name
ms.assetid: fe8f71ab-7055-41b5-8ef8-2b97cfa4a432
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 523fc171aa8df3d0b4c6e09909db7c2c1dc0b833
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="implib-name-import-library"></a>/IMPLIB (İçeri Aktarma Kitaplığını Adlandır)
  
> / IMPLIB:*dosya adı*  
  
## <a name="parameters"></a>Parametreler  
  
*Dosya adı*  
Bir kullanıcı tarafından belirtilen adı içeri aktarma kitaplığı. Varsayılan adı değiştirir.  
  
## <a name="remarks"></a>Açıklamalar  
  
/IMPLIB seçenek bağlantı dışarı aktarmaları içeren bir program oluşturduğunda oluşturan içeri aktarma kitaplığı için varsayılan adı geçersiz kılar. Varsayılan adı ana çıkış dosyasını ve uzantı temel adından oluşturulmuş. lib. Aşağıdakilerden birini veya birkaçını belirtilmezse, bir program dışarı içerir:  
  
-   [__Declspec(dllexport)](../../cpp/dllexport-dllimport.md) kaynak kodundaki anahtar sözcüğü  
  
-   [Dışarı aktarma](../../build/reference/exports.md) .def dosyası deyimi  
  
-   Bir [/dışarı aktarma](../../build/reference/export-exports-a-function.md) bağlantı komutunda belirtimi  
  
 İçeri aktarma kitaplığı değil oluşturulduğunda bağlantı /IMPLIB yok sayar. Hiçbir dışarı aktarma belirttiyseniz, bağlantıyı içeri aktarma kitaplığı oluşturmaz. Dışa aktarma dosyası derleme kullanılırsa, bağlantı içeri aktarma kitaplığı zaten var ve bir oluşturmaz varsayar. İçeri aktarma kitaplıkları ve dışarı aktarma dosyaları hakkında daha fazla bilgi için bkz: [LIB başvurusu](../../build/reference/lib-reference.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **Gelişmiş** özellik sayfası.  
  
4.  Değiştirme **içeri aktarma kitaplığını** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ImportLibrary%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)