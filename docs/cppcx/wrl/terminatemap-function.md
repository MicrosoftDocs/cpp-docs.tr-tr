---
description: 'Daha fazla bilgi edinin: TerminateMap Işlevi'
title: TerminateMap İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
ms.openlocfilehash: 919759d0b4b7f67cf3aff83c3e83678860d0badc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135076"
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

*birimi*<br/>
[Modül](module-class.md).

*serverName*<br/>
Parametre *modülü* tarafından belirtilen modüldeki sınıf fabrikalarının bir alt kümesinin adı.

*forceTerminate*<br/>
**`true`** sınıf fabrikalarını etkin olmalarından bağımsız olarak sonlandırmak için **`false`** herhangi bir fabrika etkin ise, sınıf fabrikalarını sonlandıramayın.

## <a name="return-value"></a>Dönüş Değeri

**`true`** Tüm sınıf fabrikaları sonlandırılırsa; Aksi takdirde, **`false`** .

## <a name="remarks"></a>Açıklamalar

Belirtilen modüldeki sınıf fabrikalarını kapatır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL::D euçlar ad alanı](microsoft-wrl-details-namespace.md)
