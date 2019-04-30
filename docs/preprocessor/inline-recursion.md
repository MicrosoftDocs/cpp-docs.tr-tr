---
title: inline_recursion
ms.date: 11/04/2016
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
ms.openlocfilehash: 80ffabc6ac7c95fd7d9fb4e62bea38c2a04b04f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383704"
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

## <a name="see-also"></a>Ayrıca bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[inline_depth](../preprocessor/inline-depth.md)<br/>
[/Ob (Satır İçi İşlev Genişletmesi)](../build/reference/ob-inline-function-expansion.md)