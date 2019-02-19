---
title: / CETCOMPAT (denetim akışı zorlama teknolojisi ile uyumlu)
ms.date: 02/19/2019
f1_keywords:
- /CETCOMPAT
helpviewer_keywords:
- /CETCOMPAT linker option
- /CETCOMPAT
ms.openlocfilehash: 48eb1e2369e54d855bd19bb1d26ad057c903b9d0
ms.sourcegitcommit: 7cd712176e5bc341b9d8f899d41ad49f02f85e5f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/19/2019
ms.locfileid: "56418698"
---
# <a name="cetcompat-control-flow-enforcement-technology-compatible"></a>/ CETCOMPAT (denetim akışı zorlama teknolojisi ile uyumlu)

Bir yürütülebilir görüntü denetim akışı zorlama teknolojisi (CET) ile uyumlu olarak işaretlemek belirtir.

## <a name="syntax"></a>Sözdizimi

> **/ CETCOMPAT**\[**: NO**]

## <a name="arguments"></a>Arguments

**YOK**<br/>
Yürütülebilir dosya ile CET uyumlu işaretli olmamalıdır olduğunu belirtir.

## <a name="remarks"></a>Açıklamalar

Denetim akışı zorlama teknolojisi (CET) belirli türde kötü amaçlı yazılım saldırılarına karşı korumaya yönelik özellikler sağlayan bir bilgisayar işlemci özelliğidir. Daha fazla bilgi için [Intel denetim akışı zorlama Technology Preview](https://software.intel.com/sites/default/files/managed/4d/2a/control-flow-enforcement-technology-preview.pdf).

**/CETCOMPAT** bağlayıcı seçeneği bağlayıcıya ikili CET uyumlu olarak işaretlemek için. **/CETCOMPAT:No** ikili CET ile uyumlu değil olarak işaretler. Komut satırında iki seçenek de belirtilirse, belirtilen sonuncu kullanılır. Bu anahtar şu anda yalnızca x86 ve x64 mimarileri için geçerlidir.

**/CETCOMPAT** seçeneği olan Visual Studio 2019 Preview 3 araç takımında sonraki sürümlerinde kullanılabilir.

### <a name="to-set-the-cetcompat-linker-option-in-visual-studio"></a>Visual Studio'da /CETCOMPAT bağlayıcı seçeneğini ayarlamak için

1. Açık **özellik sayfaları** iletişim kutusu için proje. Daha fazla bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. İçinde **ek seçenekler** kutusunda **/CETCOMPAT** veya **/CETCOMPAT:NO** seçip **Tamam** veya **Uygula**yaptığınız değişiklikleri kaydedin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

Bu seçenek, bir program eşdeğerini yok.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
