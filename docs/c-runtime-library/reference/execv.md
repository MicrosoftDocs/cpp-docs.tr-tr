---
title: execv
ms.date: 12/16/2019
api_name:
- execv
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
- execv
helpviewer_keywords:
- execv function
ms.assetid: b097d606-9384-427a-9a1d-707dc4ce03ae
ms.openlocfilehash: b9467106dd059380ec9d8af4ccaeeadd93f900fb
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75299630"
---
# <a name="execv"></a>execv

Microsoft tarafından uygulanan POSIX işlev adı `execv`, [_execv](execv-wexecv.md) işlevi için kullanım dışı bir diğer addır. Varsayılan olarak, [Derleyici Uyarısı (düzey 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)oluşturur. Ad, uygulamaya özgü adlarla ilgili standart C kurallarını izlemediğinden kullanım dışı bırakılmıştır. Ancak, işlev hala desteklenmektedir.

Bunun yerine [_execv](execv-wexecv.md) kullanmanızı öneririz. Ya da bu işlev adını kullanmaya devam edebilir ve uyarıyı devre dışı bırakabilirsiniz. Daha fazla bilgi için bkz. [Uyarı](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) ve [POSIX işlev adlarını](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)kapatma.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).
