---
title: FtmBase::ReleaseMarshalData yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::ReleaseMarshalData
dev_langs:
- C++
helpviewer_keywords:
- ReleaseMarshalData method
ms.assetid: a94f9940-183a-4fde-8504-d223f346a0a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6c536d3708141250c6e0ab19cacb22fe989dc236
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39568764"
---
# <a name="ftmbasereleasemarshaldata-method"></a>FtmBase::ReleaseMarshalData Yöntemi
Bir sıralanmış veri paketi yok eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHODIMP ReleaseMarshalData(  
   __in IStream *pStm  
) override;  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pStm*  
 Yok edilecek veri paketi içeren bir akışa yönelik işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [FtmBase Sınıfı](../windows/ftmbase-class.md)