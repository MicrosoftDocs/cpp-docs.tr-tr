---
title: Platform::RecreateException yöntemi
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
ms.openlocfilehash: 9e167efc54352d125e849956a2da8d8e8cad4ed6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330329"
---
# <a name="platformrecreateexception-method"></a>Platform::ReCreateException yöntemi

Bu yöntem, yalnızca dahili kullanım içindir ve kullanıcı kodu için tasarlanmamıştır. Bunun yerine Exception::CreateException yöntemi kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
static Exception^ ReCreateException(int hr)
```

### <a name="parameters"></a>Parametreler

*İK*

### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

Yeni bir Platform::Exception döndürür ^ bağlı olarak belirtilen HRESULT.
