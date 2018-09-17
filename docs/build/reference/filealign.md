---
title: / FILEALIGN (dosyalardaki bölümleri Hizala) | Microsoft Docs
ms.date: 10/23/2017
ms.technology:
- cpp-tools
ms.topic: reference
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
ms.workload:
- cplusplus
ms.openlocfilehash: 630fe7014c87487a9b4df61de60ac8f5518593e0
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720024"
---
# <a name="filealign-align-sections-in-files"></a>/ FILEALIGN (dosyalardaki bölümleri Hizala)

**/Filealign** bağlayıcı seçeneği çıkış dosyanızı yazılmış bir belirtilen boyutunun bir katı bölümlerde hizalamasını belirtmenize olanak sağlar.

## <a name="syntax"></a>Sözdizimi

> __/ FILEALIGN:__*boyutu*

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
Bölüm hizalama ikinin üssü olmalıdır bayt cinsinden boyutu.

## <a name="remarks"></a>Açıklamalar

**/Filealign** seçeneği neden olur, çıkış dosyası katları olan bir sınır üzerinde her bölümde hizalamak bağlayıcı *boyutu* değeri. Varsayılan olarak bağlayıcı bir sabit hizalama boyutu kullanmaz.

**/Filealign** seçeneği, disk kullanımını daha verimli hale getirmek için kullanılabilir veya daha hızlı diskten yükler sayfa. Daha küçük bir bölümü boyutu daha küçük ya da daha küçük indirmeler tutmak için çalışan uygulamalar için yararlı olabilir. Bölüm hizalama disk üzerinde bellek hizalama etkilemez.

Kullanım [DUMPBIN](dumpbin-reference.md) , çıkış dosyası bölümleri hakkında bilgi için.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **komut satırı** özellik sayfasında **bağlayıcı** klasör.

1. Seçenek adı **/filealign:** ve boyut **ek seçenekler** kutusu.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)