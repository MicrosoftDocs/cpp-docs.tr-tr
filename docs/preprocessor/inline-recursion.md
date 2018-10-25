---
title: inline_recursion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
dev_langs:
- C++
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a51428d32c1e7e5863e777302c3c55b728ce11f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083067"
---
# <a name="inlinerecursion"></a>inline_recursion
Doğrudan veya karşılıklı özyinelemeli işlev çağrıları satır içi genişlemeyi denetler.

## <a name="syntax"></a>Sözdizimi

```
#pragma inline_recursion( [{on | off}] )
```

## <a name="remarks"></a>Açıklamalar

Olarak işaretlenmiş denetim işlevleri bu pragmayı kullanmak [satır içi](../cpp/inline-functions-cpp.md) ve [__inline](../cpp/inline-functions-cpp.md) veya derleyici altında otomatik olarak genişleyen işlevleri `/Ob2` seçeneği. Bu pragma kullanılmasını gerektiren bir [/Ob](../build/reference/ob-inline-function-expansion.md) derleyici seçeneği ayarıyla 1 veya 2. İçin varsayılan duruma **inline_recursion** kapalıdır. Pragma görüldüğünde ve işlev tanımını etkilemez sonra bu pragmayı ilk işlev çağrısında etkili olur.

**İnline_recursion** pragma denetimleri nasıl özyinelemeli işlevler genişletilir. Varsa **inline_recursion** kapalıdır ve satır içi işlev kendisi (doğrudan veya dolaylı olarak), işlev çağrıları, genişletilmiş yalnızca bir kez yapılır. Varsa **inline_recursion** açıktır, işlevi, birden çok kez genişletilir, ile ayarlanan değere ulaşana kadar [inline_depth](../preprocessor/inline-depth.md) pragması, özyinelemeli işlevler için tarafındantanımlananvarsayılandeğer`inline_depth` pragma veya bir kapasite sınırlayın.

## <a name="see-also"></a>Ayrıca Bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[inline_depth](../preprocessor/inline-depth.md)<br/>
[/Ob (Satır İçi İşlev Genişletmesi)](../build/reference/ob-inline-function-expansion.md)