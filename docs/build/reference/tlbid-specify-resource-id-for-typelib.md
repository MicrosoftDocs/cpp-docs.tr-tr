---
title: "-TLBID (TypeLib için kaynak Kimliğini belirt) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /tlbid
- VC.Project.VCLinkerTool.TypeLibraryResourceID
dev_langs:
- C++
helpviewer_keywords:
- tlb files, specifying resource ID
- -TLBID linker option
- .tlb files, specifying resource ID
- /TLBID linker option
- TLBID linker option
- type libraries, specifying resource ID
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a552edab9f2de646de3b869bf84467924b5db348
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tlbid-specify-resource-id-for-typelib"></a>/TLBID (TypeLib için Kaynak Kimliğini Belirt)
```  
/TLBID:id  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 `id`  
 Bir kullanıcı tarafından belirtilen değeri bir bağlayıcı oluşturulan tür kitaplığı. Bu, varsayılan kaynak kimliği 1 geçersiz kılar.  
  
## <a name="remarks"></a>Açıklamalar  
 Öznitelikler kullanan bir programı derlerken bağlayıcı bir tür kitaplığı oluşturun. Bağlayıcı için tür kitaplığı kaynak kimliği 1 atar.  
  
 Bu kaynak kimliği mevcut kaynaklarınızı biriyle çakışırsa, başka bir kimlik ile /TLBID belirtebilirsiniz. İçin geçirebilir değerleri aralığı `id` 1-65535'tir.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **katıştırılmış IDL** özellik sayfası.  
  
4.  Değiştirme **TypeLib kaynak kimliği** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)