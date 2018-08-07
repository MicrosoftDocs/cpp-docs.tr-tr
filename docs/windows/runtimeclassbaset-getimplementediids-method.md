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
ms.openlocfilehash: bf29b5db15f88528012914476572cb1ccb21a07c
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603257"
---
# <a name="runtimeclassbasetgetimplementediids-method"></a>RuntimeClassBaseT::GetImplementedIIDS Metodu
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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