---
description: pragmaMicrosoft C/C++ ' da inline_depth yönergesi hakkında daha fazla bilgi edinin
title: inline_depth pragma
ms.date: 01/22/2021
f1_keywords:
- inline_depth_CPP
- vc-pragma.inline_depth
helpviewer_keywords:
- pragma, inline_depth
- inline_depth pragma
no-loc:
- pragma
ms.openlocfilehash: 6daffdbcb598304925675c15c955941eb8369d23
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713577"
---
# <a name="inline_depth-no-locpragma"></a>`inline_depth` pragma

Satır içi buluşsal arama derinliğini belirtir. Çağrı grafiğinde belirtilen değerden büyük bir derinlikte bulunan işlevler satır içine alınmadı.

## <a name="syntax"></a>Syntax

> **`#pragma inline_depth(`** [ *n* ] **`)`**

## <a name="remarks"></a>Açıklamalar

Bu, pragma [`inline`](../cpp/inline-functions-cpp.md) [`__inline`](../cpp/inline-functions-cpp.md) derleyici seçeneği altında ve olarak işaretlenen işlevlerin listesini denetler **`/Ob`** . Daha fazla bilgi için bkz. [ `/Ob` (satır içi işlev genişletmesi)](../build/reference/ob-inline-function-expansion.md).

*n* , 0 ile 255 arasında bir değer olabilir; burada 255, çağrı grafiğinde sınırsız derinliğe yol açabilir. 0 değeri satır içi genişletmeyi engeller. *N* belirtilmediğinde, varsayılan 254 değeri kullanılır.

, **`inline_depth`** pragma Bir dizi işlev çağrısının genişletilebilecek sayısını denetler. Örneğin, satır içi derinliğin 4 olduğunu varsayalım. B çağrısı, B ve sonra C 'yi çağırırsa, üç çağrının hepsi satır içi olarak genişletilir. Ancak, en yakın satır içi derinlik genişletmesi 2 ise, yalnızca A ve B genişletilir ve C bir işlev çağrısı olarak kalır.

Bunu kullanmak için pragma , **`/Ob`** derleyici seçeneğini 1 veya daha yüksek bir değere ayarlamanız gerekir. Bunu kullanan derinlik kümesi pragma , sonrasında ilk işlev çağrısında etkili olur pragma .

Satır içi derinlik, genişleme sırasında azaltılabilir ancak artmaz. Satır içi derinlik 6 ise ve genişletme sırasında Önişlemci, **`inline_depth`** pragma 8 değeriyle karşılaştığında, derinlik 6 kalır.

, **`inline_depth`** pragma İle işaretlenen işlevleri etkilemez **`__forceinline`** .

> [!NOTE]
> Özyinelemeli işlevler, satır içinde en fazla 16 çağrılık bir derinlikle değiştirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)\
[`inline_recursion`](../preprocessor/inline-recursion.md)
