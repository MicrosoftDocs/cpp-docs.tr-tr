---
title: /NATVIS (PDB’ye Natvis ekle)
ms.date: 08/10/2017
f1_keywords:
- /natvis
helpviewer_keywords:
- NATVIS linker option
- /NATVIS linker option
- -NATVIS linker option
- Add Natvis file to PDB
ms.assetid: 8747fc0c-701a-4796-bb4d-818ab4465cca
ms.openlocfilehash: a16e320a2f8f946912fef6a354f27f6514a67e29
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439281"
---
# <a name="natvis-add-natvis-to-pdb"></a>/NATVIS (PDB’ye Natvis ekle)

> /NATVIS:*dosya adı*

## <a name="parameters"></a>Parametreler

*kısaltın*<br/>
PDB dosyasına eklenecek natvis dosyası. Natvis dosyasındaki hata ayıklayıcı görselleştirmelerini PDB 'ye katıştırır.

## <a name="remarks"></a>Açıklamalar

/NATVIS seçeneği, Natvis dosya *dosya adında* tanımlanan hata ayıklayıcı GÖRSELLEŞTIRMELERINI bağlantı tarafından oluşturulan pdb dosyasına katıştırır. Bu, hata ayıklayıcının görselleştirmeleri. natvis dosyasından bağımsız olarak görüntülemesini sağlar. Birden çok/NATVIS seçeneğini, oluşturulan PDB dosyasına birden fazla natvis dosyası eklemek için kullanabilirsiniz.

Bir PDB dosyası [/Debug](debug-generate-debug-info.md) seçeneği kullanılarak OLUŞTURULMADıYSA bağlantı/Natvis 'yi yoksayar. . Natvis dosyalarını oluşturma ve kullanma hakkında bilgi için bkz. [Visual Studio hata ayıklayıcıda yerel nesnelerin özel görünümlerini oluşturma](/visualstudio/debugger/create-custom-views-of-native-objects).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasöründeki **komut satırı** özellik sayfasını seçin.

1. /NATVIS seçeneğini **ek seçenekler** metin kutusuna ekleyin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bu seçeneğin programlı bir eşdeğeri yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
