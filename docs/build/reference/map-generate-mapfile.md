---
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
ms.openlocfilehash: 9a45fd5ea44b8908e77f847275bde42b86385cdb
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57817952"
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

[Mapınfo](mapinfo-include-information-in-mapfile.md) seçeneği mapfile içinde dahil edilecek ek bilgiler belirtir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **hata ayıklama** özellik sayfası.

1. Değiştirme **harita dosyası oluştur** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateMapFile%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapFileName%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
