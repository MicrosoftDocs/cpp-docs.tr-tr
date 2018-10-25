---
title: raw_interfaces_only | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_interfaces_only
dev_langs:
- C++
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 789c9179b2ba48f5c3796f709931728bc756aaaa
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075040"
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