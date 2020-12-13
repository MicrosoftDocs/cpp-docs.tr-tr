---
description: 'Hakkında daha fazla bilgi edinin: no_dual_interfaces Import özniteliği'
title: no_dual_interfaces içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- no_dual_interfaces
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
ms.openlocfilehash: 1c3010b252ac71e38312fa193520938fbb4d681a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333335"
---
# <a name="no_dual_interfaces-import-attribute"></a>no_dual_interfaces içeri aktarma özniteliği

**C++ özel**

Derleyicinin çift arabirim yöntemleri için sarmalayıcı işlevleri üretme şeklini değiştirir.

## <a name="syntax"></a>Syntax

> **#import** *türü-kitaplık* **no_dual_interfaces**

## <a name="remarks"></a>Açıklamalar

Normalde sarmalayıcı, arabirimi için sanal işlev tablosu aracılığıyla yöntemini çağırır. **No_dual_interfaces**, sarmalayıcı `IDispatch::Invoke` metodunu çağırmak için çağırır.

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
