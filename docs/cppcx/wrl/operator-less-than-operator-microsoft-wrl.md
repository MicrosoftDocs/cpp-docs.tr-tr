---
description: 'Daha fazla bilgi edinin: işleç &lt; işleci (Microsoft:: WRL)'
title: 'işleç &lt; işleci (Microsoft:: WRL)'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator<
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
ms.openlocfilehash: 1edbb8218ef07355040bd05ab99db8f97be1cb59
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330775"
---
# <a name="operatorlt-operator-microsoftwrl"></a>işleç &lt; işleci (Microsoft:: WRL)

Bir nesnenin adresinin diğerinden daha küçük olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class T, class U>
bool operator<(const ComPtr<T>& a, const ComPtr<U>& b) throw();
template<class T, class U>
bool operator<(const Details::ComPtrRef<ComPtr<T>>& a, const Details::ComPtrRef<ComPtr<U>>& b) throw();
```

### <a name="parameters"></a>Parametreler

*a*<br/>
Sol nesne.

*kenarı*<br/>
Doğru nesne.

## <a name="return-value"></a>Dönüş Değeri

**`true`** adresinin adresi *b*'nin *adresinden* küçükse; Aksi takdirde, **`false`** .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL ad alanı](microsoft-wrl-namespace.md)
