---
title: strdup, wcsdup
ms.date: 12/16/2019
api_name:
- wcsdup
- strdup
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
- wcsdup
- strdup
helpviewer_keywords:
- wcsdup function
- strdup function
ms.assetid: c9ac0935-b525-4e95-8a64-396fc7e34ee9
ms.openlocfilehash: e381a1933a6b657108a66053bad1c7ff795c1a29
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75300527"
---
# <a name="strdup-wcsdup"></a>strdup, wcsdup

`strdup` ve `wcsdup` Microsoft tarafından uygulanan POSIX işlev adları [_strdup ve _wcsdup](strdup-wcsdup-mbsdup.md) işlevlerinin kullanım dışı diğer adlarıdır. Varsayılan olarak, [Derleyici Uyarısı (düzey 3) oluşturur C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Adlar, uygulamaya özgü adlarla ilgili standart C kurallarını izlemediğinden kullanım dışı bırakılmıştır. Ancak, işlevleri hala desteklenmektedir.

Bunun yerine [_strdup ve _wcsdup](strdup-wcsdup-mbsdup.md) kullanmanızı öneririz. Ya da bu işlev adlarını kullanmaya devam edebilir ve uyarıyı devre dışı bırakabilirsiniz. Daha fazla bilgi için bkz. [Uyarı](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) ve [POSIX işlev adlarını](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)kapatma.
