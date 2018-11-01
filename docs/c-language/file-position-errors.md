---
title: Dosya Konumu Hataları
ms.date: 11/04/2016
helpviewer_keywords:
- file pointers [C++], file position errors
ms.assetid: d5e59d8b-08c0-4927-a338-0b2d8234ce24
ms.openlocfilehash: f8c1d5dfc6a599533ce8c1dcfa624d2595779f2b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554615"
---
# <a name="file-position-errors"></a>Dosya Konumu Hataları

**ANSI 4.9.9.1, 4.9.9.4** değerine makro `errno` tarafından ayarlanır `fgetpos` veya `ftell` hatasında işlevi

Zaman `fgetpos` veya `ftell` başarısız olursa `errno` Bildirim sabiti için ayarlanmış `EINVAL` konumu geçersiz olduğunda veya `EBADF` hatalı dosya numarası ise. Sabitler ERRNO içinde tanımlanır. H

## <a name="see-also"></a>Ayrıca Bkz.

[Kitaplık İşlevleri](../c-language/library-functions.md)
