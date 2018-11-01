---
title: Adres Deposu
ms.date: 11/04/2016
helpviewer_keywords:
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
ms.openlocfilehash: 2a0e218d4d34fa1482986ecccd7da8adba38086b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539379"
---
# <a name="storage-of-addresses"></a>Adres Deposu

Adres ve adresin anlamı için gereken depolama alanı miktarı, derleyicinin uygulamasına bağlıdır. Farklı türlerden işaretçilerin aynı uzunluğa sahip olacağı garanti edilmez. Bu nedenle, **sizeof (char \*)** eşit değil **sizeof (int \*)**.

**Microsoft'a özgü**

Microsoft C derleyicisi için **sizeof (char \*)** eşittir **sizeof (int \*)**.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[İşaretçi Bildirimleri](../c-language/pointer-declarations.md)