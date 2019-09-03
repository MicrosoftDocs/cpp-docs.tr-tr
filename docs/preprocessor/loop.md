---
title: döngü pragması
ms.date: 08/29/2019
f1_keywords:
- loop_CPP
- vc-pragma.loop
ms.assetid: 6d5bb428-cead-47e7-941d-7513bbb162c7
ms.openlocfilehash: 013540ffe120f42c15538ce86661753b9cf9416f
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220854"
---
# <a name="loop-pragma"></a>döngü pragması

Döngü kodunun otomatik paralelleştirme tarafından nasıl ele alınacağını denetler veya bir döngüyü otomatik Vektörleştirici tarafından göz önünde bulundurarak dışlar.

## <a name="syntax"></a>Sözdizimi

> **#pragma döngüsü (hint_parallel (** *n* **))** \
> **#pragma döngüsü (no_vector)** \
> **#pragma döngüsü (ivdep)**

### <a name="parameters"></a>Parametreler

**hint_parallel (** *n* **)** \
Derleyiciye bu döngünün bir ipucu, n pozitif bir tamsayı değişmez değeri veya sıfır olduğu, *n* iş parçacığı genelinde paralelleştirilmesine sahip olması gerektiğini belirtir. *N* sıfırsa, çalışma zamanında en fazla iş parçacığı sayısı kullanılır. Bu bir komut değil derleyiciye yönelik bir ipucu. Döngünün paralelleştirilmesine garanti yoktur. Döngüde veri bağımlılıkları veya yapısal sorunlar varsa, bu, paralelleştirilmedi. Örneğin, döngü gövdesinin ötesinde kullanılan bir skaler öğesine depoluyorsa paralelleştirilmedi.

[/Qpar](../build/reference/qpar-auto-parallelizer.md) derleyici anahtarı belirtilmediği takdirde derleyici bu seçeneği yoksayar.

**no_vector**\
Varsayılan olarak, otomatik Vektörleştirici, değerlendirdiği tüm döngüleri vektörleştirmeye çalışır. Aşağıdaki döngü için otomatik Vektörleştirici devre dışı bırakmak üzere bu pragmayı belirtin.

**ivdep**\
Bu döngü için vektör bağımlılıklarını yoksaymak üzere derleyiciye ipucu. Bu seçeneği **hint_parallel**ile birlikte kullanın.

## <a name="remarks"></a>Açıklamalar

**Loop** pragma ' ı kullanmak için, döngü tanımına değil, hemen öncesine yerleştirin. Pragma, onu takip eden döngü kapsamı için etkili olur. Bir döngüye herhangi bir sırada birden fazla pragma uygulayabilirsiniz, ancak her birini ayrı bir pragma deyimi içinde belirtmelisiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Otomatik paralelleştirme ve otomatik vektörleştirme](../parallel/auto-parallelization-and-auto-vectorization.md)\
[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
