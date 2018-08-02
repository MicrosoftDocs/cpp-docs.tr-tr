---
title: AsyncBase::Close yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: a52b1124-754b-4393-b491-64aae0c22f1c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9d0798a6ef593e388ce7867ee9a55763be9ae890
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463365"
---
# <a name="asyncbaseclose-method"></a>AsyncBase::Close Yöntemi
Zaman uyumsuz işlemi kapatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHOD(  
   Close  
)(void) override;  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 İşlemi kapatır veya zaten S_OK kapalı; Aksi takdirde, E_ILLEGAL_STATE_CHANGE.  
  
## <a name="remarks"></a>Açıklamalar  
 **Çağrısının** varsayılan uygulamasıdır `IAsyncInfo::Close`, ve hiçbir asıl işi yapar. Zaman uyumsuz bir işlem gerçekten kapatmak için geçersiz kılma `OnClose()` saf sanal yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase Sınıfı](../windows/asyncbase-class.md)