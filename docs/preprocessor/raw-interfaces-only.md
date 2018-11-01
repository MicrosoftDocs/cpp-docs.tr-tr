---
title: raw_interfaces_only
ms.date: 11/04/2016
f1_keywords:
- raw_interfaces_only
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
ms.openlocfilehash: c07401036261b9f93bb2c07dcf3aff1ecf72e2fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519359"
---
# <a name="rawinterfacesonly"></a>raw_interfaces_only
**C++ özgü**

Hata işleme sarmalayıcı işlevleri oluşturulmasını engeller ve [özelliği](../cpp/property-cpp.md) bu sarmalayıcı işlevleri bildirimleri.

## <a name="syntax"></a>Sözdizimi

```
raw_interfaces_only
```

## <a name="remarks"></a>Açıklamalar

**Raw_interfaces_only** özniteliği de kaldırılacak özelliği olmayan işlevler adlandırmada kullanılan varsayılan ön ek neden olur. Normalde, ön ekidir **raw_**. Bu öznitelik belirtilmezse, işlev doğrudan tür kitaplığından adlarıdır.

Bu öznitelik yalnızca alt düzey tür kitaplığı içeriğini kullanıma sunmanıza olanak sağlar.

**END C++ özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)