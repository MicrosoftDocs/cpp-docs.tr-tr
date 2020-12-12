---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları uyarısı LNK4099'
title: Bağlayıcı Araçları Uyarısı LNK4099
ms.date: 11/04/2016
f1_keywords:
- LNK4099
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
ms.openlocfilehash: 1e063cce9c884b8952e4bd5807b0d4a7683d4d54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133776"
---
# <a name="linker-tools-warning-lnk4099"></a>Bağlayıcı Araçları Uyarısı LNK4099

PDB ' filename ', ' Object/Library ' veya ' Path ' üzerinde bulunamadı; nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor

Bağlayıcı,. pdb dosyanızı bulamadı. Bunu içeren dizine kopyalayın `object/library` .

Nesne dosyasıyla ilişkili. pdb dosyasının adını bulmak için:

1. Kitaplıktan bir nesne dosyasını [LIB](../../build/reference/lib-reference.md) **/Extract:** `objectname` **. obj** `xyz` **. lib** ile ayıklayın.

1. . Pdb dosyasının yolunu **dumpbin/Section:. Debug $ T/rawData** `objectname` **. obj** ile denetleyin.

Ayrıca, [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)ile derleyebilir, bu nedenle pdb kullanılması gerekmez veya bağlanmakta olduğunuz nesneler için. pdb dosyalarınız yoksa [/Debug](../../build/reference/debug-generate-debug-info.md) bağlayıcı seçeneğini kaldırın.
