---
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
ms.openlocfilehash: 27de554e1933b2753f641be358461c8d7ff4fffa
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813805"
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

Yığın boyutunu ayarlamak için başka bir yöntem, [STACKSIZE](stacksize.md) deyiminde bir modül-tanımlama (.def) dosyası. **STACKSIZE** yığın ayırmaları geçersiz kılar. (/ yığın) her ikisi de belirtilirse seçeneği. .Exe dosyasını kullanarak oluşturulduktan sonra yığın boyutu değiştirebilirsiniz [EDITBIN](editbin-reference.md) aracı.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **bağlayıcı** klasör.

1. Seçin **sistem** özellik sayfası.

1. Aşağıdaki özelliklerden birini değiştirin:

   - **Yığın işleme boyutu**

   - **Yığın ayırma boyutu**

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackCommitSize%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackReserveSize%2A> özellikleri.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
