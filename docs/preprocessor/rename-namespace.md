---
title: rename_namespace içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- rename_namespace
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
ms.openlocfilehash: d319d7390e7c7dce070a35be44aad37c7a34e1a0
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216648"
---
# <a name="rename_namespace-import-attribute"></a>rename_namespace içeri aktarma özniteliği

**C++Belirli**

Tür kitaplığının içeriğini içeren ad alanını yeniden adlandırır.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür kitaplığı* **rename_namespace (** "*YeniAd*" **)**

### <a name="parameters"></a>Parametreler

*Ad*\
Ad alanının yeni adı.

## <a name="remarks"></a>Açıklamalar

**Rename_namespace** özniteliği, ad alanı için yeni adı belirten bir bağımsız değişken ( *YeniAd*) alır.

Ad alanını kaldırmak için bunun yerine [no_namespace](../preprocessor/no-namespace.md) özniteliğini kullanın.

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
