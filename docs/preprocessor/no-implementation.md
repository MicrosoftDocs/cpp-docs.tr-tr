---
title: no_implementation içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- no_implementation
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
ms.openlocfilehash: 8f0a7454fdbedc1959b665ccb2a23748d21c342d
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220774"
---
# <a name="no_implementation-import-attribute"></a>no_implementation içeri aktarma özniteliği

**C++Belirli**

Sarmalayıcı üye işlevlerinin uygulamalarını içeren `.tli` üst bilginin oluşturulmasını engeller.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür kitaplığı* **no_implementation**

## <a name="remarks"></a>Açıklamalar

Bu öznitelik belirtilmişse `.tlh` , tür kitaplığı öğelerini kullanıma sunma bildirimiyle birlikte üst bilgi, `.tli` başlık dosyasını dahil etmek için bir `#include` bildirim olmadan oluşturulur.

Bu öznitelik, [implementation_only](../preprocessor/implementation-only.md)ile birlikte kullanılır.

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
