---
description: Şu konuda daha fazla bilgi edinin:/STACK (yığın ayırmaları)
title: /STACK (Yığın Ayırmaları)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.StackReserveSize
- VC.Project.VCLinkerTool.StackCommitSize
- /stack
helpviewer_keywords:
- STACK linker option
- -STACK linker option
- memory allocation, stack
- /STACK linker option
- stack, setting size
ms.assetid: 73283660-e4bd-47cc-b5ca-04c5d739034c
ms.openlocfilehash: 6e74b508d8cdb2340c73360bf35272d9113a0f75
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224475"
---
# <a name="stack-stack-allocations"></a>/STACK (Yığın Ayırmaları)

```
/STACK:reserve[,commit]
```

## <a name="remarks"></a>Açıklamalar

/STACK seçeneği, yığının boyutunu bayt cinsinden ayarlar. Bu seçeneği yalnızca bir. exe dosyası oluşturduğunuzda kullanın.

`reserve`Değer, sanal bellekteki toplam yığın ayırmayı belirtir. ARM, x86 ve x64 makineler için varsayılan yığın boyutu 1 MB 'tır.

`commit` , işletim sistemi tarafından yorumlamayı tabidir. Windows WindowsRT 'de, aynı anda ayrılacak fiziksel bellek miktarını belirtir. Yürütülen sanal bellek, disk belleği dosyasında ayrılan alanın ayrılmasına neden olur. `commit`Uygulamanın daha fazla yığın alanına ihtiyacı olduğunda daha yüksek bir değer zaman kazandırır, ancak bellek gereksinimlerini ve muhtemelen başlangıç süresini arttırır. ARM, x86 ve x64 makineler için varsayılan tamamlama değeri 4 KB 'tır.

`reserve` `commit` Ondalık veya C dili gösteriminde ve değerlerini belirtin.

Yığının boyutunu ayarlamaya yönelik başka bir yöntem de modül tanımı (. def) dosyasındaki [STACKSIZE](stacksize.md) deyimidir. **STACKSIZE** , her ikisi de belirtilmişse yığın ayırmaları (/Stack) seçeneğini geçersiz kılar. . Exe dosyası [editbin](editbin-reference.md) Aracı kullanılarak derlendikten sonra yığın boyutunu değiştirebilirsiniz.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörünü seçin.

1. **Sistem** özellik sayfasını seçin.

1. Aşağıdaki özelliklerden birini değiştirin:

   - **Yığın kayıt boyutu**

   - **Yığın ayırma boyutu**

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackCommitSize%2A> <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackReserveSize%2A> . ve Özellikler.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
