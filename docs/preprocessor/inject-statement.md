---
title: inject_statement | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inject_statement
dev_langs:
- C++
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27b35c10e9e1953dc45dee1caf61d2e58c38d02d
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808649"
---
# <a name="injectstatement"></a>inject_statement

**C++ özgü**

Bağımsız değişkenini tür kitaplığı üstbilgisine kaynak metin olarak ekler.

## <a name="syntax"></a>Sözdizimi

```
inject_statement("source_text")
```

### <a name="parameters"></a>Parametreler

*source_text*<br/>
Tür kitaplığı üstbilgi dosyasına eklenecek kaynak metin.

## <a name="remarks"></a>Açıklamalar

Metin, üstbilgi dosyasında tür kitaplığı içeriğini saran ad alanı bildiriminin başına yerleştirilir.

**END C++ özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)