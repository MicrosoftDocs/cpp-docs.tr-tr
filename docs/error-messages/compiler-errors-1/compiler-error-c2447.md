---
title: Derleyici Hatası C2447 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2447
dev_langs:
- C++
helpviewer_keywords:
- C2447
ms.assetid: d1bd6e9a-ee42-4510-ae5e-6b0378f7b931
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9cc18c8e6ffb31de062957e16f6f3a6573379ee
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035142"
---
# <a name="compiler-error-c2447"></a>Derleyici Hatası C2447

' {': işlev üstbilgisi eksik (eski stil resmi liste?)

Derleyici, genel kapsamda beklenmedik bir açık ayraç ile karşılaştı. Çoğu durumda, bunun nedeni hatalı biçimlendirilmiş işlev üstbilgisi, yanlış yerleştirilmiş bir bildirim ya da boştaki bir noktalı virgüldür. Bu sorunu gidermek için, açık ayracın düzgün biçimlendirilmiş bir işlev üstbilgisini izlediğini ve kendinden önce bir bildirim veya boşta noktalı virgül gelmediğini doğrulayın.

Bu hata ayrıca eski stil C dili biçimsel bağımsız değişken listesi nedeniyle de meydana gelebilir. Bu sorunu gidermek için, bağımsız değişken listesini modern stili (parantez içine alınmış biçimi) kullanacak şekilde yeniden düzenleyin.

Aşağıdaki örnek, C2447 oluşturur:

```
// C2447.cpp
int c;
{}       // C2447
```