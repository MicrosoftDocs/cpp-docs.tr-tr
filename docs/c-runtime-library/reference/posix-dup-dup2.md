---
description: 'Daha fazla bilgi edinin: DUP, dUP2'
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
ms.openlocfilehash: a3a7700aa37a5166c76bca0fcb5c71e6dc50e1a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117516"
---
# <a name="dup-dup2"></a>dup, dup2

Microsoft tarafından uygulanan POSIX işlev adları `dup` ve `dup2` [_dup](dup-dup2.md) ve [_dup2](dup-dup2.md) işlevleri için kullanım dışı diğer adlar. Varsayılan olarak, [Derleyici Uyarısı (düzey 3) oluşturur C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Adlar, uygulamaya özgü adlarla ilgili standart C kurallarını izlemediğinden kullanım dışı bırakılmıştır. Ancak, işlevleri hala desteklenmektedir.

Bunun yerine [_dup](dup-dup2.md) ve [_dup2](dup-dup2.md) kullanmanızı öneririz. Ya da bu işlev adlarını kullanmaya devam edebilir ve uyarıyı devre dışı bırakabilirsiniz. Daha fazla bilgi için bkz. [Uyarı](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) ve [POSIX işlev adlarını](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)kapatma.
