---
title: 'işleç&lt; Işleci (Microsoft:: WRL)'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator<
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
ms.openlocfilehash: 04f5598667f7e0e036f0a55cd3f9cc52b5356299
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213648"
---
# <a name="operatorlt-operator-microsoftwrl"></a>işleç&lt; Işleci (Microsoft:: WRL)

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

*a* adresinin adresi *b*'nin adresinden küçükse, **doğru** . Aksi takdirde, **false**.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Client. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)
