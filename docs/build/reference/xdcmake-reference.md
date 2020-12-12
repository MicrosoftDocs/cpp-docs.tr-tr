---
description: 'Daha fazla bilgi edinin: XDCMake başvurusu'
title: XDCMake Başvurusu
ms.date: 11/04/2016
f1_keywords:
- xdcmake
helpviewer_keywords:
- xdcmake program
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
ms.openlocfilehash: c9e597828ca37b67a21a5b2f442fffcac001b541
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261001"
---
# <a name="xdcmake-reference"></a>XDCMake Başvurusu

xdcmake.exe. xdc dosyalarını bir. xml dosyasına derleyen bir programdır. Kaynak kodu [/doc](doc-process-documentation-comments-c-cpp.md) ile derlendiğinde ve kaynak kod dosyası xml etiketleriyle işaretlenmiş belge açıklamalarını içerdiğinde, bir. xdc dosyası her kaynak kodu dosyası için MSVC derleyicisi tarafından oluşturulur.

### <a name="to-use-xdcmakeexe-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında xdcmake.exe kullanmak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** klasörünü açın.

1. **XML belgesi açıklamaları** Özellik sayfasına tıklayın.

> [!NOTE]
> Komut satırındaki xdcmake.exe seçenekleri, xdcmake.exe geliştirme ortamında (Özellik sayfaları) kullanıldığında kullanılan seçeneklerden farklıdır. Geliştirme ortamında xdcmake.exe kullanma hakkında daha fazla bilgi için bkz. [XML Document Generator aracı özellik sayfaları](xml-document-generator-tool-property-pages.md).

## <a name="syntax"></a>Syntax

xdcmake `input_filename options`

## <a name="parameters"></a>Parametreler

*input_filename*<br/>
xdcmake.exe giriş olarak kullanılan. xdc dosyalarının dosya adı. Bir veya daha fazla. xdc dosyası belirtin veya geçerli dizindeki tüm. xdc dosyalarını kullanmak için *. xdc kullanın.

*Seçenekler*<br/>
Aşağıdakilerden sıfır veya daha fazlası:

|Seçenek|Açıklama|
|------------|-----------------|
|/?,/Help|xdcmake.exe için yardımı görüntüleyin.|
|/Assembly:*filename*|\<assembly>. Xml dosyasında etiketinin değerini belirtmenize izin verir.  Varsayılan olarak, \<assembly> etiketinin değeri. xml dosyasının dosya adıyla aynıdır.|
|/nologo|Telif hakkı iletisini gizleyin.|
|/Out:*filename*|. Xml dosyasının adını belirtmenizi sağlar.  Varsayılan olarak,. xml dosyasının adı, xdcmake.exe tarafından işlenen ilk. xdc dosyasının dosya adıdır.|

## <a name="remarks"></a>Açıklamalar

Visual Studio, bir proje derlerken xdcmake.exe otomatik olarak çağırır. Ayrıca, komut satırında xdcmake.exe çağırabilirsiniz.

Belge açıklamalarını kaynak kodu dosyalarına ekleme hakkında daha fazla bilgi için bkz. [belge açıklamaları Için önerilen Etiketler](recommended-tags-for-documentation-comments-visual-cpp.md) .

## <a name="see-also"></a>Ayrıca bkz.

[XML Belgeleri](xml-documentation-visual-cpp.md)
