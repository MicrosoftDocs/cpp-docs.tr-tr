---
title: _com_error::ErrorInfo
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorInfo
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
ms.openlocfilehash: cedb9ccadc63166c43d980333d93a195254700d8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180712"
---
# <a name="_com_errorerrorinfo"></a>_com_error::ErrorInfo

**Microsoft 'a özgü**

Oluşturucuya geçirilen `IErrorInfo` nesnesini alır.

## <a name="syntax"></a>Sözdizimi

```
IErrorInfo * ErrorInfo( ) const throw( );
```

## <a name="return-value"></a>Dönüş Değeri

Oluşturucuya geçirilen ham `IErrorInfo` öğesi.

## <a name="remarks"></a>Açıklamalar

Bir `_com_error` nesnesindeki kapsüllenmiş `IErrorInfo` öğeyi alır veya `IErrorInfo` öğe kaydediltiyse NULL olur. Çağıran, tarafından kullanılırken döndürülen nesne üzerinde `Release` çağırmalıdır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error Sınıfı](../cpp/com-error-class.md)
