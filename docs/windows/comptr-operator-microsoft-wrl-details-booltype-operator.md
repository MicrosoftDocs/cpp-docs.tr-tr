---
title: ComPtr::operator Microsoft::WRL::Details::BoolType işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 05e26296646b61997baff880a671958769eb099b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433406"
---
# <a name="comptroperator-microsoftwrldetailsbooltype-operator"></a>ComPtr::operator Microsoft::WRL::Details::BoolType İşleci

Belirtir olup olmadığını bir **ComPtr** bir arabirimin nesne ömrü yönetimi.

## <a name="syntax"></a>Sözdizimi

```cpp
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;
```

## <a name="return-value"></a>Dönüş Değeri

Bir arabirim ile ilişkili ise **ComPtr**, adresini [BoolStruct::Member](../windows/boolstruct-member-data-member.md) veri üyesi; Aksi takdirde **nullptr**.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[ComPtr Sınıfı](../windows/comptr-class.md)<br/>
[ComPtr::Get Metodu](../windows/comptr-get-method.md)