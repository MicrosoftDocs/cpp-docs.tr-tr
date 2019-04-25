---
title: / FILEALIGN (dosyalardaki bölümleri Hizala)
ms.date: 10/23/2017
f1_keywords:
- /filealign
helpviewer_keywords:
- linker align sections
- /FILEALIGN linker option
- -FILEALIGN linker option
- FILEALIGN linker option
ms.assetid: c1017a35-8d71-4ad9-934b-a3e3ea037fa0
ms.openlocfilehash: 43cfdd6efb163013d05877e91c8375eb592295a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271157"
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

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **komut satırı** özellik sayfasında **bağlayıcı** klasör.

1. Seçenek adı **/filealign:** ve boyut **ek seçenekler** kutusu.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
