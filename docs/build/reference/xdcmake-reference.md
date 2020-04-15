---
title: XDCMake Başvurusu
ms.date: 11/04/2016
f1_keywords:
- xdcmake
helpviewer_keywords:
- xdcmake program
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
ms.openlocfilehash: 9970470d1feb471f9e0b8c9284a08337dac7ef0f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335854"
---
# <a name="xdcmake-reference"></a>XDCMake Başvurusu

xdcmake.exe .xdc dosyalarını bir .xml dosyasında derleyen bir programdır. Bir .xdc dosyası, kaynak kodu [/doc](doc-process-documentation-comments-c-cpp.md) ile derlendiğinde ve kaynak kod dosyası XML etiketleri ile işaretlenmiş belge yorumları içerdiğinde, her kaynak kodu dosyası için MSVC derleyicisi tarafından oluşturulur.

### <a name="to-use-xdcmakeexe-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında xdcmake.exe kullanmak için

1. Projenin **Özellik Sayfaları** iletişim kutusunu açın. Ayrıntılar için [Visual Studio'da C++ derleyicisi ayarlanın ve özellikler oluşturun.](../working-with-project-properties.md)

1. Yapılandırma **Özellikleri** klasörünü açın.

1. **XML Belge Açıklamaları** özelliği sayfasını tıklatın.

> [!NOTE]
> komut satırındaki xdcmake.exe seçenekleri, geliştirme ortamında (özellik sayfaları) kullanıldığında seçeneklerden farklıdır. Geliştirme ortamında xdcmake.exe kullanma hakkında bilgi için, [XML Belge Jeneratör Aracı Özellik Sayfaları](xml-document-generator-tool-property-pages.md)bakın.

## <a name="syntax"></a>Sözdizimi

xdcmake`input_filename options`

## <a name="parameters"></a>Parametreler

*input_filename*<br/>
xdcmake.exe girişi olarak kullanılan .xdc dosyalarının dosya adı. Bir veya daha fazla .xdc dosya belirtin veya geçerli dizindeki tüm .xdc dosyalarını kullanmak için *.xdc kullanın.

*Seçenekler*<br/>
Sıfır veya daha fazlası aşağıdakilerden:

|Seçenek|Açıklama|
|------------|-----------------|
|/?, /help|Xdcmake.exe için yardım görüntüleyin.|
|/assembly:*dosya adı*|.xml dosyasındaki \<montaj> etiketinin değerini belirtmenizi sağlar.  Varsayılan olarak, \<derleme> etiketinin değeri .xml dosyasının dosya adı ile aynıdır.|
|/nologo|Telif hakkı iletisi bastırın.|
|/out:*dosya adı*|.xml dosyasının adını belirtmenizi sağlar.  Varsayılan olarak, .xml dosyasının adı xdcmake.exe tarafından işlenen ilk .xdc dosyasının dosya adıdır.|

## <a name="remarks"></a>Açıklamalar

Visual Studio bir proje inşa ederken otomatik olarak xdcmake.exe çağırır. Ayrıca komut satırında xdcmake.exe çağırabilirsiniz.

Kaynak kod dosyalarına belge açıklamaları ekleme hakkında daha fazla bilgi için [Belgeler için Önerilen Etiketlere](recommended-tags-for-documentation-comments-visual-cpp.md) bakın Açıklamalar.

## <a name="see-also"></a>Ayrıca bkz.

[XML Dokümantasyon](xml-documentation-visual-cpp.md)
