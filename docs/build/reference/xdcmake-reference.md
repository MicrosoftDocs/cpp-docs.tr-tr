---
title: XDCMake Başvurusu
ms.date: 11/04/2016
f1_keywords:
- xdcmake
helpviewer_keywords:
- xdcmake program
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
ms.openlocfilehash: 097c105e005a3c734ba86139ed3b4b6ecdcf49d9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316398"
---
# <a name="xdcmake-reference"></a>XDCMake Başvurusu

xdcmake.exe'yi .xdc dosyalarının bir .xml dosyasının içine derleyen bir programdır. Kaynak kodu ile derlendiğinde bir .xdc dosyasını her kaynak kodu dosyası için MSVC derleyici tarafından oluşturulur [/doc](doc-process-documentation-comments-c-cpp.md) ve kaynak kodu dosyasının, XML etiketleri ile artırıldığında belge açıklamaları içerdiğinde.

### <a name="to-use-xdcmakeexe-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında xdcmake.exe'yi kullanmak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Açık **yapılandırma özellikleri** klasör.

1. Tıklayın **XML belge açıklamaları** özellik sayfası.

> [!NOTE]
>  xdcmake.exe'yi geliştirme ortamında (özellik sayfaları) kullanıldığında xdcmake.exe'yi seçenekleri komut satırında seçeneklerden farklıdır. Geliştirme ortamında xdcmake.exe'yi kullanma hakkında daha fazla bilgi için bkz: [XML belgesi oluşturma aracı özellik sayfaları](xml-document-generator-tool-property-pages.md).

## <a name="syntax"></a>Sözdizimi

xdcmake `input_filename options`

## <a name="parameters"></a>Parametreler

*input_filename*<br/>
Xdcmake.exe'yi girdi olarak kullanılan .xdc dosyalarının dosya adı. Bir veya daha fazla .xdc dosyalarının belirtin veya geçerli dizindeki tüm .xdc dosyalarının *.xdc kullanın.

*Seçenekler*<br/>
Sıfır veya daha fazlasını:

|Seçenek|Açıklama|
|------------|-----------------|
|/?, / help|Xdcmake.exe'yi için yardımı görüntüler.|
|/ Assembly:*dosya adı*|Değeri belirtmenize olanak tanır \<derleme > .xml dosyasında etiketi.  Varsayılan olarak, değerini \<derleme > etiketi olan .xml dosyasının dosya adı ile aynı.|
|/nologo|Telif hakkı iletisini bastır.|
|/ out:*dosya adı*|.Xml dosyasının adını belirtmenize olanak sağlar.  Varsayılan olarak, .xml dosyasının adını xdcmake.exe'yi tarafından işlenen ilk .xdc dosyasının dosya adıdır.|

## <a name="remarks"></a>Açıklamalar

Visual Studio xdcmake.exe'yi otomatik olarak bir proje derlenirken çağıracaktır. Komut satırında xdcmake.exe'yi de çağırabilirsiniz.

Bkz: [belge açıklamaları için önerilen etiketler](recommended-tags-for-documentation-comments-visual-cpp.md) belge açıklamaları için kaynak kodu dosyaları ekleme hakkında daha fazla bilgi.

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](xml-documentation-visual-cpp.md)
