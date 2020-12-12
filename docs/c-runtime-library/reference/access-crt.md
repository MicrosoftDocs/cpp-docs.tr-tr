---
description: 'Daha fazla bilgi edinin: erişim (CRT)'
title: erişim (CRT)
ms.date: 12/16/2019
api_name:
- access
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
- access
helpviewer_keywords:
- access function
ms.assetid: 65197793-bd0a-41c3-9c29-18de2d95d9a6
ms.openlocfilehash: 2ebfffcdc73f77a083ed5a1f29b34e2cd2e0b76a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97303935"
---
# <a name="access-crt"></a>erişim (CRT)

Microsoft tarafından uygulanan POSIX işlev adı, `access` [_access](access-waccess.md) işlevi için kullanım dışı bir diğer addır. Varsayılan olarak, [Derleyici Uyarısı (düzey 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)oluşturur. Ad, uygulamaya özgü adlarla ilgili standart C kurallarını izlemediğinden kullanım dışı bırakılmıştır. Ancak, işlev hala desteklenmektedir.

Bunun yerine [_access](access-waccess.md) veya güvenlik ile gelişmiş [_access_s](access-s-waccess-s.md) işlevini kullanmanızı öneririz. Ya da bu işlev adını kullanmaya devam edebilir ve uyarıyı devre dışı bırakabilirsiniz. Daha fazla bilgi için bkz. [Uyarı](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) ve [POSIX işlev adlarını](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)kapatma.
