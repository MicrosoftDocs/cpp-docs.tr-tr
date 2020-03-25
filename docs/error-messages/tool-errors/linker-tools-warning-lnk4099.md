---
title: Bağlayıcı Araçları Uyarısı LNK4099
ms.date: 11/04/2016
f1_keywords:
- LNK4099
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
ms.openlocfilehash: b1f330924b8e47e0649268142106a050c83cb20a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183325"
---
# <a name="linker-tools-warning-lnk4099"></a>Bağlayıcı Araçları Uyarısı LNK4099

PDB ' filename ', ' Object/Library ' veya ' Path ' üzerinde bulunamadı; nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor

Bağlayıcı,. pdb dosyanızı bulamadı. `object/library`içeren dizine kopyalayın.

Nesne dosyasıyla ilişkili. pdb dosyasının adını bulmak için:

1. Kitaplıktan bir nesne dosyasını [LIB](../../build/reference/lib-reference.md) **/Extract:** `objectname` **. obj** `xyz` **. lib**ile ayıklayın.

1. . Pdb dosyasının yolunu **dumpbin/Section:. Debug $ T/rawData** `objectname` **. obj**ile denetleyin.

Ayrıca, [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)ile derleyebilir, bu nedenle pdb kullanılması gerekmez veya bağlanmakta olduğunuz nesneler için. pdb dosyalarınız yoksa [/Debug](../../build/reference/debug-generate-debug-info.md) bağlayıcı seçeneğini kaldırın.
