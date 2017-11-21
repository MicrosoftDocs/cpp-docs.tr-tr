---
title: "Ftmbase::marshalınterface yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: ftm/Microsoft::WRL::FtmBase::MarshalInterface
dev_langs: C++
helpviewer_keywords: MarshalInterface method
ms.assetid: fc8421b4-06e4-4925-b908-c285fe4790d2
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2b6bd889a20c2c31de8e5fb6d11990fc2579ef2d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ftmbasemarshalinterface-method"></a>FtmBase::MarshalInterface Metodu
Bazı istemci işleminde proxy nesneyi başlatmak için gerekli olan veriler bir akışa yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHODIMP MarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags  
) override;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pStm`  
 Hazırlama sırasında kullanılacak akış işaretçi.  
  
 `riid`  
 Arabirim sıralanması tanıtıcısı başvuru. Bu arabirim IUnknown arabiriminden türetilmiş olmalıdır.  
  
 `pv`  
 Arabirim işaretçisi sıralanması işaretçi; Arayan istenen arabirimine bir işaretçi yoksa NULL olabilir.  
  
 `dwDestContext`  
 Burada belirtilen arabirim iptal edilip hedef bağlamı.  
  
 Bir veya daha fazla MSHCTX numaralandırma değerlerini belirtin.  
  
 Unmarshaling (MSHCTX_INPROC) geçerli işlem, başka bir Grup ya da geçerli işlem (MSHCTX_LOCAL) ile aynı bilgisayarda başka bir işlemde ortaya çıkabilir.  
  
 `pvDestContext`  
 Gelecekte kullanılmak üzere ayrılmış; sıfır olmalıdır.  
  
 `mshlflags`  
 Sıralanması için verileri geri istemci işlemi iletilmesi olup olmadığını belirtir — normal durum — veya burada alınabileceği birden çok istemciler tarafından genel bir tabloya yazılır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 S_OK  
 Arabirim işaretçisi başarıyla başvuruya.  
  
 E_NOINTERFACE  
 Belirtilen arabirim desteklenmiyor.  
  
 STG_E_MEDIUMFULL  
 Akış dolu.  
  
 E_FAIL  
 İşlem başarısız oldu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [FtmBase sınıfı](../windows/ftmbase-class.md)