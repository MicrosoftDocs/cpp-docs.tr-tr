---
title: _com_error::Description
ms.date: 11/04/2016
f1_keywords:
- _com_error::Description
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
ms.openlocfilehash: de2275f096fe2fde96e64cbc3034602a1fde5e88
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180777"
---
# <a name="_com_errordescription"></a>_com_error::Description

**Microsoft 'a özgü**

`IErrorInfo::GetDescription` işlevini çağırır.

## <a name="syntax"></a>Sözdizimi

```
_bstr_t Description( ) const;
```

## <a name="return-value"></a>Dönüş Değeri

`_com_error` nesnesi içinde kaydedilen `IErrorInfo` nesnesi için `IErrorInfo::GetDescription` sonucunu döndürür. Elde edilen `BSTR`, bir `_bstr_t` nesnesi içinde kapsüllenir. Kayıtlı `IErrorInfo` yoksa boş bir `_bstr_t`döndürür.

## <a name="remarks"></a>Açıklamalar

`IErrorInfo::GetDescription` işlevini çağırır ve `_com_error` nesne içinde kaydedilen `IErrorInfo` alır. `IErrorInfo::GetDescription` yöntemi çağrılırken herhangi bir hata yoksayıldı.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[_com_error Sınıfı](../cpp/com-error-class.md)
