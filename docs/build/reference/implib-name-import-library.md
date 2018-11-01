---
title: /IMPLIB (İçeri Aktarma Kitaplığını Adlandır)
ms.date: 11/04/2016
f1_keywords:
- /implib
- VC.Project.VCLinkerTool.ImportLIbrary
helpviewer_keywords:
- IMPLIB linker option
- /IMPLIB linker option
- -IMPLIB linker option
- import libraries, overriding default name
ms.assetid: fe8f71ab-7055-41b5-8ef8-2b97cfa4a432
ms.openlocfilehash: 268a091d3e0bc825acae96dafc5d92ffa11c7bc3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50589587"
---
# <a name="implib-name-import-library"></a>/IMPLIB (İçeri Aktarma Kitaplığını Adlandır)

> / IMPLIB:*dosya adı*

## <a name="parameters"></a>Parametreler

*Dosya adı*<br/>
İçeri aktarma kitaplığının kullanıcı tarafından belirtilen adı. Varsayılan adını değiştirir.

## <a name="remarks"></a>Açıklamalar

/IMPLIB seçenek dışarı aktarmaları içeren bir program oluşturduğunda bağlantı oluşturan içeri aktarma kitaplığı için varsayılan adı geçersiz kılar. Varsayılan adı uzantısı ile ana çıkış dosyası ve temel adından oluşturulur. LIB. Bir veya daha fazlasını belirtilmişse bir program dışarı aktarmaları içerir:

- [__Declspec(dllexport)](../../cpp/dllexport-dllimport.md) kaynak koddaki anahtar sözcüğü

- [Dışarı aktarmalar](../../build/reference/exports.md) .def dosyası deyimi

- Bir [/dışarı aktarma](../../build/reference/export-exports-a-function.md) bağlantı komut belirtimi

İçeri aktarma kitaplığı değil oluşturulurken bağlantı /IMPLIB yok sayar. Hiçbir dışarı aktarma belirtilmezse, içeri aktarma kitaplığı bağlantı oluşturmaz. Bir dışarı aktarma dosyası derleme kullanılırsa, içeri aktarma kitaplığı zaten var ve bir oluşturmaz bağlantı varsayar. İçeri aktarma kitaplıkları ve dışarı aktarma dosyaları hakkında daha fazla bilgi için bkz: [LIB başvurusu](../../build/reference/lib-reference.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **Gelişmiş** özellik sayfası.

1. Değiştirme **içeri aktarma kitaplığını** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ImportLibrary%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)