---
description: 'Daha fazla bilgi edinin: inline_recursion pragma'
title: inline_recursion pragması
ms.date: 08/29/2019
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
ms.openlocfilehash: 1688eb724a9a76ce3f173c7f9eac7d52032fbe13
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236379"
---
# <a name="inline_recursion-pragma"></a>inline_recursion pragması

Doğrudan veya birbirini dışlayan özyinelemeli işlev çağrılarının satır içi genişletmesini denetler.

## <a name="syntax"></a>Syntax

> **#pragma inline_recursion (** **[{**  |  **off** }] **)**

## <a name="remarks"></a>Açıklamalar

[Satır içi](../cpp/inline-functions-cpp.md) olarak işaretlenen işlevleri denetlemek için bu pragmayı kullanın ve derleyicinin seçenek altında otomatik olarak genişledikleri [__inline](../cpp/inline-functions-cpp.md) ya da işlevleri `/Ob2` . Bu pragma kullanımı, 1 veya 2 ' nin [/ob](../build/reference/ob-inline-function-expansion.md) derleyici seçeneği ayarını gerektirir. **İnline_recursion** için varsayılan durum kapalıdır. Bu pragma, pragma görüntülendikten sonra ilk işlev çağrısında etkili olur ve işlevin tanımını etkilemez.

**İnline_recursion** pragma özyinelemeli işlevlerin nasıl genişletildiğini denetler. **İnline_recursion** kapalıysa ve bir satır içi işlev kendisini doğrudan ya da dolaylı olarak çağırırsa, işlev yalnızca bir kez genişletilir. **İnline_recursion** açık ise, işlev [inline_depth](../preprocessor/inline-depth.md) pragması, pragma tarafından tanımlanan özyinelemeli işlevlerin varsayılan değeri `inline_depth` veya bir kapasite sınırı olan değer kümesine ulaşıncaya kadar birden çok kez genişletilir.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[inline_depth](../preprocessor/inline-depth.md)\
[/OB (satır Içi Işlev genişletmesi)](../build/reference/ob-inline-function-expansion.md)
