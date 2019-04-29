---
title: Adres Deposu
ms.date: 11/04/2016
helpviewer_keywords:
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
ms.openlocfilehash: 47b09ab6cd0b2045206daaee4badad32858ff934
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336198"
---
# <a name="storage-of-addresses"></a>Adres Deposu

Adres ve adresin anlamı için gereken depolama alanı miktarı, derleyicinin uygulamasına bağlıdır. Farklı türlerden işaretçilerin aynı uzunluğa sahip olacağı garanti edilmez. Bu nedenle, **sizeof (char \*)** eşit değil **sizeof (int \*)**.

**Microsoft'a özgü**

Microsoft C derleyicisi için **sizeof (char \*)** eşittir **sizeof (int \*)**.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[İşaretçi Bildirimleri](../c-language/pointer-declarations.md)
