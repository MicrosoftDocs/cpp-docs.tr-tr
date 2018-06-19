---
title: -MERGE (bölümleri Birleştir) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /merge
- VC.Project.VCLinkerTool.MergeSections
dev_langs:
- C++
helpviewer_keywords:
- sections, combining
- /MERGE linker option
- sections, naming
- sections
- -MERGE linker option
- MERGE linker option
ms.assetid: 10fb20c2-0b3f-4c8d-98a8-f69aedf03d52
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ece36de793b17b8cc064ec3837ea481a1ce870a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373481"
---
# <a name="merge-combine-sections"></a>/MERGE (Bölümleri Birleştir)
```  
/MERGE:from=to  
```  
  
## <a name="remarks"></a>Açıklamalar  
 / Merge seçeneği ilk bölümü birleştirir (*gelen*) ikinci bölümüyle (*için*), sonuçta ortaya çıkan bölüm adlandırma *için*. Örneğin, `/merge:.rdata=.text`.  
  
 İkinci bölüm mevcut değilse, bağlantı bölümü yeniden adlandırır *gelen* olarak *için*.  
  
 / Merge seçenek vxd oluşturmak ve derleyicinin ürettiği bölüm adları geçersiz kılma için yararlıdır.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **Gelişmiş** özellik sayfası.  
  
4.  Değiştirme **birleştirme bölümleri** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergeSections%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)