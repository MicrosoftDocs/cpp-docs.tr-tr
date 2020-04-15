---
title: /SOURCELINK (Sourcelink dosyasını PDB’ye dahil et)
description: Microsoft C++'daki /SOURCELINK bağlayıcı seçeneğine başvuru kılavuzu.
ms.date: 03/31/2020
f1_keywords:
- /sourcelink
helpviewer_keywords:
- /SOURCELINK linker option
- /SOURCELINK
ms.openlocfilehash: bde55c401e17f7b3c84ffcdad29dda2badcc260b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336064"
---
# <a name="sourcelink-include-source-link-file-in-pdb"></a>/SOURCELINK (PDB'ye Kaynak Bağlantı dosyalarını dahil et)

Bağlayıcı tarafından oluşturulan PDB dosyasına dahil etmek üzere bir Kaynak Bağlantısı yapılandırma dosyası belirtir.

## <a name="syntax"></a>Sözdizimi

> **`/SOURCELINK:`**_`filename`_

## <a name="arguments"></a>Bağımsız Değişkenler

*filename*<br/>
Kaynak dosyaların hata ayıklamada görüntülenmesi için URL'lere yerel dosya yollarının basit bir eşleşmesini içeren JSON biçimli bir yapılandırma dosyasi belirtir. Bu dosyanın biçimi hakkında daha fazla bilgi için [Kaynak Bağlantı JSON Schema'ya](https://github.com/dotnet/designs/blob/master/accepted/2020/diagnostics/source-link.md#source-link-json-schema)bakın.

## <a name="remarks"></a>Açıklamalar

Kaynak Bağlantı, ikili ler için kaynak hata ayıklama sağlamak için bir dil ve kaynak denetimi agnostik sistemidir. Source Link, Visual Studio 2017 sürüm 15.8'den başlayarak yerel C++ ikilileri için desteklenir. Kaynak Bağlantı'ya genel bir bakış için [Kaynak Bağlantı'ya](https://github.com/dotnet/designs/blob/master/accepted/2020/diagnostics/source-link.md)bakın. Projelerinizde Kaynak Bağlantı'nın nasıl kullanılacağı ve projenizin bir parçası olarak SourceLink dosyasının nasıl oluşturacağı hakkında bilgi için [Kaynak Bağlantısını Kullanma](https://github.com/dotnet/sourcelink#using-source-link-in-c-projects)bölümüne bakın.

### <a name="to-set-the-sourcelink-linker-option-in-visual-studio"></a>Visual Studio'da /SOURCELINK bağlantı seçeneğini ayarlamak için

1. Proje için **Özellik Sayfaları** iletişim kutusunu açın. Daha fazla bilgi için [Bkz. C++ derleyicisi ayarlanın ve Visual Studio'da özellikler oluşturun.](../working-with-project-properties.md)

1. Yapılandırma **Özellikleri** > **Bağlayıcı** > **Komut Satırı** özellik sayfasını seçin.

1. Ek **seçenekler** kutusunda, **`/SOURCELINK:`** _`filename`_ değişikliklerinizi kaydetmek için **Tamam** veya **Uygula'yı** ekleyin ve sonra seçin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bu seçeneğin programeşdeğeri yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
