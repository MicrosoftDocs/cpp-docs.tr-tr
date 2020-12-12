---
description: ': Strnset, wcsnset hakkında daha fazla bilgi'
title: strnset, wcsnset
ms.date: 12/16/2019
api_name:
- strnset
- wcsnset
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
- wcsnset
- strnset
helpviewer_keywords:
- strnset function
- wcsnset function
ms.assetid: e7868ac9-dc34-4606-bd3c-0fb2e7c51631
ms.openlocfilehash: a38241e52330786d15fa1ff8bb0172c7aff0e5bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341418"
---
# <a name="strnset-wcsnset"></a>strnset, wcsnset

Microsoft 'a özgü işlev adları `strnset` ve `wcsnset` [_strnset ve _wcsnset](strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md) işlevleri için kullanım dışı diğer adlar. Varsayılan olarak, [Derleyici Uyarısı (düzey 3) oluşturur C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Adlar, uygulamaya özgü adlarla ilgili standart C kurallarını izlemediğinden kullanım dışı bırakılmıştır. Ancak, işlevleri hala desteklenmektedir.

Bunun yerine [_strnset ve _wcsnset](strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md) ya da gelişmiş güvenlik [_strnset_s ve _wcsnset_s](strnset-s-strnset-s-l-wcsnset-s-wcsnset-s-l-mbsnset-s-mbsnset-s-l.md) işlevlerini kullanmanızı öneririz. Ya da bu işlev adlarını kullanmaya devam edebilir ve uyarıyı devre dışı bırakabilirsiniz. Daha fazla bilgi için bkz. [Uyarı](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) ve [POSIX işlev adlarını](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)kapatma.
