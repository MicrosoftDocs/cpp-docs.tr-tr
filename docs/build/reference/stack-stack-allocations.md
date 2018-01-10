---
title: "-STACK (yığın ayırmaları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.StackReserveSize
- VC.Project.VCLinkerTool.StackCommitSize
- /stack
dev_langs: C++
helpviewer_keywords:
- STACK linker option
- -STACK linker option
- memory allocation, stack
- /STACK linker option
- stack, setting size
ms.assetid: 73283660-e4bd-47cc-b5ca-04c5d739034c
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6b487ff830abd3dfa97a748c81d541cbd9fdd0b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="stack-stack-allocations"></a>/STACK (Yığın Ayırmaları)
```  
/STACK:reserve[,commit]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 /STACK seçeneği yığın boyutunu bayt cinsinden ayarlar. Yalnızca bir .exe dosyası oluşturduğunuzda bu seçeneği kullanın.  
  
 `reserve` Değeri sanal bellek toplam yığın ayırma belirtir. ARM, x86 için ve [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] makineler, varsayılan yığın boyutu 1 MB olduğu.  
  
 `commit`işletim sistemi tarafından tercüme tabidir. Windows WindowsRT aynı anda ayırmak için fiziksel bellek miktarını belirtir. Kaydedilebilen sanal bellek disk belleği dosyasında ayrılacak alanı neden olur. Yüksek bir `commit` zaman uygulama daha fazla yığın alanı gerekiyor, ancak bellek gereksinimlerini ve büyük olasılıkla başlangıç zamanını artırır zaman kaydeder. ARM, x86 için ve [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] makineler, varsayılan yürütme değer olan 4 KB.  
  
 Belirtin `reserve` ve `commit` değerleri ondalık veya dil C gösterimi.  
  
 Yığın boyutunu ayarlamak için başka bir yolu [STACKSIZE](../../build/reference/stacksize.md) bir modül-tanımlama (.def) dosyası deyiminde. **STACKSIZE** yığın ayırmaları geçersiz kılar (/ yığın) her ikisi de belirtilirse seçeneği. .Exe dosyasını kullanarak oluşturulduktan sonra yığın boyutunu değiştirebilirsiniz [EDITBIN](../../build/reference/editbin-reference.md) aracı.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Seçin **bağlayıcı** klasör.  
  
3.  Seçin **sistem** özellik sayfası.  
  
4.  Aşağıdaki özelliklerden birini değiştirin:  
  
    -   **Yığın ayırma boyutu**  
  
    -   **Yığın ayırma boyutu**  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackCommitSize%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackReserveSize%2A> özellikleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)