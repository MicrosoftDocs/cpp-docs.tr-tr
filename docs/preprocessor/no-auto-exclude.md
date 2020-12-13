---
description: 'Hakkında daha fazla bilgi edinin: no_auto_exclude Import özniteliği'
title: no_auto_exclude içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- no_auto_exclude
helpviewer_keywords:
- no_auto_exclude attribute
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
ms.openlocfilehash: 81e4d7e7f9295a4ed983e2a5024d891e30fe1361
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333348"
---
# <a name="no_auto_exclude-import-attribute"></a>no_auto_exclude içeri aktarma özniteliği

**C++ özel**

Otomatik dışlamayı devre dışı bırakır.

## <a name="syntax"></a>Syntax

> **#import** *türü-kitaplık* **no_auto_exclude**

## <a name="remarks"></a>Açıklamalar

Tür kitaplıkları, sistem üstbilgileri veya diğer tür kitaplıklarında tanımlanan öğelerin tanımlarını içerebilir. `#import` Bu tür öğeleri otomatik olarak dışlayarak birden çok tanım hatasını önlemenize çalışır. Bu, [Derleyici Uyarısı (düzey 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md) 'in hariç tutulacak her öğe için verilmesine neden olur. Bu özniteliği kullanarak otomatik dışlamayı devre dışı bırakabilirsiniz.

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
