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
ms.openlocfilehash: 71c059939891680b638e8644f7902d54452f5332
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="file-position-errors"></a>Dosya Konumu Hataları
**ANSI 4.9.9.1, 4.9.9.4** olan değer makrosu `errno` tarafından belirlenen `fgetpos` veya `ftell` hatasında işlevi  
  
 Zaman `fgetpos` veya `ftell` başarısız olursa `errno` Bildirim sabiti ayarlanır `EINVAL` konumu geçersizse veya `EBADF` dosya numarası hatalı olması durumunda. Sabitler ERRNO içinde tanımlanmıştır. H.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kitaplık İşlevleri](../c-language/library-functions.md)
