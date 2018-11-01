---
title: /TLBOUT (.TLB Dosyası Adlandır)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.TypeLibraryFile
- /tlbout
helpviewer_keywords:
- tlb files, renaming
- TLBOUT linker option
- /TLBOUT linker option
- .tlb files, renaming
- -TLBOUT linker option
ms.assetid: 0df6d078-2e48-46c9-a1a5-02674d85dce8
ms.openlocfilehash: 97659341d4566cd34fe705b89758929f0c1e995d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613817"
---
# <a name="tlbout-name-tlb-file"></a>/TLBOUT (.TLB Dosyası Adlandır)

```
/TLBOUT:[path\]filename
```

## <a name="arguments"></a>Arguments

*Yolu*<br/>
.Tlb dosyasının nerede oluşturulması gereken bir mutlak veya göreli yol belirtimi.

*Dosya adı*<br/>
MIDL derleyicisi tarafından oluşturulan .tlb dosyasının adını belirtir. Dosyanın uzantısı varsayılır; belirtin *filename*.tlb uzantılı istiyorsanız .tlb.

## <a name="remarks"></a>Açıklamalar

/ Tlbout seçeneği .tlb dosyasının uzantısı ve adını belirtir.

MIDL derleyicisi olan projelerin bağlanırken Visual C++ bağlayıcı tarafından çağrılır [Modülü](../../windows/module-cpp.md) özniteliği.

/ Tlbout belirtilmezse, .tlb dosyasının adını alırsınız [/ıdlout](../../build/reference/idlout-name-midl-output-files.md) *filename*. / Idlout belirtilmezse, .tlb dosyasının vc70.tlb çağrılmaz.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **katıştırılmış IDL** özellik sayfası.

1. Değiştirme **tür kitaplığı** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)<br/>
[/IGNOREIDL (Öznitelikleri MIDL'ye İşleme)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/MIDL (MIDL Komut Satırı Seçeneklerini Belirt)](../../build/reference/midl-specify-midl-command-line-options.md)<br/>
[Öznitelikli Program Derleme](../../windows/building-an-attributed-program.md)