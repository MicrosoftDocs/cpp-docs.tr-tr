---
title: Dosya Konumu Hataları
ms.date: 11/04/2016
helpviewer_keywords:
- file pointers [C++], file position errors
ms.assetid: d5e59d8b-08c0-4927-a338-0b2d8234ce24
ms.openlocfilehash: 3d581d86d6f08eee564feb6373a623512085ccca
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56147808"
---
# <a name="file-position-errors"></a>Dosya Konumu Hataları

**ANSI 4.9.9.1, 4.9.9.4** değerine makro `errno` tarafından ayarlanır `fgetpos` veya `ftell` hatasında işlevi

Zaman `fgetpos` veya `ftell` başarısız olursa `errno` Bildirim sabiti için ayarlanmış `EINVAL` konumu geçersiz olduğunda veya `EBADF` hatalı dosya numarası ise. Sabitler ERRNO içinde tanımlanır. H

## <a name="see-also"></a>Ayrıca bkz.

[Kitaplık İşlevleri](../c-language/library-functions.md)
