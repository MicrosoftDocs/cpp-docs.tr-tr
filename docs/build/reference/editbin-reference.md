---
title: EDITBIN başvurusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- editbin
dev_langs:
- C++
helpviewer_keywords:
- binary data, editing
- object files, modifying
- EDITBIN program
- COFF files, editing
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 809d1d4f25611b2310d651702f01e1e98888ad4a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699953"
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