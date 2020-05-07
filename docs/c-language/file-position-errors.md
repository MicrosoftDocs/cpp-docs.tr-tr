---
title: Dosya Konumu Hataları
ms.date: 11/04/2016
helpviewer_keywords:
- file pointers [C++], file position errors
ms.assetid: d5e59d8b-08c0-4927-a338-0b2d8234ce24
ms.openlocfilehash: 3d581d86d6f08eee564feb6373a623512085ccca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62233663"
---
# <a name="file-position-errors"></a>Dosya Konumu Hataları

**ANSI 4.9.9.1, 4.9.9.4** Hata durumunda makronun `errno` `fgetpos` veya `ftell` işlevin ayarlandığı değer

Ya `fgetpos` `ftell` da başarısız olduğunda `errno` , konum geçersizse veya `EINVAL` `EBADF` dosya numarası bozuksa bildirim sabiti olarak ayarlanır. Sabitler ERRNO içinde tanımlanmıştır. Olsun.

## <a name="see-also"></a>Ayrıca bkz.

[Kitaplık İşlevleri](../c-language/library-functions.md)
