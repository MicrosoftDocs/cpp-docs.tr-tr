---
title: /DEFAULTLIB (Varsayılan Kitaplığı Belirt)
ms.date: 05/29/2018
f1_keywords:
- VC.Project.VCLinkerTool.DefaultLibraries
- /defaultlib
helpviewer_keywords:
- -DEFAULTLIB linker option
- DEFAULTLIB linker option
- /DEFAULTLIB linker option
- libraries, adding to list of
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
ms.openlocfilehash: 0b7d4569c7be70bd97094ebbe09a7ae462331983
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293868"
---
# <a name="defaultlib-specify-default-library"></a>/DEFAULTLIB (Varsayılan Kitaplığı Belirt)

Bir varsayılan kitaplığı dış başvuruları çözümlemek için aranacak belirtin.

## <a name="syntax"></a>Sözdizimi

> **/ DEFAULTLIB**:_kitaplığı_

### <a name="arguments"></a>Arguments

*Kitaplık*<br/>
Dış başvurular çözümlediğinde aramak için bir kitaplık adı.

## <a name="remarks"></a>Açıklamalar

**/DEFAULTLIB** seçeneği bir ekler *Kitaplığı* listesine bağlantı başvuruların çözümlenmesi sırasında aradığı kitaplık. Belirtilen kitaplık **/DEFAULTLIB** açıkça belirtilen komut satırında ve adlı .obj dosyalarında varsayılan kitaplık önce kitaplıkları sonra aranır.

Bağımsız değişkenler olmadan kullanıldığında [/nodefaultlıb (tüm varsayılan kitaplıkları yoksay)](nodefaultlib-ignore-libraries.md) seçeneği tüm geçersiz kılmaları **/DEFAULTLIB**:*Kitaplığı* seçenekleri. **/Nodefaultlıb**:*Kitaplığı* seçeneği geçersiz kılmaları **/DEFAULTLIB**:*Kitaplığı* olduğunda aynı *Kitaplığı*adı hem de belirtilir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. İçinde **ek seçenekler**, girin bir **/DEFAULTLIB**:*Kitaplığı* aramak her bir kitaplık için seçenek. Seçin **Tamam** yaptığınız değişiklikleri kaydedin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC bağlayıcı başvurusu](linking.md)
- [MSVC Bağlayıcı Seçenekleri](linker-options.md)
