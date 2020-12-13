---
description: 'Hakkında daha fazla bilgi edinin: raw_interfaces_only Import özniteliği'
title: raw_interfaces_only içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- raw_interfaces_only
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
ms.openlocfilehash: f043bef5cde0454ce9f08f45efb0417aa7fdbb2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142746"
---
# <a name="raw_interfaces_only-import-attribute"></a>raw_interfaces_only içeri aktarma özniteliği

**C++ özel**

Hata işleme sarmalayıcı işlevlerinin ve bu sarmalayıcı işlevlerini kullanan [özellik](../cpp/property-cpp.md) bildirimlerinin oluşturulmasını engeller.

## <a name="syntax"></a>Syntax

> **#import** *türü-kitaplık* **raw_interfaces_only**

## <a name="remarks"></a>Açıklamalar

**Raw_interfaces_only** özniteliği, Özellik dışı işlevlerin kaldırılmasına izin vermek için kullanılan varsayılan ön eke de neden olur. Genellikle, ön ek olur `raw_` . Bu öznitelik belirtilmişse, işlev adları doğrudan tür kitaplığından alınır.

Bu öznitelik, yalnızca tür kitaplığının alt düzey içeriğini sergileme olanağı sağlar.

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
