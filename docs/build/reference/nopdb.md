---
title: /NOPDB
description: /NOPDB seçeneği, DUMPBIN 'in sembol bilgileri için PDB dosyalarını yüklemesini ve aramasını önler.
ms.date: 12/04/2019
f1_keywords:
- /NOPDB
helpviewer_keywords:
- /NOPDB dumpbin option
- /NOPDB
ms.openlocfilehash: 7b0c01e59b52bcec6ddf09416dd6aac9999527a6
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856975"
---
# <a name="nopdb"></a>/NOPDB

DUMPBIN 'in sembol bilgileri için program veritabanı (PDB) dosyalarını yükleyip araymayacağını söyler.

## <a name="syntax"></a>Sözdizimi

> **/NOPDB**

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, DUMPBIN hedef yürütülebilir dosyaları için PDB dosyalarını yüklemeye çalışır. DUMPBIN, bu bilgileri simge adlarıyla eşleştirmek için kullanır. PDB dosyaları büyükse işlem zaman alabilir veya uzak bir sunucudan yüklenmesi gerekir. **/Nopdb** SEÇENEĞI, dumpbin 'i bu adımı atlayacak şekilde söyler. Yalnızca yürütülebilir dosyada bulunan adresleri ve sembol bilgilerini yazdırır.

### <a name="to-set-the-nopdb-linker-option-in-visual-studio"></a>Visual Studio 'da/NOPDB bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz [. C++ Visual Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** kutusuna **/nopdb** seçeneğini ekleyin. Değişikliklerinizi kaydetmek için **Tamam ' ı** veya **Uygula** ' yı seçin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bu seçeneğin programlı bir eşdeğeri yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[Dumpbin komut satırı](dumpbin-command-line.md)\
[Dumpbin seçenekleri](dumpbin-options.md)\
[DUMPBIN başvurusu](dumpbin-reference.md)
