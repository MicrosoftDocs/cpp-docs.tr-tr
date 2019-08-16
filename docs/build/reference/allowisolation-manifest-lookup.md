---
title: /ALLOWISOLATION (Bildirim Arama)
ms.date: 11/04/2016
f1_keywords:
- /ALLOWISOLATION
- VC.Project.VCLinkerTool.AllowIsolation
helpviewer_keywords:
- -ALLOWISOLATION linker option
- /ALLOWISOLATION linker option
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
ms.openlocfilehash: 7c799f3d44428643bccc2869255ffa4e9d194d70
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493131"
---
# <a name="allowisolation-manifest-lookup"></a>/ALLOWISOLATION (Bildirim Arama)

Bildirim arama için davranışı belirtir.

## <a name="syntax"></a>Sözdizimi

```
/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>Açıklamalar

**/Allowisolation: Hayır** , hiçbir bildirim olmadığı gibi dll 'lerin yüklendiğini ve bağlayıcının isteğe bağlı üst bilgi `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` `DllCharacteristics` alanında biti ayarlamaya neden olduğunu gösterir.

**/Allowısolation** , işletim sisteminin bildirim aramalarını ve yüklemelerini sağlar.

**/Allowisolation** varsayılandır.

Bir yürütülebilir dosya için yalıtım devre dışı bırakıldığında, Windows yükleyicisi yeni oluşturulan işlem için bir uygulama bildirimi bulmaya çalışmaz. Yürütülebilir dosya içinde bir bildirim olsa veya çalıştırılabilir <em>-adı</em> **. exe. manifest**adlı yürütülebilir dosya ile aynı dizine yerleştirilmiş olsa bile, yeni işlem varsayılan etkinleştirme bağlamına sahip olmayacaktır.

Daha fazla bilgi için bkz. [bildirim dosyaları başvurusu](/windows/win32/SbsCs/manifest-files-reference).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > bağlayıcıbildirim > **dosyası** özellik sayfasını seçin.

1. Yalıtıma **Izin ver** özelliğini değiştirin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
