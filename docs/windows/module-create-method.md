---
title: Module::Create yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Create
dev_langs:
- C++
helpviewer_keywords:
- Create method
ms.assetid: bfa97fd7-5226-4604-92a5-3b9697053e64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a8b84bcaec7dbadfb7b735264df12f7e958dcd20
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444703"
---
# <a name="modulecreate-method"></a>Module::Create Yöntemi

Bir modülün örneği oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
WRL_NOTHROW static Module& Create();
template<typename T>
WRL_NOTHROW static Module& Create(
   T callback
);
template<typename T>
WRL_NOTHROW static Module& Create(
   _In_ T* object,
   _In_ void (T::* method)()  
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Modül türü.

*geri çağırma*<br/>
Son örnek nesnesi modülünün bırakıldığında çağırılır.

*object*<br/>
*Nesne* ve *yöntemi* parametreleri birlikte kullanılır. Son örnek nesne modülünde yayımlandığında son örnek nesnesi işaret eder.

*Yöntemi*<br/>
*Nesne* ve *yöntemi* parametreleri birlikte kullanılır. Nesnenin son örnek nesne modülünde yayımlandığında son örneği noktaları yöntemi.

## <a name="return-value"></a>Dönüş Değeri

Modül başvuru.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Modül Sınıfı](../windows/module-class.md)