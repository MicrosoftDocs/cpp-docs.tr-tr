---
description: 'Daha fazla bilgi edinin: bağlantı yok'
title: Bağlantı Yok
ms.date: 11/04/2016
helpviewer_keywords:
- no linkage
- linkage [C++], none
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
ms.openlocfilehash: cf0e1ccbbea3b79bce66335e361f3c23162e6cb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243321"
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
