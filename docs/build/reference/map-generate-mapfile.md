---
description: Daha fazla bilgi edinin:/MAP (mapfile üret)
title: /MAP (Eşlem Dosyası Oluştur)
ms.date: 11/04/2016
f1_keywords:
- /map
- VC.Project.VCLinkerTool.MapFileName
- VC.Project.VCLinkerTool.GenerateMapFile
helpviewer_keywords:
- mapfiles, creating linker
- generate mapfile linker option
- mapfile linker option
- mapfiles, information about program being linked
- MAP linker option
- -MAP linker option
- mapfiles, specifying file name
- /MAP linker option
ms.assetid: 9ccce53d-4e36-43da-87b0-7603ddfdea63
ms.openlocfilehash: 28e3823099b4893dcf344a0b1aae99577d850821
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176437"
---
# <a name="map-generate-mapfile"></a>/MAP (Eşlem Dosyası Oluştur)

```
/MAP[:filename]
```

## <a name="arguments"></a>Arguments

*filename*<br/>
Mapfile için Kullanıcı tarafından belirtilen bir ad. Varsayılan adı değiştirir.

## <a name="remarks"></a>Açıklamalar

/MAP seçeneği, bağlayıcıya bir mapfile oluşturmasını söyler.

Varsayılan olarak, bağlayıcı map dosyasını programın temel adıyla ve. Map uzantısıyla adlandırır. İsteğe bağlı *Dosya* adı, bir mapfile için varsayılan adı geçersiz kılmanızı sağlar.

Eşlem dosyası, bağlanan programla ilgili olarak aşağıdaki bilgileri içeren bir metin dosyasıdır:

- Dosyanın temel adı olan modül adı

- Program dosyası başlığından zaman damgası (dosya sisteminden değil)

- Her grubun başlangıç adresi ( *bölüm*:*konum*), uzunluk, Grup adı ve sınıf ile programdaki grupların listesi

- Her adresle ( *bölüm*:*konum* olarak), sembol adı, düz adres ve bir simgenin tanımlandığı. obj dosyasının bulunduğu genel simgelerin listesi

- Giriş noktası ( *bölüm*:*konum*)

[/MapInfo](mapinfo-include-information-in-mapfile.md) seçeneği, mapfile 'a dahil edilecek ek bilgileri belirtir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Hata ayıklama** Özellik sayfasına tıklayın.

1. **Eşleme dosyası oluştur** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateMapFile%2A> <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapFileName%2A> . ve.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
