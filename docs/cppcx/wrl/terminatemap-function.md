---
title: TerminateMap İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
ms.openlocfilehash: 560f563e43fc8b818b04cd0bda6b01fbc916cb84
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213557"
---
# <a name="terminatemap-function"></a>TerminateMap İşlevi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
inline bool TerminateMap(
   _In_ ModuleBase *module,
   _In_opt_z_ const wchar_t *serverName,
    bool forceTerminate) throw()
```

### <a name="parameters"></a>Parametreler

*module*<br/>
[Modül](module-class.md).

*serverName*<br/>
Parametre *modülü*tarafından belirtilen modüldeki sınıf fabrikalarının bir alt kümesinin adı.

*forceTerminate*<br/>
etkin olduklarından bağımsız olarak sınıf fabrikalarını sonlandırmak için **true** ; herhangi bir fabrika etkin ise, sınıf fabrikalarını sonlandırmak için **false** .

## <a name="return-value"></a>Dönüş Değeri

Tüm sınıf fabrikaları sonlandırılırsa **doğru** . Aksi takdirde, **false**.

## <a name="remarks"></a>Açıklamalar

Belirtilen modüldeki sınıf fabrikalarını kapatır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Details Ad Alanı](microsoft-wrl-details-namespace.md)
