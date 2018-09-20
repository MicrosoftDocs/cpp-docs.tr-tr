---
title: ComPtr::ReleaseAndGetAddressOf yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- ReleaseAndGetAddressOf method
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7f4aee13808fd55c42319aab90c13af7922ed9d2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394848"
---
# <a name="comptrreleaseandgetaddressof-method"></a>ComPtr::ReleaseAndGetAddressOf Yöntemi

Şununla ilişkili arabirimini yayımlar **ComPtr** ve adresini alır. [ptr_](../windows/comptr-ptr-data-member.md) yayımlanan arabirimi için bir işaretçi içeren veri üyesi.

## <a name="syntax"></a>Sözdizimi

```cpp
T** ReleaseAndGetAddressOf();
```

## <a name="return-value"></a>Dönüş Değeri

Adresini [ptr_](../windows/comptr-ptr-data-member.md) veri üyesi bu **ComPtr**.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[ComPtr Sınıfı](../windows/comptr-class.md)<br/>
[ComPtr::ptr_ Veri Üyesi](../windows/comptr-ptr-data-member.md)