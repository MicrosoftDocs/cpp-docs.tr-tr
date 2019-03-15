---
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
ms.openlocfilehash: c52bfb9e4b6d0e94cecb77c766ac9e82b52f1e66
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820641"
---
# <a name="tlbid-specify-resource-id-for-typelib"></a>/TLBID (TypeLib için Kaynak Kimliğini Belirt)

```
/TLBID:id
```

## <a name="arguments"></a>Arguments

*id*<br/>
Kullanıcı tanımlı bir değer için bir bağlayıcı tarafından oluşturulan tür kitaplığı. Bu, 1 varsayılan kaynak kimliği geçersiz kılar.

## <a name="remarks"></a>Açıklamalar

Öznitelikleri kullanan bir program derlerken, bağlayıcı bir tür kitaplığı oluşturur. Bağlayıcı tür kitaplığı için bir kaynak kimliği 1 atar.

Bu kaynak kimliği, var olan kaynaklardan biri ile çakışırsa, farklı bir kimlik ile /TLBID belirtebilirsiniz. Öğesine iletebileceğiniz değerleri aralığı `id` 1-65535'tir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **katıştırılmış IDL** özellik sayfası.

1. Değiştirme **TypeLib kaynak kimliği** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
