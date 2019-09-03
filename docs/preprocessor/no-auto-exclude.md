---
title: no_auto_exclude içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- no_auto_exclude
helpviewer_keywords:
- no_auto_exclude attribute
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
ms.openlocfilehash: 530c2b2adf24e964cb0a512371f4430a61bf8b11
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216084"
---
# <a name="no_auto_exclude-import-attribute"></a>no_auto_exclude içeri aktarma özniteliği

**C++Belirli**

Otomatik dışlamayı devre dışı bırakır.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür kitaplığı* **no_auto_exclude**

## <a name="remarks"></a>Açıklamalar

Tür kitaplıkları, sistem üstbilgileri veya diğer tür kitaplıklarında tanımlanan öğelerin tanımlarını içerebilir. `#import`Bu tür öğeleri otomatik olarak dışlayarak birden çok tanım hatasını önlemenize çalışır. Bu, [Derleyici Uyarısı (düzey 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md) 'in hariç tutulacak her öğe için verilmesine neden olur. Bu özniteliği kullanarak otomatik dışlamayı devre dışı bırakabilirsiniz.

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
