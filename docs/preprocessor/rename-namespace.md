---
description: 'Hakkında daha fazla bilgi edinin: rename_namespace Import özniteliği'
title: rename_namespace içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- rename_namespace
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
ms.openlocfilehash: 402d9c9cd8dee5979dd71e16fec1a606d8b4b996
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167389"
---
# <a name="rename_namespace-import-attribute"></a>rename_namespace içeri aktarma özniteliği

**C++ özel**

Tür kitaplığının içeriğini içeren ad alanını yeniden adlandırır.

## <a name="syntax"></a>Syntax

> **#import** *türü-kitaplık* **rename_namespace (** "*YeniAd*" **)**

### <a name="parameters"></a>Parametreler

*Ad*\
Ad alanının yeni adı.

## <a name="remarks"></a>Açıklamalar

**Rename_namespace** özniteliği, ad alanı için yeni adı belirten bir bağımsız değişken ( *YeniAd*) alır.

Ad alanını kaldırmak için bunun yerine [no_namespace](../preprocessor/no-namespace.md) özniteliğini kullanın.

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
