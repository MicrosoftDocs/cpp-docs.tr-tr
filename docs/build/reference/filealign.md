---
description: Hakkında daha fazla bilgi edinin:/FILEALIGN (dosyalardaki bölümleri Hizala)
title: /FILEALIGN (Dosyalardaki bölümleri hizala)
ms.date: 10/23/2017
f1_keywords:
- /filealign
helpviewer_keywords:
- linker align sections
- /FILEALIGN linker option
- -FILEALIGN linker option
- FILEALIGN linker option
ms.assetid: c1017a35-8d71-4ad9-934b-a3e3ea037fa0
ms.openlocfilehash: a67cf682c8fe55b80b2253864e08919e08242f74
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192171"
---
# <a name="filealign-align-sections-in-files"></a>/FILEALIGN (Dosyalardaki bölümleri hizala)

**/Filealign** bağlayıcı seçeneği, çıktı dosyanıza yazılan bölümlerin hizalamasını belirtilen boyutun katı olarak belirtmenizi sağlar.

## <a name="syntax"></a>Syntax

> __/Filealign:__*size*

### <a name="parameters"></a>Parametreler

*boyutla*<br/>
İkinci bir üssü olması gereken bayt cinsinden Bölüm hizalama boyutu.

## <a name="remarks"></a>Açıklamalar

**/Filealign** seçeneği, bağlayıcının çıkış dosyasındaki her bölümü, *Boyut* değerinin birden çok katı olan bir sınırın hizalanmasına neden olur. Varsayılan olarak, bağlayıcı sabit bir hizalama boyutu kullanmaz.

**/Filealign** seçeneği, disk kullanımını daha verimli hale getirmek veya sayfa yükünü diskten daha hızlı hale getirmek için kullanılabilir. Daha küçük bir bölüm boyutu, daha küçük cihazlarda çalışan uygulamalar için veya İndirmeleri daha küçük tutmak için yararlı olabilir. Diskteki bölüm hizalaması, bellekteki hizalamayı etkilemez.

Çıkış dosyanızdaki bölümler hakkındaki bilgileri görmek için [dumpbin](dumpbin-reference.md) ' i kullanın.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasöründeki **komut satırı** özellik sayfasını seçin.

1. **/Filealign:** adını ve **ek seçenekler** kutusuna boyutu yazın.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
