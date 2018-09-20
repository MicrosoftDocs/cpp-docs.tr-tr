---
title: TerminateMap işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
dev_langs:
- C++
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f844d63bc04deb4294203f04aef30db48f195fd9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438073"
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

*Modülü*<br/>
A [Modülü](../windows/module-class.md).

*SunucuAdı*<br/>
Sınıf üreteçlerini parametresi tarafından belirtilen modüldeki bir alt kümesi adını *Modülü*.

*forceTerminate*<br/>
**doğru** sınıfı sonlandırmak için bunlar bağımsız olarak fabrikaları; etkindir **false** herhangi bir Fabrika etkinse sınıf üreteçlerini sona erdirmek.

## <a name="return-value"></a>Dönüş Değeri

**doğru** tüm sınıf üreteçlerini, sonlandırılmış; Aksi takdirde **false**.

## <a name="remarks"></a>Açıklamalar

Belirtilen modül sınıfı Fabrikalar kapatır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)