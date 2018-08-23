---
title: Runtimeclassbaset::getımplementedııds metodu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS
dev_langs:
- C++
helpviewer_keywords:
- GetImplementedIIDS method
ms.assetid: adae54da-521d-4add-87f5-242fbd85f33b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 907a249090ec58d6379cb58f3d63e15826c1f6ad
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610366"
---
# <a name="runtimeclassbasetgetimplementediids-method"></a>RuntimeClassBaseT::GetImplementedIIDS Metodu

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
__forceinline static HRESULT GetImplementedIIDS(
   _In_ T* implements,
   _Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids
);
```

### <a name="parameters"></a>Parametreler

*T*  
Türünü *uygulayan* parametresi.

*Uygulayan*  
Parametresi tarafından belirtilen türe işaretçi *T*.

*Iidcount*  
Arabirim kimlikleri alınacak maksimum sayısı.

*IID'leri*  
Bu işlem kimlikleri tür tarafından uygulanan arabirimi dizisi başarıyla tamamlanırsa *T*.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.

## <a name="remarks"></a>Açıklamalar

Belirtilen bir tür tarafından uygulanan kimlikleri arabiriminin dizisini alır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[RuntimeClassBaseT Yapısı](../windows/runtimeclassbaset-structure.md)