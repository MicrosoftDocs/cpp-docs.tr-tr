---
description: Daha fazla bilgi edinin:/TLDEKLARASYON (TypeLib için kaynak KIMLIĞINI belirt)
title: /TLBID (TypeLib için Kaynak Kimliğini Belirt)
ms.date: 11/04/2016
f1_keywords:
- /tlbid
- VC.Project.VCLinkerTool.TypeLibraryResourceID
helpviewer_keywords:
- tlb files, specifying resource ID
- -TLBID linker option
- .tlb files, specifying resource ID
- /TLBID linker option
- TLBID linker option
- type libraries, specifying resource ID
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
ms.openlocfilehash: 4958229cbebe988867c5419d7953b6ffd968e45f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230022"
---
# <a name="tlbid-specify-resource-id-for-typelib"></a>/TLBID (TypeLib için Kaynak Kimliğini Belirt)

```
/TLBID:id
```

## <a name="arguments"></a>Arguments

*id*<br/>
Bağlayıcı tarafından oluşturulan tür kitaplığı için Kullanıcı tarafından belirtilen bir değer. Varsayılan kaynak KIMLIĞI olan 1 ' i geçersiz kılar.

## <a name="remarks"></a>Açıklamalar

Öznitelikleri kullanan bir programı derlerken bağlayıcı bir tür kitaplığı oluşturur. Bağlayıcı, tür kitaplığına 1 kaynak KIMLIĞI atayacaktır.

Bu kaynak KIMLIĞI, mevcut kaynaklarınızdan biriyle çakışırsa,/TLBID. ile başka bir KIMLIK belirtebilirsiniz Geçirebilmeniz için değer aralığı `id` 1-65535 ' dir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **KATıŞTıRıLMıŞ IDL** Özellik sayfasına tıklayın.

1. **TypeLib kaynak kimliği** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
