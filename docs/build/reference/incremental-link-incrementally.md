---
title: "-ARTIMLI (artımlı Bağla) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /incremental
- VC.Project.VCLinkerTool.LinkIncremental
dev_langs:
- C++
helpviewer_keywords:
- /INCREMENTAL linker option
- -INCREMENTAL linker option
- INCREMENTAL linker option
- link incrementally option
- LINK tool [C++], options for full linking
- incremental linking
ms.assetid: 135656ff-94fa-4ad4-a613-22e1a2a5d16b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7e4104fec3d6678ced04a0b070d118b5539b4140
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="incremental-link-incrementally"></a>/INCREMENTAL (Artımlı Bağla)
```  
/INCREMENTAL[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bağlayıcının artımlı bağlamayı nasıl işlediğini denetler.  
  
 Varsayılan olarak bağlayıcı artımlı modda çalışır. Varsayılan bir artırımlı bağlantıyı geçersiz kılmak için /INCREMENTAL:NO belirtin.  
  
 Artımlı olarak bağlı bir program artımlı olmayan bağlı bir program işlevsel olarak eşdeğerdir. Ancak, sonraki artımlı bağlantılar, artımlı olarak bağlanmış yürütülebilir, statik kitaplık ya da dinamik bağlantı kitaplığı dosyası için hazırlanmış nedeni:  
  
-   Kod ve veri doldurma nedeniyle artımlı olmayan bağlı bir program büyük. Doldurma dosyasını yeniden olmadan işlev ve veri boyutunu artırmak bağlayıcı sağlar.  
  
-   İşlevlerin yeni adreslerine tanıtılması için atlama dönüştürücüler içerebilir.  
  
    > [!NOTE]
    >  Son sürümde yapınızın doldurma veya dönüştürücüler içermediğinden emin olmak için program artımlı olmayan bağlayın.  
  
 Varsayılandan bağımsız ve artırımlı olarak bağlamak için /INCREMENTAL belirtin. Bu seçenek belirlendiğinde, bağlayıcı artımlı olarak bağlayamazsınız, bir uyarı verir ve program artımlı olmayan bağlar. Belirli seçenekler ve durumlar /INCREMENTAL öğesini geçersiz kılar.  
  
 Çoğu program kademeli olarak bağlanabilir. Ancak bası değişiklikler çok büyük değildir ve bazı seçenekler artımlı bağlama ile uyumlu değildir. LINK, aşağıdaki seçeneklerden herhangi biri belirtilirse tam bağlantı gerçekleştirir:  
  
-   Artımlı Bağlantı seçili değil (/INCREMENTAL:NO)  
  
-   /OPT:REF seçili  
  
-   /OPT:ICF seçili  
  
-   /OPT:LBR seçili  
  
-   /ORDER seçili  
  
 / INCREMENTAL zaman kapsanan [/DEBUG](../../build/reference/debug-generate-debug-info.md) belirtilir.  
  
 Ayrıca, aşağıdaki durumlardan herhangi biri söz konusu olursa LINK tam bağlantı gerçekleştirir:  
  
-   Artımlı durum (.ilk) dosyası eksik. (LINK ileride artımlı bağlamaya hazırlık olarak yeni bir .ilk dosyası oluşturur.)  
  
-   .ilk dosyası için hiçbir yazma izni yoktur. (Bağlantı .ilk dosya ve bağlantıları artımlı olmayan yoksayar.)  
  
-   .exe veya .dll çıktı dosyası eksik.  
  
-   .ilk, .exe veya .dll'nin zaman damgası değişmiş.  
  
-   LINK seçeneği değiştirilir. Yapılar arasında değiştirildiğinde çoğu bağlantı seçenekleri, tam bir bağlantıya neden olur.  
  
-   Bir nesne (.obj) dosyası eklendi veya atlandı.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **bağlayıcı** klasör.  
  
3.  Seçin **genel** özellik sayfası.  
  
4.  Değiştirme **etkinleştirmek artımlı bağlantılandırma** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkIncremental%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)