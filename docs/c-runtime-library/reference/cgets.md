---
title: cgets
ms.date: 12/16/2019
api_name:
- cgets
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
- cgets
helpviewer_keywords:
- cgets function
ms.assetid: 54faf257-5ed6-4301-be19-66d953e901fa
ms.openlocfilehash: 702bb75381eb458b3c98ac2991a28046ebb561a7
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75299981"
---
# <a name="cgets"></a>cgets

`cgets` Microsoft 'a özgü işlev adı, [_cgets](../cgets-cgetws.md) işlevi için kullanım dışı bırakılmış bir diğer addır. Varsayılan olarak, [Derleyici Uyarısı (düzey 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)oluşturur. Ad, uygulamaya özgü adlarla ilgili standart C kurallarını izlemediğinden kullanım dışı bırakılmıştır. Ancak, işlev hala desteklenmektedir.

Bunun yerine güvenlik ile geliştirilmiş [_cgets_s](cgets-s-cgetws-s.md) işlevini kullanmanızı öneririz. Ya da bu işlev adını kullanmaya devam edebilir ve uyarıyı devre dışı bırakabilirsiniz. Daha fazla bilgi için bkz. [Uyarı](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) ve [POSIX işlev adlarını](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)kapatma.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).
