---
description: 'Hakkında daha fazla bilgi edinin: no_implementation Import özniteliği'
title: no_implementation içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- no_implementation
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
ms.openlocfilehash: 0cfd51b344847d2e5658fd4e4ec1a9f30db51fe6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333328"
---
# <a name="no_implementation-import-attribute"></a>no_implementation içeri aktarma özniteliği

**C++ özel**

`.tli`Sarmalayıcı üye işlevlerinin uygulamalarını içeren üst bilginin oluşturulmasını engeller.

## <a name="syntax"></a>Syntax

> **#import** *türü-kitaplık* **no_implementation**

## <a name="remarks"></a>Açıklamalar

Bu öznitelik belirtilmişse, `.tlh` tür kitaplığı öğelerini kullanıma sunma bildirimiyle birlikte üst bilgi, `#include` başlık dosyasını dahil etmek için bir bildirim olmadan oluşturulur `.tli` .

Bu öznitelik [implementation_only](../preprocessor/implementation-only.md)birlikte kullanılır.

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
