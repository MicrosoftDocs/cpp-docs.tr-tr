---
description: pragmaMicrosoft C/C++ ' da döngü yönergesi hakkında daha fazla bilgi edinin
title: gerçekleştirmek pragma
ms.date: 01/22/2021
f1_keywords:
- loop_CPP
- vc-pragma.loop
helpviewer_keywords:
- loop pragma
- pragma, loop
no-loc:
- pragma
ms.openlocfilehash: 4aac76cb5220e57dd378ac00ff576521c9001218
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713538"
---
# <a name="loop-no-locpragma"></a>`loop` pragma

Döngü kodunun otomatik paralelleştirme tarafından nasıl ele alınacağını denetler veya bir döngüyü otomatik Vektörleştirici tarafından göz önünde bulundurarak dışlar.

## <a name="syntax"></a>Syntax

> **`#pragma loop( hint_parallel(`***n***`) )`**\
> **`#pragma loop( no_vector )`**\
> **`#pragma loop( ivdep )`**

### <a name="parameters"></a>Parametreler

**`hint_parallel(`***n***`)`**\
Derleyiciye bu döngünün bir ipucu, n pozitif bir tamsayı değişmez değeri veya *sıfır olduğu,* *n* iş parçacığı genelinde paralelleştirilmesine sahip olması gerektiğini belirtir. *N* sıfırsa, çalışma zamanında en fazla iş parçacığı sayısı kullanılır. Bu bir komut değil derleyiciye yönelik bir ipucu. Döngünün paralelleştirilmesine garanti yoktur. Döngüde veri bağımlılıkları veya yapısal sorunlar varsa, bu, paralelleştirilmedi. Örneğin, döngü gövdesinin ötesinde kullanılan bir skaler öğesine depoluyorsa paralelleştirilmedi.

Derleyici anahtarı belirtilmediği takdirde derleyici bu seçeneği yoksayar [`/Qpar`](../build/reference/qpar-auto-parallelizer.md) .

**`no_vector`**\
Varsayılan olarak, otomatik Vektörleştirici, değerlendirdiği tüm döngüleri vektörleştirmeye çalışır. pragmaAşağıdaki döngü için otomatik Vektörleştirici devre dışı bırakmak üzere bunu belirtin.

**`ivdep`**\
Bu döngü için vektör bağımlılıklarını yoksaymak üzere derleyiciye ipucu.

## <a name="remarks"></a>Açıklamalar

Öğesini kullanmak için, **`loop`** pragma bir döngü tanımına değil, hemen öncesine yerleştirin. , pragma İzleyen döngünün kapsamı için geçerli olur. pragmaHerhangi bir sırada bir döngüye birden çok yönergeler uygulayabilirsiniz, ancak her birini ayrı bir pragma bildirimde belirtmelisiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Otomatik paralelleştirme ve otomatik vektörleştirme](../parallel/auto-parallelization-and-auto-vectorization.md)\
[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
