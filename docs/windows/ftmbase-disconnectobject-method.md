---
title: FtmBase::DisconnectObject yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::DisconnectObject
dev_langs:
- C++
helpviewer_keywords:
- DisconnectObject method
ms.assetid: 33253eec-3a65-4e72-8525-0249245a4790
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b467162d2f5cc5b04bc43a6d31019eb08e17e750
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595412"
---
# <a name="ftmbasedisconnectobject-method"></a>FtmBase::DisconnectObject Yöntemi

Zorla tüm dış bağlantılar kurulmasına nesnenin serbest bırakır. Nesnenin sunucu nesnenin uygulaması kapatmadan önce bu yöntemi çağırır.

## <a name="syntax"></a>Sözdizimi

```cpp
STDMETHODIMP DisconnectObject(
   __in DWORD dwReserved
) override;
```

### <a name="parameters"></a>Parametreler

*dwReserved*  
Gelecekte kullanılmak üzere ayrılmış; sıfır olmalıdır.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** ftm.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[FtmBase Sınıfı](../windows/ftmbase-class.md)