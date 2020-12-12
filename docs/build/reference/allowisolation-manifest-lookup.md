---
description: Daha fazla bilgi edinin:/ALLOWıSOLATıON (bildirim arama)
title: /ALLOWISOLATION (Bildirim Arama)
ms.date: 11/04/2016
f1_keywords:
- /ALLOWISOLATION
- VC.Project.VCLinkerTool.AllowIsolation
helpviewer_keywords:
- -ALLOWISOLATION linker option
- /ALLOWISOLATION linker option
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
ms.openlocfilehash: 659c908e4de910941ca71c9f40814608df19c6d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187227"
---
# <a name="allowisolation-manifest-lookup"></a>/ALLOWISOLATION (Bildirim Arama)

Bildirim arama için davranışı belirtir.

## <a name="syntax"></a>Syntax

```
/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>Açıklamalar

**/Allowisolation: Hayır** , hiçbir bildirim olmadığı gibi dll 'lerin yüklendiğini ve bağlayıcının `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` isteğe bağlı üst bilgi alanında biti ayarlamaya neden olduğunu gösterir `DllCharacteristics` .

**/Allowısolation** , işletim sisteminin bildirim aramalarını ve yüklemelerini sağlar.

**/Allowisolation** varsayılandır.

Bir yürütülebilir dosya için yalıtım devre dışı bırakıldığında, Windows yükleyicisi yeni oluşturulan işlem için bir uygulama bildirimi bulmaya çalışmaz. Yürütülebilir dosya içinde bir bildirim olsa veya çalıştırılabilir <em>-adı</em>**. exe. manifest** adlı yürütülebilir dosya ile aynı dizine yerleştirilmiş olsa bile, yeni işlem varsayılan etkinleştirme bağlamına sahip olmayacaktır.

Daha fazla bilgi için bkz. [bildirim dosyaları başvurusu](/windows/win32/SbsCs/manifest-files-reference).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **bildirim dosyası** özellik sayfasını seçin.

1. **Yalıtıma Izin ver** özelliğini değiştirin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
