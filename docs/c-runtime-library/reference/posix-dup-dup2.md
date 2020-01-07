---
title: dup, dup2
ms.date: 12/16/2019
api_name:
- dup2
- dup
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- dup
- dup2
helpviewer_keywords:
- dup function
- dup2 function
ms.assetid: c7572170-47ff-4e0d-b9c3-10f0ab0ba40a
ms.openlocfilehash: ea6fe475b4a5e3cce5e9d05d89bd351361c2a4de
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301216"
---
# <a name="dup-dup2"></a>dup, dup2

`dup` ve `dup2` Microsoft tarafından uygulanan POSIX işlev adları [_dup](dup-dup2.md) ve [_dup2](dup-dup2.md) işlevlerinin kullanım dışı diğer adlarıdır. Varsayılan olarak, [Derleyici Uyarısı (düzey 3) oluşturur C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Adlar, uygulamaya özgü adlarla ilgili standart C kurallarını izlemediğinden kullanım dışı bırakılmıştır. Ancak, işlevleri hala desteklenmektedir.

Bunun yerine [_dup](dup-dup2.md) ve [_dup2](dup-dup2.md) kullanmanızı öneririz. Ya da bu işlev adlarını kullanmaya devam edebilir ve uyarıyı devre dışı bırakabilirsiniz. Daha fazla bilgi için bkz. [Uyarı](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) ve [POSIX işlev adlarını](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)kapatma.
