---
title: / CETCOMPAT (CET gölge yığın ile uyumlu)
ms.date: 02/19/2019
f1_keywords:
- /CETCOMPAT
helpviewer_keywords:
- /CETCOMPAT linker option
- /CETCOMPAT
ms.openlocfilehash: 0ed5d9d4f9f4f4dc5cd4fc19df4179e86e430187
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273254"
---
# <a name="cetcompat-cet-shadow-stack-compatible"></a>/ CETCOMPAT (CET gölge yığın ile uyumlu)

Bir yürütülebilir görüntü denetim akışı zorlama teknolojisi (CET) gölge yığın ile uyumlu olarak işaretlemek belirtir.

## <a name="syntax"></a>Sözdizimi

> **/ CETCOMPAT**\[**: NO**]

## <a name="arguments"></a>Arguments

**YOK**<br/>
Yürütülebilir dosyayı CET gölge yığın ile uyumlu işaretli olmamalıdır olduğunu belirtir.

## <a name="remarks"></a>Açıklamalar

Denetim akışı zorlama teknolojisi (CET) gölge yığın, kötü amaçlı yazılım saldırılarını dönüş yönelimli programlama (KIRPMA) karşı korumaya yönelik özellikler sunar bir bilgisayar işlemci özelliktir. Daha fazla bilgi için [Intel denetim akışı zorlama Technology Preview](https://software.intel.com/sites/default/files/managed/4d/2a/control-flow-enforcement-technology-preview.pdf).

**/CETCOMPAT** bağlayıcı seçeneği bağlayıcıya ikili CET gölge yığın ile uyumlu olarak işaretlemek için. **/CETCOMPAT:No** ikili CET gölge yığın ile uyumlu değil olarak işaretler. Komut satırında iki seçenek de belirtilirse, belirtilen sonuncu kullanılır. Bu anahtar şu anda yalnızca x86 ve x64 mimarileri için geçerlidir.

**/CETCOMPAT** seçeneği olan Visual Studio 2019 Preview 3 araç takımında sonraki sürümlerinde kullanılabilir.

### <a name="to-set-the-cetcompat-linker-option-in-visual-studio"></a>Visual Studio'da /CETCOMPAT bağlayıcı seçeneğini ayarlamak için

1. Açık **özellik sayfaları** iletişim kutusu için proje. Daha fazla bilgi için [Working with Project Properties](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. İçinde **ek seçenekler** kutusunda **/CETCOMPAT** veya **/CETCOMPAT:NO** seçip **Tamam** veya **Uygula**yaptığınız değişiklikleri kaydedin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

Bu seçenek, bir program eşdeğerini yok.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Seçenekleri](linker-options.md)
