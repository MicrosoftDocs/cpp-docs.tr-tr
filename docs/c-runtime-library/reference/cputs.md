---
description: 'Daha fazla bilgi edinin: cput'
title: cputs
ms.date: 12/16/2019
api_name:
- cputs
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
- cputs
helpviewer_keywords:
- cputs function
ms.assetid: 0c2a7d4e-623a-4cb2-a0f9-1900c05bac08
ms.openlocfilehash: 4d39fde67830fc92c2ff31c8fa6529817d2e5b86
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155936"
---
# <a name="cputs"></a>cputs

Microsoft 'a özgü işlev adı, `cputs` [_cputs](cputs-cputws.md) işlevi için kullanım dışı bir diğer addır. Varsayılan olarak, [Derleyici Uyarısı (düzey 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)oluşturur. Ad, uygulamaya özgü adlarla ilgili standart C kurallarını izlemediğinden kullanım dışı bırakılmıştır. Ancak, işlev hala desteklenmektedir.

Bunun yerine [_cputs](cputs-cputws.md) kullanmanızı öneririz. Ya da bu işlev adını kullanmaya devam edebilir ve uyarıyı devre dışı bırakabilirsiniz. Daha fazla bilgi için bkz. [Uyarı](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) ve [POSIX işlev adlarını](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)kapatma.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).
