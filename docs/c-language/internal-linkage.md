---
title: İç bağlantı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- internal linkage
- linkage [C++], internal
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 09b5a02b7892bff0233e37bbd63020a4d2904ec3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094214"
---
# <a name="internal-linkage"></a>İç Bağlantı

Bir nesne veya işlevi için bir dosya kapsam tanımlayıcısının bildirimi içeriyorsa *depolama sınıfı tanımlayıcısı* **statik**, tanımlayıcının iç bağlantısı vardır. Aksi takdirde, tanımlayıcının dış bağlantısı vardır. Bkz: [depolama sınıfları](../c-language/c-storage-classes.md) bir irdelemesi *depolama sınıfı tanımlayıcısı* bildirimlere.

Bir çeviri birimi içinde iç bağlantı içeren bir tanımlayıcının her örneği aynı tanımlayıcı veya işlevi gösterir. Dahili olarak bağlantılı tanımlayıcılar bir çeviri birimi için benzersizdir.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlantıyı Belirtmek için extern Kullanma](../cpp/using-extern-to-specify-linkage.md)