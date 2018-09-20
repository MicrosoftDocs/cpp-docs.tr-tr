---
title: Module::UnregisterObjects yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::UnregisterObjects
dev_langs:
- C++
helpviewer_keywords:
- UnregisterObjects method
ms.assetid: 3d8119a7-991d-45e9-b8c5-ed36c0be0332
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 87fb8ece3e1897a3ba460403d273bd649784ad44
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400443"
---
# <a name="moduleunregisterobjects-method"></a>Module::UnregisterObjects Yöntemi

Diğer uygulamalar için bağlantı nesneleri belirtilen modüldeki kaydını siler.

## <a name="syntax"></a>Sözdizimi

```cpp
HRESULT UnregisterObjects(
   ModuleBase* module,
   const wchar_t* serverName);
```

### <a name="parameters"></a>Parametreler

*Modülü*<br/>
Bir modül için işaretçi.

*SunucuAdı*<br/>
Bu işlemden etkilenen nesneler kümesini belirtir uygun bir ad.

## <a name="return-value"></a>Dönüş Değeri

Bu işlem başarılı olursa S_OK; Aksi takdirde bir hata nedenini belirten HRESULT bu işlemi başarısız oldu.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Modül Sınıfı](../windows/module-class.md)