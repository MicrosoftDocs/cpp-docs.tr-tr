---
description: 'Hakkında daha fazla bilgi edinin: dosya konumu hataları'
title: Dosya Konumu Hataları
ms.date: 11/04/2016
helpviewer_keywords:
- file pointers [C++], file position errors
ms.assetid: d5e59d8b-08c0-4927-a338-0b2d8234ce24
ms.openlocfilehash: d29f8d86280427db915c016fea0fd80567913baf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196158"
---
# <a name="file-position-errors"></a>Dosya Konumu Hataları

**ANSI 4.9.9.1, 4.9.9.4** `errno` `fgetpos` Hata durumunda makronun veya işlevin ayarlandığı değer `ftell`

`fgetpos`Ya da `ftell` başarısız olduğunda, `errno` `EINVAL` konum geçersizse veya `EBADF` Dosya numarası bozuksa bildirim sabiti olarak ayarlanır. Sabitler ERRNO. H içinde tanımlanır.

## <a name="see-also"></a>Ayrıca bkz.

[Kitaplık Işlevleri](../c-language/library-functions.md)
