---
title: raw_interfaces_only
ms.date: 11/04/2016
f1_keywords:
- raw_interfaces_only
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
ms.openlocfilehash: 48133b85ccb5ddb8de8e6cb614d41cde22dac66b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179795"
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

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)