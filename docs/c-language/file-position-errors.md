---
title: "Dosya konumu hataları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- file pointers [C++], file position errors
ms.assetid: d5e59d8b-08c0-4927-a338-0b2d8234ce24
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fc55622f724a903c94fe49a935b906d2826297ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="file-position-errors"></a>Dosya Konumu Hataları
**ANSI 4.9.9.1, 4.9.9.4** olan değer makrosu `errno` tarafından belirlenen `fgetpos` veya `ftell` hatasında işlevi  
  
 Zaman `fgetpos` veya `ftell` başarısız olursa `errno` Bildirim sabiti ayarlanır `EINVAL` konumu geçersizse veya dosya numarası hatalı ise EBADF. Sabitler ERRNO içinde tanımlanmıştır. H.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kitaplık İşlevleri](../c-language/library-functions.md)