---
title: Bağlantı Yok
ms.date: 11/04/2016
helpviewer_keywords:
- no linkage
- linkage [C++], none
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
ms.openlocfilehash: 69ead5d12d6689370e9ae04a54d5f5a8db06eca5
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500750"
---
# <a name="no-linkage"></a>Bağlantı Yok

Bir blok içindeki tanımlayıcı için bir bildirim, **`extern`** depolama sınıfı belirticisini içermiyorsa, tanımlayıcının bağlantısı yoktur ve işlev için benzersizdir.

Aşağıdaki tanımlayıcıların bağlantısı yoktur:

- Nesne veya işlev dışında bir şey olarak bildirilmiş tanımlayıcı

- Bir işlev parametresi olarak bildirilmiş bir tanımlayıcı

- Depolama sınıfı tanımlayıcısı olmadan belirtilen bir nesne için blok kapsamı tanımlayıcısı **`extern`**

Tanımlayıcının hiçbir bağlantı yoksa, aynı kapsamda aynı adın yeniden bildirilmesi (bildirimcide veya tür tanımlayıcısında) simge yeniden tanımlama hatası oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlantıyı Belirtmek için extern Kullanma](../cpp/extern-cpp.md)
