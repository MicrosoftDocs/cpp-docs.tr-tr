---
title: / DEFAULTLIB (varsayılan kitaplığı belirt) | Microsoft Docs
ms.custom: ''
ms.date: 05/29/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.DefaultLibraries
- /defaultlib
dev_langs:
- C++
helpviewer_keywords:
- -DEFAULTLIB linker option
- DEFAULTLIB linker option
- /DEFAULTLIB linker option
- libraries, adding to list of
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9afcaa0e229ec34ba91b4d60a7a4fa9acec2d7e3
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34569787"
---
# <a name="defaultlib-specify-default-library"></a>/DEFAULTLIB (Varsayılan Kitaplığı Belirt)

Dış başvuruları çözümlemek için aramak için varsayılan bir kitaplığı belirtin.

## <a name="syntax"></a>Sözdizimi

> **/ DEFAULTLIB**:_kitaplığı_

### <a name="arguments"></a>Arguments

|Bağımsız Değişken|Açıklama|
|-|-|
*Kitaplığı*|Dış başvurular çözülürken aramak için bir kitaplık adı.

## <a name="remarks"></a>Açıklamalar

**/DEFAULTLIB** seçeneği ekler bir *Kitaplığı* bağlantı başvuruları çözülürken arar kitaplıkları listesi. İle belirtilen bir kitaplık **/DEFAULTLIB** açıkça belirtilen komut satırında ve varsayılan kitaplık .obj dosyaları adlı önce kitaplıkları sonra aranır.

Bağımsız değişkenler olmadan kullanıldığında [/NODEFAULTLIB (tüm varsayılan kitaplıkları yoksay)](../../build/reference/nodefaultlib-ignore-libraries.md) seçeneği tüm geçersiz kılmaları **/DEFAULTLIB**:*Kitaplığı* seçenekleri. **/NODEFAULTLIB**:*Kitaplığı* seçeneği geçersiz kılmaları **/DEFAULTLIB**:*Kitaplığı* zaman aynı *Kitaplığı*adı hem de belirtilir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projeyi açın **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. İçinde **ek seçenekler**, girin bir **/DEFAULTLIB**:*Kitaplığı* aramak her kitaplığın seçeneği. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)
- [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
