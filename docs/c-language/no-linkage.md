---
title: Bağlantı Yok
ms.date: 11/04/2016
helpviewer_keywords:
- no linkage
- linkage [C++], none
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
ms.openlocfilehash: c80cb814145ac986864fe351e664d8472f3bf880
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62232395"
---
# <a name="no-linkage"></a>Bağlantı Yok

Bir blok içerisindeki tanımlayıcının bildirimi `extern` depolama sınıfı tanımlayıcısını içermiyorsa, tanımlayıcının bağlantısı yoktur ve tanımlayıcı işleve özgüdür.

Aşağıdaki tanımlayıcıların bağlantısı yoktur:

- Nesne veya işlev dışında bir şey olarak bildirilmiş tanımlayıcı

- Bir işlev parametresi olarak bildirilmiş bir tanımlayıcı

- `extern` depolama sınıfı tanımlayıcısı olmadan bildirilmiş bir nesneye yönelik blok kapsamı tanımlayıcısı

Tanımlayıcının hiçbir bağlantı yoksa, aynı kapsamda aynı adın yeniden bildirilmesi (bildirimcide veya tür tanımlayıcısında) simge yeniden tanımlama hatası oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlantıyı Belirtmek için extern Kullanma](../cpp/using-extern-to-specify-linkage.md)
