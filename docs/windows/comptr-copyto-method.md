---
title: ComPtr::CopyTo yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::CopyTo
dev_langs:
- C++
helpviewer_keywords:
- CopyTo method
ms.assetid: 8801bc49-6db4-4393-a55f-a701ae3b8718
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c295767070da04d0173e3299576338e700a1c6aa
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597019"
---
# <a name="comptrcopyto-method"></a>ComPtr::CopyTo Yöntemi

Şununla ilişkili geçerli ya da belirtilen arabirim kopyalar **ComPtr** belirtilen işaretçi.

## <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CopyTo(
   _Deref_out_ InterfaceType** ptr
);

HRESULT CopyTo(
   REFIID riid,
   _Deref_out_ void** ptr
) const;

template<typename U>
HRESULT CopyTo(
   _Deref_out_ U** ptr
) const;
```

### <a name="parameters"></a>Parametreler

*U*  
Tür adı.

*ptr*  
Bu işlem tamamlandığında istenen arabirim işaretçisi.

*riid*  
Bir arabirim kimliği.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, nedenini belirten bir HRESULT örtük `QueryInterface` işlemi başarısız oldu.

## <a name="remarks"></a>Açıklamalar

İlk işlev, bununla ilişkili arabirimi için bir işaretçi bir kopyasını döndürür. **ComPtr**. Bu işlev her zaman S_OK döndürür.

İkinci işlevi gerçekleştiren bir `QueryInterface` işlemi ile ilişkili arabirimde **ComPtr** tarafından belirtilen arabirim için *riid* parametresi.

Üçüncü işlevi gerçekleştiren bir `QueryInterface` işlemi ile ilişkili arabirimde **ComPtr** temel arabirimi için *U* parametresi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[ComPtr Sınıfı](../windows/comptr-class.md)