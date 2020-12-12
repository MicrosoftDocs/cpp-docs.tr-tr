---
description: 'Daha fazla bilgi edinin: tempnam'
title: tempnam
ms.date: 12/16/2019
api_name:
- tempnam
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
- tempnam
helpviewer_keywords:
- tempnam function
ms.assetid: 42446733-f131-470f-b4d0-96918becab11
ms.openlocfilehash: 14bf6b9e4614ee82af4fe7f0aee10f81d97194cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326189"
---
# <a name="tempnam"></a>tempnam

Microsoft tarafından uygulanan POSIX işlev adı, `tempnam` [_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md) işlevi için kullanım dışı bir diğer addır. Varsayılan olarak, [Derleyici Uyarısı (düzey 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)oluşturur. Ad, uygulamaya özgü adlarla ilgili standart C kurallarını izlemediğinden kullanım dışı bırakılmıştır. Ancak, işlev hala desteklenmektedir.

Bunun yerine [_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md) kullanmanızı öneririz. Ya da bu işlev adını kullanmaya devam edebilir ve uyarıyı devre dışı bırakabilirsiniz. Daha fazla bilgi için bkz. [Uyarı](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) ve [POSIX işlev adlarını](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)kapatma.
