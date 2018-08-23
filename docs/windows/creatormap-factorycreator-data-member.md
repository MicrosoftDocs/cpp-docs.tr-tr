---
title: CreatorMap::factoryCreator veri üyesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap::factoryCreator
dev_langs:
- C++
helpviewer_keywords:
- factoryCreator data member
ms.assetid: c9aac363-8f38-4cfd-9605-1e6ac74c5097
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 90367a21d76fe7fe735d1174bc9b9d40900dec78
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600836"
---
# <a name="creatormapfactorycreator-data-member"></a>CreatorMap::factoryCreator Veri Üyesi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
HRESULT (*factoryCreator)(
   unsigned int* currentflags,
   const CreatorMap* entry,
   REFIID iidClassFactory,
 IUnknown** factory);
```

### <a name="parameters"></a>Parametreler

*currentflags*  
Aşağıdakilerden birini [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) numaralandırıcılar.

*entry*  
CreatorMap bir.

*iidClassFactory*  
Bir sınıf üreteci arabirim kimliği.

*Fabrika*  
İşlem tamamlandığında bir sınıf üreteci adresidir.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="remarks"></a>Açıklamalar

Belirtilen CreatorMap için bir üreteci oluşturur.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[CreatorMap Yapısı](../windows/creatormap-structure.md)  
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)