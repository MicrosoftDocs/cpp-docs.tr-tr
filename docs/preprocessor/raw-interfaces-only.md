---
title: raw_interfaces_only içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- raw_interfaces_only
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
ms.openlocfilehash: 4b79aa4dbafa204d84f4d6ed7ec78fdec1b81fa7
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216213"
---
# <a name="raw_interfaces_only-import-attribute"></a>raw_interfaces_only içeri aktarma özniteliği

**C++Belirli**

Hata işleme sarmalayıcı işlevlerinin ve bu sarmalayıcı işlevlerini kullanan [özellik](../cpp/property-cpp.md) bildirimlerinin oluşturulmasını engeller.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür kitaplığı* **raw_interfaces_only**

## <a name="remarks"></a>Açıklamalar

**Raw_interfaces_only** özniteliği Ayrıca Özellik dışı işlevlerin kaldırılmasına izin vermek için kullanılan varsayılan öneki de sağlar. Genellikle, ön ek olur `raw_`. Bu öznitelik belirtilmişse, işlev adları doğrudan tür kitaplığından alınır.

Bu öznitelik, yalnızca tür kitaplığının alt düzey içeriğini sergileme olanağı sağlar.

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
