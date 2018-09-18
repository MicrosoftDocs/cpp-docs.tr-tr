---
title: Bağlantı yok | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- no linkage
- linkage [C++], none
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: acbce1b4a4a19c5fa1a015e01bd2078fc70f6e1c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063092"
---
# <a name="no-linkage"></a>Bağlantı Yok

Bir blok içerisindeki tanımlayıcının bildirimi `extern` depolama sınıfı tanımlayıcısını içermiyorsa, tanımlayıcının bağlantısı yoktur ve tanımlayıcı işleve özgüdür.

Aşağıdaki tanımlayıcıların bağlantısı yoktur:

- Nesne veya işlev dışında bir şey olarak bildirilmiş tanımlayıcı

- Bir işlev parametresi olarak bildirilmiş bir tanımlayıcı

- `extern` depolama sınıfı tanımlayıcısı olmadan bildirilmiş bir nesneye yönelik blok kapsamı tanımlayıcısı

Tanımlayıcının hiçbir bağlantı yoksa, aynı kapsamda aynı adın yeniden bildirilmesi (bildirimcide veya tür tanımlayıcısında) simge yeniden tanımlama hatası oluşturur.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlantıyı Belirtmek için extern Kullanma](../cpp/using-extern-to-specify-linkage.md)