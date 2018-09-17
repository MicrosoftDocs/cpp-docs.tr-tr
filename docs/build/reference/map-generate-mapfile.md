---
title: -MAP (eşlem dosyası oluştur) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /map
- VC.Project.VCLinkerTool.MapFileName
- VC.Project.VCLinkerTool.GenerateMapFile
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c39134f45b1a044a76139d33aa9e761a0f14c8c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725588"
---
# <a name="map-generate-mapfile"></a>/MAP (Eşlem Dosyası Oluştur)

```
/MAP[:filename]
```

## <a name="arguments"></a>Arguments

*Dosya adı*<br/>
Mapfile kullanıcı tarafından belirtilen adı. Varsayılan adını değiştirir.

## <a name="remarks"></a>Açıklamalar

Map seçeneği bağlayıcıya eşlem dosyası oluşturmasını söyler.

Varsayılan olarak, bağlayıcı temel programının adını ve uzantısını .map ile eşlem dosyası adı. İsteğe bağlı *filename* bir eşlem dosyası için varsayılan adı geçersiz kılmanıza da olanak tanır.

Bir eşlem bağlantılandırılan program hakkında aşağıdaki bilgileri içeren bir metin dosyasıdır:

- Dosyanın temel adı Modül adı

- (Dosya sisteminden değil) programı dosya üstbilgisi itibaren zaman damgası

- Programında, her grubun başlangıç adresi ile gruplarının bir listesini (olarak *bölümü*:*uzaklığı*), uzunluğunu, grup adı ve sınıfı

- Her adresi ile ortak semboller listesini (olarak *bölümü*:*uzaklığı*), sembol adı, düz bir adres ve simgenin tanımlandığı .obj dosyası

- Giriş noktası (olarak *bölümü*:*uzaklığı*)

[Mapınfo](../../build/reference/mapinfo-include-information-in-mapfile.md) seçeneği mapfile içinde dahil edilecek ek bilgiler belirtir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **hata ayıklama** özellik sayfası.

1. Değiştirme **harita dosyası oluştur** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateMapFile%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapFileName%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)