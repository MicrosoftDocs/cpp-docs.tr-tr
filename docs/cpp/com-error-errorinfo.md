---
title: _com_error::ErrorInfo
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorInfo
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
ms.openlocfilehash: 59ada8a7e098e57cca5641a439365851bbae2485
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155078"
---
# <a name="comerrorerrorinfo"></a>_com_error::ErrorInfo

**Microsoft'a özgü**

Alır `IErrorInfo` oluşturucuya nesnesi geçirildi.

## <a name="syntax"></a>Sözdizimi

```
IErrorInfo * ErrorInfo( ) const throw( );
```

## <a name="return-value"></a>Dönüş Değeri

Ham `IErrorInfo` öğesi oluşturucuya geçirilen.

## <a name="remarks"></a>Açıklamalar

Kapsüllenmiş alır `IErrorInfo` öğesi bir `_com_error` nesne veya hiç yoksa NULL `IErrorInfo` öğesi kaydedilir. Çağıranın çağırmalıdır `Release` bittiğinde, döndürülen nesneyi kullanmayı.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error Sınıfı](../cpp/com-error-class.md)