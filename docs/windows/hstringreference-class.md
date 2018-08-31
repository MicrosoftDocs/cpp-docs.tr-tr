---
title: HStringReference sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference
dev_langs:
- C++
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4e3f7d59dd86aa15833134223854eb9ed01f6679
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43216581"
---
# <a name="hstringreference-class"></a>HStringReference Sınıfı

Varolan bir dizeden oluşturulan bir HSTRING temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class HStringReference;
```

## <a name="remarks"></a>Açıklamalar

Yeni HSTRING öğesindeki yedekleme arabelleğinin yaşam süresi Windows çalışma zamanı tarafından yönetilmiyor. Arayanın yığın ayırmasını engellemek ve bellek sızıntısı riskini ortadan kaldırmak için yığın çerçevesinde bir kaynak dizesi ayırır. Ayrıca, arayanın eklenen HSTRING ömrü boyunca kaynak dizesi değişmeden kalır emin olmalısınız. Daha fazla bilgi için [WindowsCreateStringReference işlevi](https://msdn.microsoft.com/0361bb7e-da49-4289-a93e-de7aab8712ac).

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[HStringReference::HStringReference Oluşturucusu](../windows/hstringreference-hstringreference-constructor.md)|Yeni bir örneğini başlatır **HStringReference** sınıfı.|

### <a name="members"></a>Üyeler

|Üye|Açıklama|
|------------|-----------------|
|[HStringReference::CopyTo Metodu](../windows/hstringreference-copyto-method.md)|Geçerli kopyalar **HStringReference** nesnesini bir HSTRING nesnesine.|
|[HStringReference::Get Metodu](../windows/hstringreference-get-method.md)|Temel HSTRING tanıtıcısının değerini alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[HStringReference::Operator= İşleci](../windows/hstringreference-operator-assign-operator.md)|Başka bir değer taşır **HStringReference** geçerli nesneye **HStringReference** nesne.|
|[HStringReference::Operator== İşleci](../windows/hstringreference-operator-equality-operator.md)|İki parametrenin eşit olup olmadığını gösterir.|
|[HStringReference::Operator!= İşleci](../windows/hstringreference-operator-inequality-operator.md)|İki parametrenin eşit olup olmadığını gösterir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`HStringReference`

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::wrl:: Wrappers

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Wrappers Ad Alanı](../windows/microsoft-wrl-wrappers-namespace.md)