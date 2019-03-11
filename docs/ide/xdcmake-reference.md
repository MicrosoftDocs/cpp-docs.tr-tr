---
title: XDCMake Başvurusu
ms.date: 11/04/2016
f1_keywords:
- xdcmake
helpviewer_keywords:
- xdcmake program
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
ms.openlocfilehash: adbb06b5100850aac0cfd191a530d5c98b380738
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740439"
---
# <a name="xdcmake-reference"></a>XDCMake Başvurusu

xdcmake.exe'yi .xdc dosyalarının bir .xml dosyasının içine derleyen bir programdır. Kaynak kodu ile derlendiğinde bir .xdc dosyasını her kaynak kodu dosyası için Visual C++ derleyicisi tarafından oluşturulur [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) ve kaynak kodu dosyasının, XML etiketleri ile artırıldığında belge açıklamaları içerdiğinde.

### <a name="to-use-xdcmakeexe-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında xdcmake.exe'yi kullanmak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../ide/working-with-project-properties.md).

1. Açık **yapılandırma özellikleri** klasör.

1. Tıklayın **XML belge açıklamaları** özellik sayfası.

> [!NOTE]
>  xdcmake.exe'yi geliştirme ortamında (özellik sayfaları) kullanıldığında xdcmake.exe'yi seçenekleri komut satırında seçeneklerden farklıdır. Geliştirme ortamında xdcmake.exe'yi kullanma hakkında daha fazla bilgi için bkz: [XML belgesi oluşturma aracı özellik sayfaları](../ide/xml-document-generator-tool-property-pages.md).

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

Bkz: [belge açıklamaları için önerilen etiketler](../ide/recommended-tags-for-documentation-comments-visual-cpp.md) belge açıklamaları için kaynak kodu dosyaları ekleme hakkında daha fazla bilgi.

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](../ide/xml-documentation-visual-cpp.md)
