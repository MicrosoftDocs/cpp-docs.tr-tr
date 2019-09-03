---
title: no_dual_interfaces içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- no_dual_interfaces
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
ms.openlocfilehash: 6270888f0d31e4fbe18fb3364995be8c73426b83
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220756"
---
# <a name="no_dual_interfaces-import-attribute"></a>no_dual_interfaces içeri aktarma özniteliği

**C++Belirli**

Derleyicinin çift arabirim yöntemleri için sarmalayıcı işlevleri üretme şeklini değiştirir.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür kitaplığı* **no_dual_interfaces**

## <a name="remarks"></a>Açıklamalar

Normalde sarmalayıcı, arabirimi için sanal işlev tablosu aracılığıyla yöntemini çağırır. **No_dual_interfaces**ile sarmalayıcı, yöntemi çağırmak için `IDispatch::Invoke` çağırır.

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
