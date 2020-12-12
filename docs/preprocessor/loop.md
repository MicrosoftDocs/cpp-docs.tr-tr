---
description: 'Daha fazla bilgi edinin: Loop pragma'
title: döngü pragması
ms.date: 08/29/2019
f1_keywords:
- loop_CPP
- vc-pragma.loop
ms.assetid: 6d5bb428-cead-47e7-941d-7513bbb162c7
ms.openlocfilehash: b54d62a6c9a29a4688453992ad9647d9bc21afd1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167467"
---
# <a name="loop-pragma"></a>döngü pragması

Döngü kodunun otomatik paralelleştirme tarafından nasıl ele alınacağını denetler veya bir döngüyü otomatik Vektörleştirici tarafından göz önünde bulundurarak dışlar.

## <a name="syntax"></a>Syntax

> **#pragma döngüsü (hint_parallel (** *n* **))**\
> **#pragma döngüsü (no_vector)**\
> **#pragma döngüsü (ivdep)**

### <a name="parameters"></a>Parametreler

**hint_parallel (** *n* **)**\
Derleyiciye bu döngünün bir ipucu, n pozitif bir tamsayı değişmez değeri veya *sıfır olduğu,* *n* iş parçacığı genelinde paralelleştirilmesine sahip olması gerektiğini belirtir. *N* sıfırsa, çalışma zamanında en fazla iş parçacığı sayısı kullanılır. Bu bir komut değil derleyiciye yönelik bir ipucu. Döngünün paralelleştirilmesine garanti yoktur. Döngüde veri bağımlılıkları veya yapısal sorunlar varsa, bu, paralelleştirilmedi. Örneğin, döngü gövdesinin ötesinde kullanılan bir skaler öğesine depoluyorsa paralelleştirilmedi.

[/Qpar](../build/reference/qpar-auto-parallelizer.md) derleyici anahtarı belirtilmediği takdirde derleyici bu seçeneği yoksayar.

**no_vector**\
Varsayılan olarak, otomatik Vektörleştirici, değerlendirdiği tüm döngüleri vektörleştirmeye çalışır. Aşağıdaki döngü için otomatik Vektörleştirici devre dışı bırakmak üzere bu pragmayı belirtin.

**ivdep**\
Bu döngü için vektör bağımlılıklarını yoksaymak üzere derleyiciye ipucu.

## <a name="remarks"></a>Açıklamalar

**Loop** pragma ' ı kullanmak için, döngü tanımına değil, hemen öncesine yerleştirin. Pragma, onu takip eden döngü kapsamı için etkili olur. Bir döngüye herhangi bir sırada birden fazla pragma uygulayabilirsiniz, ancak her birini ayrı bir pragma deyimi içinde belirtmelisiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Otomatik paralelleştirme ve otomatik vektörleştirme](../parallel/auto-parallelization-and-auto-vectorization.md)\
[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
