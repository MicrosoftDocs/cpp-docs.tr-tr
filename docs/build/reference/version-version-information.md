---
title: /VERSION (Sürüm Bilgileri)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Version
- /version
helpviewer_keywords:
- -VERSION linker option
- Version Information linker option
- version numbers, specifying in .exe
- /VERSION linker option
- VERSION linker option
ms.assetid: b86d0e86-dca6-4316-aee2-d863ccb9f223
ms.openlocfilehash: 626461fc7a9fc6dd7b6578e836733d154a66862a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807611"
---
# <a name="version-version-information"></a>/VERSION (Sürüm Bilgileri)

```
/VERSION:major[.minor]
```

## <a name="arguments"></a>Arguments

*Ana* ve *küçük*<br/>
İstediğiniz .exe veya .dll dosyasının üst bilgisinde sürüm numarası.

## <a name="remarks"></a>Açıklamalar

/ VERSION seçeneği .exe veya .dll dosyasının üst bilgisinde sürüm numarası put söyler. DUMPBIN kullanma [OPTIONAL ](headers.md) /VERSION etkisini görmek için isteğe bağlı üstbilgi değerleri alanının görüntü sürümünü görmek için.

*Ana* ve *küçük* bağımsız değişkenler 0 ile 65.535 aralığındaki ondalık sayı. Varsayılan değer 0,0 sürümüdür.

/ VERSION ile belirtilen bilgileri dosya Gezgini'nde özelliklerini görüntülerken bir uygulama için görüntülenen sürüm bilgilerini etkilemez. Bu sürüm bilgileri, uygulama oluşturmak için kullanılan bir kaynak dosyasından gelir. Bkz: [sürüm bilgileri Düzenleyicisi](../../windows/version-information-editor.md) daha fazla bilgi için.

Bir sürüm numarası eklemek için başka bir yöntem, [sürüm](version-c-cpp.md) modül-tanımlama bildirimi.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **genel** özellik sayfası.

1. Değiştirme **sürüm** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Version%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
