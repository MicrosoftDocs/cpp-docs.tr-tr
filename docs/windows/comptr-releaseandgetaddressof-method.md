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
ms.openlocfilehash: e3efdce7cde39431a8d6f097aace2ed2f5a66b4d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42589953"
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

[ComPtr Sınıfı](../windows/comptr-class.md)  
[ComPtr::ptr_ Veri Üyesi](../windows/comptr-ptr-data-member.md)