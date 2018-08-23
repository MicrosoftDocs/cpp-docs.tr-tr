---
title: AsyncBase::get_ErrorCode metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::get_ErrorCode
dev_langs:
- C++
helpviewer_keywords:
- get_ErrorCode method
ms.assetid: 50b4f8a2-9a21-4ea0-bb5d-7ff524d62aea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8e1e9355b6063ae67a40373828f394e3e6334f7d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613428"
---
# <a name="asyncbasegeterrorcode-method"></a>AsyncBase::get_ErrorCode Metodu

Geçerli zaman uyumsuz işlem hata kodunu alır.

## <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(
   get_ErrorCode
)(HRESULT* errorCode) override;
```

### <a name="parameters"></a>Parametreler

*hata kodu*  
Geçerli hata kodu nerede depolandığını konumu.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, geçerli zaman uyumsuz işlemin kapatılırsa E_ILLEGAL_METHOD_CALL.

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[AsyncBase Sınıfı](../windows/asyncbase-class.md)