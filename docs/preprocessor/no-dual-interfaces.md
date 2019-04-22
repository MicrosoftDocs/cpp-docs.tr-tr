---
title: no_dual_interfaces
ms.date: 11/04/2016
f1_keywords:
- no_dual_interfaces
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
ms.openlocfilehash: ae75bc2e974f374768f1a9e5a0e1ced61e9904b0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023808"
---
# <a name="nodualinterfaces"></a>no_dual_interfaces
**C++ özgü**

Değişiklikleri derleyici yolu çift arabirim yöntemleri için sarmalayıcı işlevleri oluşturur.

## <a name="syntax"></a>Sözdizimi

```
no_dual_interfaces
```

## <a name="remarks"></a>Açıklamalar

Normalde, sarmalayıcı yöntemin sanal işlev tablosu aracılığıyla arabirimi çağırır. İle **no_dual_interfaces**, bunun yerine sarmalayıcıyı çağıran `IDispatch::Invoke` yöntemini çağırmak için.

**END C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)