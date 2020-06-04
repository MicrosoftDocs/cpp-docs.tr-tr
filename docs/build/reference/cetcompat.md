---
title: /CETCOMPAT (CET gölge yığını uyumlu)
ms.date: 02/19/2019
f1_keywords:
- /CETCOMPAT
helpviewer_keywords:
- /CETCOMPAT linker option
- /CETCOMPAT
ms.openlocfilehash: 2c807d91d69b967fd62e01a077711dede5f55c44
ms.sourcegitcommit: 7e011c68ca7547469544fac87001a33a37e1792e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84421309"
---
# <a name="cetcompat-cet-shadow-stack-compatible"></a>/CETCOMPAT (CET gölge yığını uyumlu)

Yürütülebilir bir görüntünün denetim akışı zorlama teknolojisi (CET) gölge yığınında uyumlu olarak işaretlenip işaretlenmeyeceğini belirtir.

## <a name="syntax"></a>Sözdizimi

> **/Cetcompat** \[ **: Hayır**]

## <a name="arguments"></a>Arguments

**EŞLEŞEN**<br/>
Yürütülebilir dosyanın CET gölge yığınında uyumlu olarak işaretlenmemiş olması gerektiğini belirtir.

## <a name="remarks"></a>Açıklamalar

Denetim akışı zorlama teknolojisi (CET) gölge yığını, return odaklı programlama (ROP) tabanlı kötü amaçlı yazılım saldırılarına karşı savunmaya yönelik yetenekler sağlayan bir bilgisayar işlemcisi özelliğidir. Daha fazla bilgi için bkz. [Intel Control-Flow zorlama teknolojisi önizlemesi](https://software.intel.com/sites/default/files/managed/4d/2a/control-flow-enforcement-technology-preview.pdf).

**/Cetcompat** bağlayıcı seçeneği, bağlayıcının IKILISINI CET Shadow Stack ile uyumlu olarak işaretlemesini söyler. **/Cetcompat: Hayır** , ikili dosyasını CET gölge yığını ile uyumlu değil olarak işaretler. Komut satırında her iki seçenek de belirtilirse, belirtilen son bir tane kullanılır. Bu anahtar şu anda yalnızca x86 ve x64 mimarileri için geçerlidir.

**/Cetcompat** seçeneği, Visual Studio 2019 Preview 3 araç takımının başlangıcında bulunur.

### <a name="to-set-the-cetcompat-linker-option-in-visual-studio"></a>Visual Studio 'da/CETCOMPAT bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Proje özellikleriyle çalışma](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **Bağlayıcısı**  >  **Gelişmiş** özellik sayfasını seçin.

1. **CET gölge yığını uyumlu** özelliğini seçin.

1. Aşağı açılan denetimde, EH ' ı etkinleştirmek için **Evet (/cetcompat)** veya devre dışı bırakmak için **Hayır (/cetcompat: No)** seçeneğini belirleyin.


### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

Bu seçeneğin programlı bir eşdeğeri yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Seçenekleri](linker-options.md)
