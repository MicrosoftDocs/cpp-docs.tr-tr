---
description: pragmaMicrosoft C/C++ ' da inline_recursion yönergesi hakkında daha fazla bilgi edinin
title: inline_recursion pragma
ms.date: 01/22/2021
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
helpviewer_keywords:
- pragma, inline_recursion
- inline_recursion pragma
no-loc:
- pragma
ms.openlocfilehash: b4e377d4c97c46a20e44a2c41f872a8762cdea4d
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713564"
---
# <a name="inline_recursion-no-locpragma"></a>`inline_recursion` pragma

Doğrudan veya birbirini dışlayan özyinelemeli işlev çağrılarının satır içi genişletmesini denetler.

## <a name="syntax"></a>Syntax

> **`#pragma inline_recursion(`** [ { **`on`** | **`off`** } ] **`)`**

## <a name="remarks"></a>Açıklamalar

pragmaOlarak işaretlenen işlevleri [`inline`](../cpp/inline-functions-cpp.md) ve [`__inline`](../cpp/inline-functions-cpp.md) ya da derleyicinin seçenek altında otomatik olarak genişledikleri işlevleri denetlemek için bunu kullanın **`/Ob2`** . Bunun kullanımı, pragma [`/Ob`](../build/reference/ob-inline-function-expansion.md) 1 veya 2 olan bir derleyici seçenek ayarı gerektirir. İçin varsayılan durum **`inline_recursion`** Kapalı ' dır. Bu pragma , görünmeden sonra ilk işlev çağrısında etkili olur pragma ve işlevin tanımını etkilemez.

**`inline_recursion`** pragma Özyinelemeli işlevlerin nasıl genişletildiğini denetler. **`inline_recursion`** Kapalıysa ve bir satır içi işlev kendisini doğrudan ya da dolaylı olarak çağırırsa, işlev yalnızca bir kez genişletilir. Açık ise, **`inline_recursion`** işlev, ile ayarlanan değere ulaşıncaya kadar birden çok kez genişletilir, [`inline_depth`](../preprocessor/inline-depth.md) pragma `inline_depth` pragma ya da veya kapasite sınırı tarafından tanımlanan özyinelemeli işlevlerin varsayılan değeridir.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)\
[`inline_depth`](../preprocessor/inline-depth.md)\
[`/Ob` (Satır içi işlev genişletmesi)](../build/reference/ob-inline-function-expansion.md)
