---
title: -STACK (yığın ayırmaları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.StackReserveSize
- VC.Project.VCLinkerTool.StackCommitSize
- /stack
dev_langs:
- C++
helpviewer_keywords:
- STACK linker option
- -STACK linker option
- memory allocation, stack
- /STACK linker option
- stack, setting size
ms.assetid: 73283660-e4bd-47cc-b5ca-04c5d739034c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29ed2efa73d3ec1014bf0a65e7b4b1b1b85cf879
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42464499"
---
# <a name="stack-stack-allocations"></a>/STACK (Yığın Ayırmaları)
```  
/STACK:reserve[,commit]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 /STACK seçeneği, yığın boyunu bayt cinsinden ayarlar. Bir .exe dosyası oluşturduğunuzda bu seçeneği kullanın.  
  
 `reserve` Değeri sanal bellekte toplam yığın ayırma belirtir. ARM için x86 ve x64 makineler, varsayılan yığın boyutu 1 MB olan.  
  
 `commit` işletim sistemi tarafından yorumu tabidir. Windows WindowsRT içinde aynı anda ayrılacak fiziksel bellek miktarını belirtir. Yürütülen sanal bellek disk belleği dosyasında ayrılacak alanı neden olur. Daha yüksek bir `commit` değeri kaydeder zaman zaman uygulama daha fazla yığın alanı gerekiyor, ancak bellek gereksinimleri ve büyük olasılıkla başlangıç süresini artırır. ARM için 4 KB x86 ve x64 makineler, varsayılan işleme değer olur.  
  
 Belirtin `reserve` ve `commit` değerleri ondalık ya da C dili gösterimi.  
  
 Yığın boyutunu ayarlamak için başka bir yöntem, [STACKSIZE](../../build/reference/stacksize.md) deyiminde bir modül-tanımlama (.def) dosyası. **STACKSIZE** yığın ayırmaları geçersiz kılar. (/ yığın) her ikisi de belirtilirse seçeneği. .Exe dosyasını kullanarak oluşturulduktan sonra yığın boyutu değiştirebilirsiniz [EDITBIN](../../build/reference/editbin-reference.md) aracı.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Seçin **bağlayıcı** klasör.  
  
3.  Seçin **sistem** özellik sayfası.  
  
4.  Aşağıdaki özelliklerden birini değiştirin:  
  
    -   **Yığın işleme boyutu**  
  
    -   **Yığın ayırma boyutu**  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackCommitSize%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackReserveSize%2A> özellikleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)