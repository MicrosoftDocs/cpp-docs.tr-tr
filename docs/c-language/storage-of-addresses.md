---
title: Adres deposu | Microsoft Docs
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
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bd82f6f5046cf910fbc871be37d4af5856796792
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="storage-of-addresses"></a>Adres Deposu
Adres ve adresin anlamı için gereken depolama alanı miktarı, derleyicinin uygulamasına bağlıdır. Farklı türlerden işaretçilerin aynı uzunluğa sahip olacağı garanti edilmez. Bu nedenle, **sizeof (char \*)** mutlaka eşit değil **sizeof (int \*)**.  
  
 **Microsoft özel**  
  
 Microsoft C derleyicisi için **sizeof (char \*)** eşittir **sizeof (int \*)**.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşaretçi Bildirimleri](../c-language/pointer-declarations.md)