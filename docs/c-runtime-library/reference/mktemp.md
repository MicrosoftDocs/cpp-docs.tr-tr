---
title: mktemp
ms.date: 12/16/2019
api_name:
- mktemp
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
- mktemp
helpviewer_keywords:
- mktemp function
ms.assetid: b58cba60-034f-4e63-b312-ccbcd489d0a7
ms.openlocfilehash: c9efd79111c000764561ba415db79a13a34c46fe
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301021"
---
# <a name="mktemp"></a>mktemp

`mktemp` Microsoft 'a özgü işlev adı, [_mktemp](mktemp-wmktemp.md) işlevi için kullanım dışı bırakılmış bir diğer addır. Varsayılan olarak, [Derleyici Uyarısı (düzey 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)oluşturur. Ad, uygulamaya özgü adlarla ilgili standart C kurallarını izlemediğinden kullanım dışı bırakılmıştır. Ancak, işlev hala desteklenmektedir.

Bunun yerine [_mktemp](mktemp-wmktemp.md) veya güvenlik ile gelişmiş [_mktemp_s](mktemp-s-wmktemp-s.md) işlevini kullanmanızı öneririz. Ya da bu işlev adını kullanmaya devam edebilir ve uyarıyı devre dışı bırakabilirsiniz. Daha fazla bilgi için bkz. [Uyarı](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) ve [POSIX işlev adlarını](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)kapatma.
