---
title: Bağlantı Yok
ms.date: 11/04/2016
helpviewer_keywords:
- no linkage
- linkage [C++], none
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
ms.openlocfilehash: a7c9a5b8f0ba92830500e55818093981a044d2df
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218812"
---
# <a name="no-linkage"></a>Bağlantı Yok

Bir blok içindeki tanımlayıcı için bir bildirim, **`extern`** depolama sınıfı belirticisini içermiyorsa, tanımlayıcının bağlantısı yoktur ve işlev için benzersizdir.

Aşağıdaki tanımlayıcıların bağlantısı yoktur:

- Nesne veya işlev dışında bir şey olarak bildirilmiş tanımlayıcı

- Bir işlev parametresi olarak bildirilmiş bir tanımlayıcı

- Depolama sınıfı tanımlayıcısı olmadan belirtilen bir nesne için blok kapsamı tanımlayıcısı **`extern`**

Tanımlayıcının hiçbir bağlantı yoksa, aynı kapsamda aynı adın yeniden bildirilmesi (bildirimcide veya tür tanımlayıcısında) simge yeniden tanımlama hatası oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlantıyı Belirtmek için extern Kullanma](../cpp/using-extern-to-specify-linkage.md)
