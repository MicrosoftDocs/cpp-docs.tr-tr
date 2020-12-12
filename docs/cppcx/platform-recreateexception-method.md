---
description: 'Daha fazla bilgi edinin: Platform:: ReCreateException yöntemi'
title: 'Platform:: RecreateException yöntemi'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
ms.openlocfilehash: 273f60055e4cf5a940558ba5dcaa4aa6a7c70bca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308061"
---
# <a name="platformrecreateexception-method"></a>Platform:: ReCreateException yöntemi

Bu yöntem yalnızca dahili kullanım içindir ve Kullanıcı kodu için tasarlanmamıştır. Bunun yerine Exception:: CreateException metodunu kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
static Exception^ ReCreateException(int hr)
```

### <a name="parameters"></a>Parametreler

*sa*

### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

Belirtilen HRESULT temelinde yeni bir platform:: Exception ^ döndürür.
