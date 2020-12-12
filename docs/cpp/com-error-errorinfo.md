---
description: 'Hakkında daha fazla bilgi edinin: _com_error:: ErrorInfo'
title: _com_error::ErrorInfo
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorInfo
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
ms.openlocfilehash: 36092ae9287352d421bf502ad24c054cf3b7a907
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296049"
---
# <a name="_com_errorerrorinfo"></a>_com_error::ErrorInfo

**Microsoft'a Özgü**

`IErrorInfo`Oluşturucuya geçirilen nesneyi alır.

## <a name="syntax"></a>Syntax

```
IErrorInfo * ErrorInfo( ) const throw( );
```

## <a name="return-value"></a>Dönüş Değeri

`IErrorInfo`Oluşturucuya geçirilen ham öğe.

## <a name="remarks"></a>Açıklamalar

`IErrorInfo`Bir nesne içindeki kapsüllenmiş öğeyi alır `_com_error` veya hiçbir `IErrorInfo` öğe kaydediltiyse null değerini alır. Çağıran `Release` nesne kullanılarak çalıştırıldığında döndürülen nesneyi çağırmalıdır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error sınıfı](../cpp/com-error-class.md)
