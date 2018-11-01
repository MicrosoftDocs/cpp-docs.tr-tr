---
title: İşleç&lt; işleci (Microsoft::WRL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator<
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
ms.openlocfilehash: 2c45f4b2c905fe925cdb52520180d83a4c156b53
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50645074"
---
# <a name="operatorlt-operator-microsoftwrl"></a>İşleç&lt; işleci (Microsoft::WRL)

Bir nesnenin adresini daha az olup olmadığını belirler.

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

*b*<br/>
Doğru nesne.

## <a name="return-value"></a>Dönüş Değeri

**doğru** varsa adresini *bir* adresini'dan küçük *b*; Aksi takdirde **false**.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)