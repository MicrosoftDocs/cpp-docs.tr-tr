---
title: "/ FILEALIGN (dosyaları bölümlerdeki hizalama) | Microsoft Docs"
ms.date: 10/23/2017
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /filealign
dev_langs:
- C++
helpviewer_keywords:
- linker align sections
- /FILEALIGN linker option
- -FILEALIGN linker option
- FILEALIGN linker option
ms.assetid: c1017a35-8d71-4ad9-934b-a3e3ea037fa0
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 753f6c5fade4211654246aec19af60c60706d7ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="filealign-align-sections-in-files"></a>/ FILEALIGN (dosyaları bölümlerdeki hizalama)

**/Filealign** bağlayıcı seçeneği, çıktı dosyası için belirtilen boyut birden fazla yazılmış bölümleri hizalamasını belirtmenize olanak sağlar.

## <a name="syntax"></a>Sözdizimi

> __/ FILEALIGN:__*boyutu*

### <a name="parameters"></a>Parametreler

*boyutu*  
İki gücünü olmalıdır bayt bölüm hizalama boyutu.

## <a name="remarks"></a>Açıklamalar

**/Filealign** seçeneği neden olan bir sınır çıkış dosyasındaki her bölüm hizalamak bağlayıcı *boyutu* değeri. Varsayılan olarak, bağlayıcı sabit hizalama boyutu kullanmaz.

**/Filealign** seçeneği, disk kullanımı daha verimli hale getirmek için kullanılabilir veya daha hızlı diskten yükler sayfa olun. Daha küçük bir bölüm boyutu daha küçük cihazlarda ya da indirme daha küçük tutmak için çalışan uygulamalar için yararlı olabilir. Disk üzerindeki bölüm hizalama bellekte hizalama etkilemez.

Kullanım [DUMPBIN](dumpbin-reference.md) çıkış dosyanızdaki bölümler hakkındaki bilgileri görmek için.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **komut satırı** özellik sayfasında **bağlayıcı** klasör.

1. Seçenek adı yazın **/filealign:** ve boyutu **ek seçenekler** kutusu.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)