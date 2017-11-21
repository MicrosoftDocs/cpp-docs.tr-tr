---
title: "FtmBase::GetMarshalSizeMax yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: ftm/Microsoft::WRL::FtmBase::GetMarshalSizeMax
dev_langs: C++
helpviewer_keywords: GetMarshalSizeMax method
ms.assetid: b416b1bf-c73e-45d5-abb8-04921c1a0c94
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3597d19e1bcdc6b1b14e150c66236585f8c35fb8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ftmbasegetmarshalsizemax-method"></a>FtmBase::GetMarshalSizeMax Metodu
Belirtilen nesne üzerindeki belirtilen arabirim işaretçisi hazırlamak için gereken bayt sayısı üst sınırı öğrenin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHODIMP GetMarshalSizeMax(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out DWORD *pSize  
) override;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `riid`  
 Arabirim sıralanması tanıtıcısı başvuru.  
  
 `pv`  
 Arabirim işaretçisi; sıralanması için NULL olabilir.  
  
 `dwDestContext`  
 Burada belirtilen arabirim iptal edilip hedef bağlamı.  
  
 Bir veya daha fazla MSHCTX numaralandırma değerlerini belirtin.  
  
 Şu anda unmarshaling (MSHCTX_INPROC) geçerli işlem, başka bir grup veya geçerli işlem (MSHCTX_LOCAL) ile aynı bilgisayarda başka bir işlemde ortaya çıkabilir.  
  
 `pvDestContext`  
 Gelecekte kullanılmak üzere ayrılmış; NULL olmamalıdır.  
  
 `mshlflags`  
 Sıralanması için verileri geri istemci işlemi aktarılacak olup olmadığını belirten bayrak — normal durum — veya burada alınabileceği birden çok istemciler tarafından genel bir tabloya yazılır. Bir veya daha fazla MSHLFLAGS numaralandırma değerlerini belirtin.  
  
 `pSize`  
 Bu işlem tamamlandığında, üst sınır hazırlama akışa yazılmasına veri miktarına yönelik işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde E_FAIL veya E_NOINTERFACE.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [FtmBase sınıfı](../windows/ftmbase-class.md)