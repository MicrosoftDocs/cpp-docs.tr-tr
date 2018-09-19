---
title: Dosya konumu hataları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- file pointers [C++], file position errors
ms.assetid: d5e59d8b-08c0-4927-a338-0b2d8234ce24
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8def11317548bfd6e70badab4563891c1b6f864d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031929"
---
# <a name="file-position-errors"></a>Dosya Konumu Hataları

**ANSI 4.9.9.1, 4.9.9.4** değerine makro `errno` tarafından ayarlanır `fgetpos` veya `ftell` hatasında işlevi

Zaman `fgetpos` veya `ftell` başarısız olursa `errno` Bildirim sabiti için ayarlanmış `EINVAL` konumu geçersiz olduğunda veya `EBADF` hatalı dosya numarası ise. Sabitler ERRNO içinde tanımlanır. H

## <a name="see-also"></a>Ayrıca Bkz.

[Kitaplık İşlevleri](../c-language/library-functions.md)
