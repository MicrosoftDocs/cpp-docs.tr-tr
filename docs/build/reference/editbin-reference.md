---
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
ms.openlocfilehash: c2c0ee66ed1811755edc33b24737e057554fd01f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542915"
---
# <a name="editbin-reference"></a>EDITBIN Başvurusu

Microsoft COFF ikili dosya Düzenleyicisi'ni (EDITBIN. Exe dosyası) ikili dosyaları ortak nesne dosyası biçimi (COFF) değiştirir. Nesne dosyaları, yürütülebilir dosyalar ve dinamik bağlantı kitaplıklarını (DLL) değiştirileceğini EDITBIN kullanabilirsiniz.

> [!NOTE]
>  Bu araç yalnızca Visual Studio komut isteminden başlatabilirsiniz. Bir sistem komut satırından veya dosya Gezgini'nden başlatılamıyor.

EDITBIN ile üretilen dosyaları kullanmak için erişilebilir değil [/GL](../../build/reference/gl-whole-program-optimization.md) derleyici seçeneği. /GL ile üretilen ikili dosyalara yapılan tüm değişiklikler, yeniden derlemeden ve bağlama elde gerekecektir.

- [EDITBIN komut satırı](../../build/reference/editbin-command-line.md)

- [EDITBIN seçenekleri](../../build/reference/editbin-options.md)

## <a name="see-also"></a>Ayrıca Bkz.

[C/C++ Derleme Araçları](../../build/reference/c-cpp-build-tools.md)