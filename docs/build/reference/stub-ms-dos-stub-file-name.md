---
title: -STUB (MS-DOS saplama dosyası adı) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /stub
- VC.Project.VCLinkerTool.DosStub
dev_langs:
- C++
helpviewer_keywords:
- Win32 [C++], attaching MS-DOS stub program
- STUB linker option
- MS-DOS stub file name linker option
- /STUB linker option
- Windows API [C++], attaching MS-DOS stub program
- -STUB linker option
ms.assetid: 65221ffe-4f9a-4a14-ac69-3cfb79b40b5f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4302040f7d18dcffc07ddd054c34b62c22e400d2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)