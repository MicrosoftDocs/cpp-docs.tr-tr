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
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9df1e5d7559b434c1af0f1feff3b73b8141a8865
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [FtmBase Sınıfı](../windows/ftmbase-class.md)