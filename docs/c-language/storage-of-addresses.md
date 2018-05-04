---
title: Adres deposu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d892aac81efa8c2628c8662558b52cc1eb2e21c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="storage-of-addresses"></a>Adres Deposu
Adres ve adresin anlamı için gereken depolama alanı miktarı, derleyicinin uygulamasına bağlıdır. Farklı türlerden işaretçilerin aynı uzunluğa sahip olacağı garanti edilmez. Bu nedenle, **sizeof (char \*)** mutlaka eşit değil **sizeof (int \*)**.  
  
 **Microsoft özel**  
  
 Microsoft C derleyicisi için **sizeof (char \*)** eşittir **sizeof (int \*)**.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşaretçi Bildirimleri](../c-language/pointer-declarations.md)