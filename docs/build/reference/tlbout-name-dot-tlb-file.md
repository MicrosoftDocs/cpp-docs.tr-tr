---
description: Şu konuda daha fazla bilgi edinin:/TLHAKKıNDA (ad. TLB dosyası)
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
ms.openlocfilehash: 4e99f3b5a036ddbc424732e771f7bab27aeb228d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230009"
---
# <a name="tlbout-name-tlb-file"></a>/TLBOUT (.TLB Dosyası Adlandır)

```
/TLBOUT:[path\]filename
```

## <a name="arguments"></a>Arguments

*Yolun*<br/>
. Tlb dosyasının oluşturulması için mutlak veya göreli bir yol belirtimi.

*filename*<br/>
MıDL derleyicisi tarafından oluşturulan. tlb dosyasının adını belirtir. Hiçbir dosya uzantısı varsayıldı; . tlb uzantısını istiyorsanız *filename*. tlb belirtin.

## <a name="remarks"></a>Açıklamalar

/TLHAKKıNDA seçeneği. tlb dosyasının adını ve uzantısını belirtir.

MıDL derleyicisi, [module](../../windows/attributes/module-cpp.md) özniteliği olan projeler bağlanırken MSVC bağlayıcı tarafından çağırılır.

/TLHAKKıNDA belirtilmemişse,. tlb dosyası adı [/IDLOUT](idlout-name-midl-output-files.md) *filename* konumundan alınır. /IDLOUT belirtilmemişse,. tlb dosyası vc70. tlb olarak adlandırılacaktır.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **KATıŞTıRıLMıŞ IDL** Özellik sayfasına tıklayın.

1. **Tür kitaplığı** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)<br/>
[/IGNOREıDL (öznitelikleri MıDL 'ye Işleme)](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/MıDL (MıDL komut satırı seçeneklerini belirt)](midl-specify-midl-command-line-options.md)<br/>
[Öznitelikli Program Oluşturma](../../windows/attributes/cpp-attributes-com-net.md)
