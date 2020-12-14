---
description: 'Daha fazla bilgi edinin: EDITBIN Başvurusu'
title: EDITBIN Başvurusu
ms.date: 11/04/2016
f1_keywords:
- editbin
helpviewer_keywords:
- binary data, editing
- object files, modifying
- EDITBIN program
- COFF files, editing
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
ms.openlocfilehash: ad211ab85ac00cd716b7c3b8e381a9a448ea04ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201033"
---
# <a name="editbin-reference"></a>EDITBIN Başvurusu

Microsoft COFF Ikili dosya Düzenleyicisi (EDITBIN.EXE), ortak nesne dosyası biçimi (COFF) ikili dosyalarını değiştirir. Nesne dosyalarını, yürütülebilir dosyaları ve dinamik bağlantı kitaplıklarını (DLL) değiştirmek için EDITBIN kullanabilirsiniz.

> [!NOTE]
> Bu aracı yalnızca Visual Studio komut isteminden başlatabilirsiniz. Bunu bir sistem komut isteminden veya dosya Gezgini 'nden başlatamazsınız.

EDITBIN, [/GL](gl-whole-program-optimization.md) derleyici seçeneği ile oluşturulan dosyalarda kullanılabilir değildir. /GL ile üretilen ikili dosyalardaki değişikliklerin yeniden derlenmesi ve bağlanması ile elde edilmesi gerekir.

- [EDITBIN komut satırı](editbin-command-line.md)

- [EDITBIN seçenekleri](editbin-options.md)

## <a name="see-also"></a>Ayrıca bkz.

[Ek MSVC derleme araçları](c-cpp-build-tools.md)
