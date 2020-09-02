---
title: /CETCOMPAT (CET gölge yığını uyumlu)
ms.date: 09/01/2020
f1_keywords:
- /CETCOMPAT
helpviewer_keywords:
- /CETCOMPAT linker option
- /CETCOMPAT
ms.openlocfilehash: 7de7c2007c29769cb3ac8f89d07de8b00bf44c26
ms.sourcegitcommit: e58918c45316d799c1952ca7797a85adbcd0c472
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2020
ms.locfileid: "89281840"
---
# <a name="cetcompat-cet-shadow-stack-compatible"></a>/CETCOMPAT (CET gölge yığını uyumlu)

Yürütülebilir bir görüntünün denetim akışı zorlama teknolojisi (CET) gölge yığınında uyumlu olarak işaretlenip işaretlenmeyeceğini belirtir.

## <a name="syntax"></a>Söz dizimi

> **`/CETCOMPAT`**\
> **`/CETCOMPAT:NO`**

## <a name="arguments"></a>Bağımsız değişkenler

**`NO`**<br/>
Yürütülebilir dosyanın CET gölge yığınında uyumlu olarak işaretlenmemesi gerektiğini belirtir.

## <a name="remarks"></a>Açıklamalar

Denetim akışı zorlama teknolojisi (CET) gölge yığını, return-yönelimli programlama (ROP) tabanlı kötü amaçlı yazılım saldırılarına karşı savunmaya yönelik yetenekler sağlayan bir bilgisayar işlemcisi özelliğidir. Daha fazla bilgi için bkz. [Intel Control-Flow zorlama teknolojisi önizlemesi](https://software.intel.com/sites/default/files/managed/4d/2a/control-flow-enforcement-technology-preview.pdf).

**`/CETCOMPAT`** Bağlayıcı seçeneği, bağlayıcının ikilisini CET Shadow Stack ile uyumlu olarak işaretlemesini söyler. **`/CETCOMPAT:NO`** ikiliyi, CET gölge yığını ile uyumlu değil olarak işaretler. Komut satırında her iki seçenek de belirtilirse, belirtilen son bir tane kullanılır. Bu anahtar şu anda yalnızca x86 ve x64 mimarileri için geçerlidir.

Bu **`/CETCOMPAT`** seçenek, Visual Studio 2019 ' den başlayarak kullanılabilir.

### <a name="to-set-the-cetcompat-linker-option-in-visual-studio"></a>`/CETCOMPAT`Visual Studio 'da bağlayıcı seçeneğini ayarlamak için

Visual Studio 2019 sürüm 16,7 ' den başlayarak:

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Proje özellikleriyle çalışma](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **Bağlayıcısı**  >  **Gelişmiş** özellik sayfasını seçin.

1. **CET gölge yığını uyumlu** özelliğini seçin.

1. Açılan denetimde, **`Yes (/CETCOMPAT)`** ikili dosyayı CET gölge yığını ile uyumlu olarak işaretlemeyi veya **`No (/CETCOMPAT:NO)`** uyumsuz olarak işaretleneceğini seçin.

Visual Studio 'nun önceki sürümlerinde 2019:

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Proje özellikleriyle çalışma](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** düzenleme denetiminde, *`/CETCOMPAT`* ikili dosyayı CET gölge yığını ile uyumlu olarak işaretlemek veya *`/CETCOMPAT:NO`* açıkça uyumlu değil olarak işaretlemek için ekleyin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

Bu seçeneğin programlı bir eşdeğeri yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı seçenekleri](linker-options.md)
