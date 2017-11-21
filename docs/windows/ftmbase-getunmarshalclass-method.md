---
title: "FtmBase::GetUnmarshalClass yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass
dev_langs: C++
helpviewer_keywords: GetUnmarshalClass method
ms.assetid: 535fc539-5b97-4967-b158-f7568f13d341
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 967c8e8cc397a7f9efdb145bf337049627f24a2c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ftmbasegetunmarshalclass-method"></a>FtmBase::GetUnmarshalClass Metodu
COM için karşılık gelen proxy kodu içeren DLL bulmak için kullandığı CLSID alır. COM proxy başlatılmamış bir örneğini oluşturmak için bu DLL yükler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHODIMP GetUnmarshalClass(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out CLSID *pCid  
) override;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `riid`  
 Arabirim sıralanması tanıtıcısı başvuru.  
  
 `pv`  
 İşaretçi sıralanması arabirimine; Arayan istenen arabirimine bir işaretçi yoksa NULL olabilir.  
  
 `dwDestContext`  
 Burada belirtilen arabirim iptal edilip hedef bağlamı.  
  
 Bir veya daha fazla MSHCTX numaralandırma değerlerini belirtin.  
  
 Unmarshaling (MSHCTX_INPROC) geçerli işlem, başka bir grup veya geçerli işlem (MSHCTX_LOCAL) ile aynı bilgisayarda başka bir işlem ortaya çıkabilir.  
  
 `pvDestContext`  
 Gelecekte kullanılmak üzere ayrılmış; NULL olmamalıdır.  
  
 `mshlflags`  
 Bu işlem tamamlandığında istemci işleminde bir proxy sunucu oluşturmak için kullanılacak CLSID işaretçi.  
  
 `pCid`  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde S_FALSE.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [FtmBase sınıfı](../windows/ftmbase-class.md)