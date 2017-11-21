---
title: "-STUB (MS-DOS saplama dosyası adı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /stub
- VC.Project.VCLinkerTool.DosStub
dev_langs: C++
helpviewer_keywords:
- Win32 [C++], attaching MS-DOS stub program
- STUB linker option
- MS-DOS stub file name linker option
- /STUB linker option
- Windows API [C++], attaching MS-DOS stub program
- -STUB linker option
ms.assetid: 65221ffe-4f9a-4a14-ac69-3cfb79b40b5f
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 75d5d3d1eb362c893f3594e5d770111ddded01b9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="stub-ms-dos-stub-file-name"></a>/STUB (MS-DOS Saplama Dosyası Adı)
```  
/STUB:filename  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 *Dosya adı*  
 MS-DOS uygulama.  
  
## <a name="remarks"></a>Açıklamalar  
 / Stub seçeneği bir Win32 programı MS-DOS saplama programını ekler.  
  
 Dosya MS-DOS yürütülürse saplama programını çağrılır. Genellikle, uygun bir mesaj görüntüler; Ancak, herhangi bir geçerli MS-DOS uygulama saplama programını olabilir.  
  
 Belirtin bir *filename* sonra iki nokta (:) komut satırında saplama programını için. Bağlayıcı denetimleri *filename* ve dosya yürütülebilir bir dosya değil, bir hata iletisi verir. Program bir .exe dosyası olmalıdır; .com dosyası için bir saplama program geçersiz.  
  
 Bu seçenek kullanılmazsa, bağlayıcı aşağıdaki iletiyi sorunları varsayılan saplama programını ekler:  
  
```  
This program cannot be run in MS-DOS mode.  
```  
  
 Bir sanal aygıt sürücüsü oluştururken *filename* (WINNT içinde tanımlanmıştır. IMAGE_DOS_HEADER yapısı içeren bir dosya adı belirtin olanak tanır. H) varsayılan üstbilgi yerine VXD kullanılacak.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Seçenek içine türünü **ek seçenekler** kutusu.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)