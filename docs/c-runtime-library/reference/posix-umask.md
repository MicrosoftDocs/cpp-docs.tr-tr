---
title: umask
ms.date: 12/16/2019
api_name:
- umask
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
- umask
helpviewer_keywords:
- umask function
ms.assetid: d2f697fc-08d5-4b70-9dd5-df3f5bb8b754
ms.openlocfilehash: e22832b7c4b9e9f7af0a6e98955a15b783c6931f
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301112"
---
# <a name="umask"></a>umask

Microsoft tarafından uygulanan POSIX işlev adı `umask`, [_umask](umask.md) işlevi için kullanım dışı bir diğer addır. Varsayılan olarak, [Derleyici Uyarısı (düzey 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)oluşturur. Ad, uygulamaya özgü adlarla ilgili standart C kurallarını izlemediğinden kullanım dışı bırakılmıştır. Ancak, işlev hala desteklenmektedir.

Bunun yerine [_umask](umask.md) veya güvenlik ile gelişmiş [_umask_s](umask-s.md) işlevi kullanmanızı öneririz. Ya da bu işlev adını kullanmaya devam edebilir ve uyarıyı devre dışı bırakabilirsiniz. Daha fazla bilgi için bkz. [Uyarı](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) ve [POSIX işlev adlarını](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)kapatma.
