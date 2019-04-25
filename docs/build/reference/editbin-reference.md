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
ms.openlocfilehash: 45c2967a55e85ae31bb77bb2e8d50415eafbea46
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293036"
---
# <a name="editbin-reference"></a>EDITBIN Başvurusu

Microsoft COFF ikili dosya Düzenleyicisi'ni (EDITBIN. Exe dosyası) ikili dosyaları ortak nesne dosyası biçimi (COFF) değiştirir. Nesne dosyaları, yürütülebilir dosyalar ve dinamik bağlantı kitaplıklarını (DLL) değiştirileceğini EDITBIN kullanabilirsiniz.

> [!NOTE]
>  Bu araç yalnızca Visual Studio komut isteminden başlatabilirsiniz. Bir sistem komut satırından veya dosya Gezgini'nden başlatılamıyor.

EDITBIN ile üretilen dosyaları kullanmak için erişilebilir değil [/GL](gl-whole-program-optimization.md) derleyici seçeneği. /GL ile üretilen ikili dosyalara yapılan tüm değişiklikler, yeniden derlemeden ve bağlama elde gerekecektir.

- [EDITBIN komut satırı](editbin-command-line.md)

- [EDITBIN seçenekleri](editbin-options.md)

## <a name="see-also"></a>Ayrıca bkz.

[Ek MSVC derleme araçları](c-cpp-build-tools.md)
